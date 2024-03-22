---
title: liblava/util/telegram.hpp
summary: Telegram dispatcher. 

---

# liblava/util/telegram.hpp

Telegram dispatcher.  [More...](#detailed-description)

## Namespaces

| Name           |
| -------------- |
| **[lava](/_doxybook/Namespaces/namespacelava.md)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| struct | **[lava::telegram](/_doxybook/Classes/structlava_1_1telegram.md)** <br>Telegram.  |
| struct | **[lava::dispatcher](/_doxybook/Classes/structlava_1_1dispatcher.md)** <br>Telegram dispatcher.  |

## Detailed Description

Telegram dispatcher. 

**Author**: Lava Block OÜ and contributors 

**Copyright**: Copyright (c) 2018-present, MIT License 



## Source code

```cpp

#pragma once

#include <any>
#include <cmath>
#include <set>
#include "liblava/util/thread.hpp"

namespace lava {

constexpr ms const telegram_min_delay{ 250 };

using any = std::any;

struct telegram {
    using ref = telegram const&;

    explicit telegram(id::ref sender,
                      id::ref receiver,
                      id::ref msg,
                      ms dispatch_time = {},
                      any info = {})
    : sender(sender), receiver(receiver),
      msg(msg), dispatch_time(dispatch_time),
      info(std::move(info)) {}

    bool operator==(ref rhs) const {
        return ((dispatch_time - rhs.dispatch_time) < telegram_min_delay)
               && (sender == rhs.sender)
               && (receiver == rhs.receiver)
               && (msg == rhs.msg);
    }

    bool operator<(ref rhs) const {
        if (*this == rhs)
            return false;

        return (dispatch_time < rhs.dispatch_time);
    }

    id sender;

    id receiver;

    id msg;

    ms dispatch_time;

    any info;
};

struct dispatcher {
    void setup(ui32 thread_count) {
        pool.setup(thread_count);
    }

    void teardown() {
        pool.teardown();
    }

    void update(ms current) {
        current_time = current;
        dispatch_delayed_messages(current_time);
    }

    void add_message(id::ref receiver,
                     id::ref sender,
                     id::ref message,
                     ms delay = {},
                     any const& info = {}) {
        telegram msg(sender,
                     receiver,
                     message,
                     current_time,
                     info);

        if (delay == ms{ 0 }) {
            discharge(msg); // now
            return;
        }

        msg.dispatch_time += delay;
        messages.insert(msg);
    }

    using message_func = std::function<void(telegram::ref, id::ref)>;

    message_func on_message;

private:
    void discharge(telegram::ref message) {
        pool.enqueue([&, message](id::ref thread_id) {
            if (on_message)
                on_message(message, thread_id);
        });
    }

    void dispatch_delayed_messages(ms time) {
        while (!messages.empty()
               && (messages.begin()->dispatch_time < time)
               && (messages.begin()->dispatch_time > ms{})) {
            discharge(*messages.begin());

            messages.erase(messages.begin());
        }
    }

    ms current_time;

    thread_pool pool;

    std::set<telegram> messages;
};

} // namespace lava
```


-------------------------------

Updated on 2024-03-22 at 21:51:38 +0000
