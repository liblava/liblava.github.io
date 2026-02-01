---
title: lava::input_events
summary: List of input events. 

---

# lava::input_events



List of input events.  [More...](#detailed-description)


`#include <input.hpp>`

Inherits from T::list

## Public Functions

|                | Name           |
| -------------- | -------------- |
| void | **[add](/_doxybook/Classes/structlava_1_1input__events.md#function-add)**(typename T::ref event)<br>Add event to list.  |

## Public Attributes

|                | Name           |
| -------------- | -------------- |
| [id_listeners](/_doxybook/Classes/structlava_1_1id__listeners.md)< T > | **[listeners](/_doxybook/Classes/structlava_1_1input__events.md#variable-listeners)** <br>List of event listeners.  |

## Detailed Description

```cpp
template <typename T >
struct lava::input_events;
```

List of input events. 

**Template Parameters**: 

  * **T** Type of event 

## Public Functions Documentation

### function add

```cpp
inline void add(
    typename T::ref event
)
```

Add event to list. 

**Parameters**: 

  * **event** Event to add 


## Public Attributes Documentation

### variable listeners

```cpp
id_listeners< T > listeners;
```

List of event listeners. 

-------------------------------

Updated on 2026-02-01 at 18:13:39 +0000