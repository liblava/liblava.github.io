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

#include <condition_variable>
#include <deque>
#include <liblava/core/id.hpp>
#include <liblava/core/time.hpp>
#include <mutex>
#include <thread>

namespace lava {

inline void sleep(ms time) {
    std::this_thread::sleep_for(time);
}

inline void sleep(seconds time) {
    std::this_thread::sleep_for(time);
}

struct thread_pool {
    using task = std::function<void(id::ref)>;

    void setup(ui32 count = 2) {
        for (auto i = 0u; i < count; ++i)
            workers.emplace_back(worker(*this));
    }

    void teardown() {
        stop = true;
        condition.notify_all();

        for (auto& worker : workers)
            worker.join();

        workers.clear();
    }

    void enqueue(auto f) {
        {
            std::unique_lock<std::mutex> lock(queue_mutex);
            tasks.push_back(task(f));
        }
        condition.notify_one();
    }

private:
    struct worker {
        explicit worker(thread_pool& pool)
        : pool(pool) {}

        void operator()() {
            auto thread_id = ids::instance().next();

            task task;
            while (true) {
                {
                    std::unique_lock<std::mutex> lock(pool.queue_mutex);

                    while (!pool.stop && pool.tasks.empty())
                        pool.condition.wait(lock);

                    if (pool.stop)
                        break;

                    task = pool.tasks.front();
                    pool.tasks.pop_front();
                }

                task(thread_id);
            }
        }

    private:
        thread_pool& pool;
    };

    std::vector<std::thread> workers;

    std::deque<task> tasks;

    std::mutex queue_mutex;

    std::condition_variable condition;

    bool stop = false;
};

} // namespace lava
```


-------------------------------

Updated on 2022-11-30 at 01:16:04 +0000
