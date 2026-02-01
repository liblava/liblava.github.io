---
title: lava::mouse_move_event
summary: Mouse move event. 

---

# lava::mouse_move_event



Mouse move event. 


`#include <input.hpp>`

## Public Types

|                | Name           |
| -------------- | -------------- |
| using [mouse_move_event](/_doxybook/Classes/structlava_1_1mouse__move__event.md) const  & | **[ref](/_doxybook/Classes/structlava_1_1mouse__move__event.md#using-ref)** <br>Reference to mouse move event.  |
| using std::function< bool([ref](/_doxybook/Classes/structlava_1_1mouse__move__event.md#using-ref))> | **[func](/_doxybook/Classes/structlava_1_1mouse__move__event.md#using-func)** <br>Mouse move event function.  |
| using std::map< [id](/_doxybook/Classes/structlava_1_1id.md), [func](/_doxybook/Classes/structlava_1_1mouse__move__event.md#using-func) > | **[listeners](/_doxybook/Classes/structlava_1_1mouse__move__event.md#using-listeners)** <br>List of mouse move event listeners.  |
| using std::vector< [mouse_move_event](/_doxybook/Classes/structlava_1_1mouse__move__event.md) > | **[list](/_doxybook/Classes/structlava_1_1mouse__move__event.md#using-list)** <br>List of mouse move events.  |

## Public Attributes

|                | Name           |
| -------------- | -------------- |
| [id](/_doxybook/Classes/structlava_1_1id.md) | **[sender](/_doxybook/Classes/structlava_1_1mouse__move__event.md#variable-sender)** <br>Sender id.  |
| [mouse_position](/_doxybook/Classes/structlava_1_1mouse__position.md) | **[position](/_doxybook/Classes/structlava_1_1mouse__move__event.md#variable-position)** <br>Input mouse position.  |

## Public Types Documentation

### using ref

```cpp
using lava::mouse_move_event::ref =  mouse_move_event const&;
```

Reference to mouse move event. 

### using func

```cpp
using lava::mouse_move_event::func =  std::function<bool(ref)>;
```

Mouse move event function. 

### using listeners

```cpp
using lava::mouse_move_event::listeners =  std::map<id, func>;
```

List of mouse move event listeners. 

### using list

```cpp
using lava::mouse_move_event::list =  std::vector<mouse_move_event>;
```

List of mouse move events. 

## Public Attributes Documentation

### variable sender

```cpp
id sender;
```

Sender id. 

### variable position

```cpp
mouse_position position;
```

Input mouse position. 

-------------------------------

Updated on 2026-02-01 at 18:13:39 +0000