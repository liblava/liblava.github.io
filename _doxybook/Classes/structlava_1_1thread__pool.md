---
title: lava::thread_pool
summary: Thread pool. 

---

# lava::thread_pool



Thread pool. 


`#include <thread.hpp>`

## Public Types

|                | Name           |
| -------------- | -------------- |
| using std::function< void([id::ref](/_doxybook/Classes/structlava_1_1id.md#using-ref))> | **[task](/_doxybook/Classes/structlava_1_1thread__pool.md#using-task)** <br>Task function (with thread id)  |

## Public Functions

|                | Name           |
| -------------- | -------------- |
| void | **[setup](/_doxybook/Classes/structlava_1_1thread__pool.md#function-setup)**([ui32](/_doxybook/Namespaces/namespacelava.md#using-ui32) count =2)<br>Set up the thread pool.  |
| void | **[teardown](/_doxybook/Classes/structlava_1_1thread__pool.md#function-teardown)**()<br>Tear down the thread pool.  |
| void | **[enqueue](/_doxybook/Classes/structlava_1_1thread__pool.md#function-enqueue)**(auto f)<br>Enqueue a task.  |

## Public Types Documentation

### using task

```cpp
using lava::thread_pool::task =  std::function<void(id::ref)>;
```

Task function (with thread id) 

## Public Functions Documentation

### function setup

```cpp
inline void setup(
    ui32 count =2
)
```

Set up the thread pool. 

**Parameters**: 

  * **count** Number of threads 


### function teardown

```cpp
inline void teardown()
```

Tear down the thread pool. 

### function enqueue

```cpp
inline void enqueue(
    auto f
)
```

Enqueue a task. 

**Parameters**: 

  * **f** Task function 


-------------------------------

Updated on 2026-02-01 at 18:13:39 +0000