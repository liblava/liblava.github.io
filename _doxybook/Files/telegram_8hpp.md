---
title: liblava/util/telegram.hpp
summary: Message dispatcher. 

---

# liblava/util/telegram.hpp

Message dispatcher.  [More...](#detailed-description)

## Namespaces

| Name           |
| -------------- |
| **[lava](/_doxybook/Namespaces/namespacelava.md)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| struct | **[lava::telegram](/_doxybook/Classes/structlava_1_1telegram.md)** <br>Telegram.  |
| struct | **[lava::telegraph](/_doxybook/Classes/structlava_1_1telegraph.md)** <br>Telegraph station.  |
| struct | **[lava::message_dispatcher](/_doxybook/Classes/structlava_1_1message__dispatcher.md)** <br>Message dispatcher.  |

## Detailed Description

Message dispatcher. 

**Author**: Lava Block OÜ and contributors 

**Copyright**: Copyright (c) 2018-present, MIT License 



## Source code

```cpp


#pragma once

#include "liblava/util/thread.hpp"
#include <any>
#include <cmath>
#include <set>

namespace lava {

constexpr ms const telegram_min_delay{250};

using any = std::any;

struct telegram {
    using ref = telegram const&;

    using set = std::multiset<telegram>;

    explicit telegram(id::ref sender,
                      id::ref receiver,
                      index msg,
                      ms dispatch_time = {},
                      any info = {})
    : sender(sender), receiver(receiver),
      msg_id(msg), dispatch_time(dispatch_time),
      info(std::move(info)) {}

    bool operator==(ref rhs) const {
        return ((dispatch_time - rhs.dispatch_time) < telegram_min_delay)
               && (sender == rhs.sender)
               && (receiver == rhs.receiver)
               && (msg_id == rhs.msg_id);
    }

    bool operator<(ref rhs) const {
        if (*this == rhs)
            return false;

        return (dispatch_time < rhs.dispatch_time);
    }

    id sender;

    id receiver;

    index msg_id = no_index;

    ms dispatch_time;

    any info;
};

struct telegraph : interface {
    virtual void send_message(id::ref receiver,
                              id::ref sender,
                              index message,
                              ms delay = {},
                              any const& info = {}) = 0;
};

struct message_dispatcher : telegraph {
    ~message_dispatcher() {
        teardown();
    }

    void setup(ui32 thread_count) {
        m_pool.setup(thread_count);
    }

    void teardown() {
        m_pool.teardown();
    }

    void update(ms current) {
        m_current_time = current;
        dispatch_delayed_messages(m_current_time);
    }

    void send_message(id::ref receiver,
                      id::ref sender,
                      index message,
                      ms delay = {},
                      any const& info = {}) override {
        telegram msg(sender,
                     receiver,
                     message,
                     m_current_time,
                     info);

        if (delay == ms{0}) {
            discharge(msg); // now
            return;
        }

        msg.dispatch_time += delay;
        m_messages.insert(msg);
    }

    using message_func = std::function<void(telegram::ref, id::ref)>;

    bool add_dispatch(id::ref target, message_func func) {
        std::lock_guard guard(m_lock);

        if (m_dispatches.count(target))
            return false;

        m_dispatches.emplace(target, func);
        return true;
    }

    bool remove_dispatch(id::ref target) {
        std::lock_guard guard(m_lock);

        if (!m_dispatches.count(target))
            return false;

        m_dispatches.erase(target);
        return true;
    }

    bool has_dispatch(id::ref target) const {
        return m_dispatches.count(target);
    }

private:
    void discharge(telegram::ref message) {
        m_pool.enqueue([&, message](id::ref thread_id) {
            std::lock_guard guard(m_lock);

            auto dispatch = get_dispatch(message.receiver);
            LAVA_ASSERT(dispatch);
            if (dispatch)
                dispatch(message, thread_id);
        });
    }

    void dispatch_delayed_messages(ms time) {
        while (!m_messages.empty()
               && (m_messages.begin()->dispatch_time < time)) {
            discharge(*m_messages.begin());

            m_messages.erase(m_messages.begin());
        }
    }

    message_func get_dispatch(id::ref target) {
        if (!m_dispatches.count(target))
            return nullptr;

        return m_dispatches.at(target);
    }

    using dispatch_map = std::map<id, message_func>;

    dispatch_map m_dispatches;

    std::mutex m_lock;

    ms m_current_time;

    thread_pool m_pool;

    telegram::set m_messages;
};

} // namespace lava
```


-------------------------------

Updated on 2026-02-01 at 18:13:39 +0000
