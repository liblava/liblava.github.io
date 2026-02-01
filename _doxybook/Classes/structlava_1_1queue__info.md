---
title: lava::queue_info
summary: Queue information. 

---

# lava::queue_info



Queue information. 


`#include <queue.hpp>`

## Public Types

|                | Name           |
| -------------- | -------------- |
| using std::deque< [queue_info](/_doxybook/Classes/structlava_1_1queue__info.md) > | **[list](/_doxybook/Classes/structlava_1_1queue__info.md#using-list)** <br>List of queue informations.  |

## Public Attributes

|                | Name           |
| -------------- | -------------- |
| VkQueueFlags | **[flags](/_doxybook/Classes/structlava_1_1queue__info.md#variable-flags)** <br>Queue flags.  |
| [r32](/_doxybook/Namespaces/namespacelava.md#using-r32) | **[priority](/_doxybook/Classes/structlava_1_1queue__info.md#variable-priority)** <br>Queue priority.  |

## Public Types Documentation

### using list

```cpp
using lava::queue_info::list =  std::deque<queue_info>;
```

List of queue informations. 

## Public Attributes Documentation

### variable flags

```cpp
VkQueueFlags flags = default_queue_flags;
```

Queue flags. 

### variable priority

```cpp
r32 priority = 1.f;
```

Queue priority. 

-------------------------------

Updated on 2026-02-01 at 18:13:39 +0000