---
title: lava::id_listeners
summary: Id listeners. 

---

# lava::id_listeners



Id listeners.  [More...](#detailed-description)


`#include <id.hpp>`

## Public Functions

|                | Name           |
| -------------- | -------------- |
| [id](/_doxybook/Classes/structlava_1_1id.md) | **[add](/_doxybook/Classes/structlava_1_1id__listeners.md#function-add)**(typename T::func const & listener)<br>Add listener to map.  |
| void | **[remove](/_doxybook/Classes/structlava_1_1id__listeners.md#function-remove)**([id](/_doxybook/Classes/structlava_1_1id.md) & id)<br>Remove listener from map by id.  |
| T::listeners const & | **[get_list](/_doxybook/Classes/structlava_1_1id__listeners.md#function-get-list)**() const<br>Get the list.  |

## Detailed Description

```cpp
template <typename T >
struct lava::id_listeners;
```

Id listeners. 

**Template Parameters**: 

  * **T** Listener 

## Public Functions Documentation

### function add

```cpp
inline id add(
    typename T::func const & listener
)
```

Add listener to map. 

**Parameters**: 

  * **listener** Target listener 


**Return**: id Id of listener 

### function remove

```cpp
inline void remove(
    id & id
)
```

Remove listener from map by id. 

**Parameters**: 

  * **id** Id of listener 


### function get_list

```cpp
inline T::listeners const & get_list() const
```

Get the list. 

**Return**: T::listeners const& List of listeners 

-------------------------------

Updated on 2026-02-01 at 18:13:39 +0000