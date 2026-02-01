---
title: liblava/util/thread.hpp
summary: Thread pool. 

---

# liblava/util/thread.hpp

Thread pool.  [More...](#detailed-description)

## Namespaces

| Name           |
| -------------- |
| **[lava](/_doxybook/Namespaces/namespacelava.md)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| struct | **[lava::thread_pool](/_doxybook/Classes/structlava_1_1thread__pool.md)** <br>Thread pool.  |

## Detailed Description

Thread pool. 

**Author**: Lava Block OÜ and contributors 

**Copyright**: Copyright (c) 2018-present, MIT License 



## Source code

```cpp


#pragma once

#include "liblava/core/id.hpp"
#include "liblava/core/time.hpp"
#include <condition_variable>
#include <deque>
#include <mutex>
#include <thread>

namespace lava {

inline void sleep(seconds time) {
    std::this_thread::sleep_for(time);
}

inline void sleep(ms time) {
    std::this_thread::sleep_for(time);
}

inline void sleep(us time) {
    std::this_thread::sleep_for(time);
}

struct thread_pool {
    using task = std::function<void(id::ref)>;

    void setup(ui32 count = 2) {
        for (auto i = 0u; i < count; ++i)
            m_workers.emplace_back(worker(*this));
    }

    void teardown() {
        m_stop = true;
        m_condition.notify_all();

        for (auto& worker : m_workers)
            worker.join();

        m_workers.clear();
    }

    void enqueue(auto f) {
        {
            std::unique_lock<std::mutex> lock(m_queue_mutex);
            m_tasks.push_back(task(f));
        }
        m_condition.notify_one();
    }

private:
    struct worker {
        explicit worker(thread_pool& pool)
        : m_pool(pool) {}

        void operator()() {
            auto thread_id = ids::instance().next();

            task task;
            while (true) {
                {
                    std::unique_lock<std::mutex> lock(m_pool.m_queue_mutex);

                    while (!m_pool.m_stop && m_pool.m_tasks.empty())
                        m_pool.m_condition.wait(lock);

                    if (m_pool.m_stop)
                        break;

                    task = m_pool.m_tasks.front();
                    m_pool.m_tasks.pop_front();
                }

                task(thread_id);
            }
        }

    private:
        thread_pool& m_pool;
    };

    std::vector<std::thread> m_workers;

    std::deque<task> m_tasks;

    std::mutex m_queue_mutex;

    std::condition_variable m_condition;

    bool m_stop = false;
};

} // namespace lava
```


-------------------------------

Updated on 2026-02-01 at 18:13:39 +0000
