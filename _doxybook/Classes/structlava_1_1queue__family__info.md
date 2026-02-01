---
title: lava::queue_family_info
summary: Queue family information. 

---

# lava::queue_family_info



Queue family information. 


`#include <queue.hpp>`

## Public Types

|                | Name           |
| -------------- | -------------- |
| using std::deque< [queue_family_info](/_doxybook/Classes/structlava_1_1queue__family__info.md) > | **[list](/_doxybook/Classes/structlava_1_1queue__family__info.md#using-list)** <br>List of queue family informations.  |

## Public Functions

|                | Name           |
| -------------- | -------------- |
| void | **[add](/_doxybook/Classes/structlava_1_1queue__family__info.md#function-add)**(VkQueueFlags flags, [ui32](/_doxybook/Namespaces/namespacelava.md#using-ui32) count =1, [r32](/_doxybook/Namespaces/namespacelava.md#using-r32) priority =1.f)<br>Add a queue family information.  |
| [ui32](/_doxybook/Namespaces/namespacelava.md#using-ui32) | **[count](/_doxybook/Classes/structlava_1_1queue__family__info.md#function-count)**() const<br>Get the count of queues.  |
| void | **[clear](/_doxybook/Classes/structlava_1_1queue__family__info.md#function-clear)**()<br>Clear the queue information.  |

## Public Attributes

|                | Name           |
| -------------- | -------------- |
| [index](/_doxybook/Namespaces/namespacelava.md#using-index) | **[family_index](/_doxybook/Classes/structlava_1_1queue__family__info.md#variable-family-index)** <br>Queue family index.  |
| [queue_info::list](/_doxybook/Classes/structlava_1_1queue__info.md#using-list) | **[queues](/_doxybook/Classes/structlava_1_1queue__family__info.md#variable-queues)** <br>List of queue informations.  |

## Public Types Documentation

### using list

```cpp
using lava::queue_family_info::list =  std::deque<queue_family_info>;
```

List of queue family informations. 

## Public Functions Documentation

### function add

```cpp
inline void add(
    VkQueueFlags flags,
    ui32 count =1,
    r32 priority =1.f
)
```

Add a queue family information. 

**Parameters**: 

  * **flags** Queue flags 
  * **count** Number of queues 
  * **priority** Queue priority 


### function count

```cpp
inline ui32 count() const
```

Get the count of queues. 

**Return**: [ui32](/_doxybook/Namespaces/namespacelava.md#using-ui32) Count of queues 

### function clear

```cpp
inline void clear()
```

Clear the queue information. 

## Public Attributes Documentation

### variable family_index

```cpp
index family_index = 0;
```

Queue family index. 

### variable queues

```cpp
queue_info::list queues;
```

List of queue informations. 

-------------------------------

Updated on 2026-02-01 at 18:13:39 +0000