---
title: lava::queue
summary: Device queue. 

---

# lava::queue



Device queue. 


`#include <queue.hpp>`

## Public Types

|                | Name           |
| -------------- | -------------- |
| using std::deque< [queue](/_doxybook/Classes/structlava_1_1queue.md) > | **[list](/_doxybook/Classes/structlava_1_1queue.md#using-list)** <br>List of queues.  |
| using [queue](/_doxybook/Classes/structlava_1_1queue.md) const  & | **[ref](/_doxybook/Classes/structlava_1_1queue.md#using-ref)** <br>Reference to queue.  |

## Public Functions

|                | Name           |
| -------------- | -------------- |
| bool | **[valid](/_doxybook/Classes/structlava_1_1queue.md#function-valid)**() const<br>Check if queue is valid.  |
| bool | **[operator<](/_doxybook/Classes/structlava_1_1queue.md#function-operator<)**([queue](/_doxybook/Classes/structlava_1_1queue.md) const & other) const<br>Queue priority compare operator.  |

## Public Attributes

|                | Name           |
| -------------- | -------------- |
| VkQueue | **[vk_queue](/_doxybook/Classes/structlava_1_1queue.md#variable-vk-queue)** <br>Vulkan queue.  |
| VkQueueFlags | **[flags](/_doxybook/Classes/structlava_1_1queue.md#variable-flags)** <br>Queue flags.  |
| [index](/_doxybook/Namespaces/namespacelava.md#using-index) | **[family](/_doxybook/Classes/structlava_1_1queue.md#variable-family)** <br>Queue family index.  |
| [r32](/_doxybook/Namespaces/namespacelava.md#using-r32) | **[priority](/_doxybook/Classes/structlava_1_1queue.md#variable-priority)** <br>Queue priority.  |

## Public Types Documentation

### using list

```cpp
using lava::queue::list =  std::deque<queue>;
```

List of queues. 

### using ref

```cpp
using lava::queue::ref =  queue const&;
```

Reference to queue. 

## Public Functions Documentation

### function valid

```cpp
inline bool valid() const
```

Check if queue is valid. 

**Return**: Queue is valid or not 

### function operator<

```cpp
inline bool operator<(
    queue const & other
) const
```

Queue priority compare operator. 

**Parameters**: 

  * **other** Queue to compare 


**Return**: Priority of queue is higher or lower and equal 

## Public Attributes Documentation

### variable vk_queue

```cpp
VkQueue vk_queue = nullptr;
```

Vulkan queue. 

### variable flags

```cpp
VkQueueFlags flags = 0;
```

Queue flags. 

### variable family

```cpp
index family = 0;
```

Queue family index. 

### variable priority

```cpp
r32 priority = 1.f;
```

Queue priority. 

-------------------------------

Updated on 2026-02-01 at 18:13:39 +0000