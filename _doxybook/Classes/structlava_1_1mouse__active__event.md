---
title: lava::mouse_active_event
summary: Mouse active event. 

---

# lava::mouse_active_event



Mouse active event. 


`#include <input.hpp>`

## Public Types

|                | Name           |
| -------------- | -------------- |
| using [mouse_active_event](/_doxybook/Classes/structlava_1_1mouse__active__event.md) const  & | **[ref](/_doxybook/Classes/structlava_1_1mouse__active__event.md#using-ref)** <br>Reference to mouse active event.  |
| using std::function< bool([ref](/_doxybook/Classes/structlava_1_1mouse__active__event.md#using-ref))> | **[func](/_doxybook/Classes/structlava_1_1mouse__active__event.md#using-func)** <br>Mouse active event function.  |
| using std::map< [id](/_doxybook/Classes/structlava_1_1id.md), [func](/_doxybook/Classes/structlava_1_1mouse__active__event.md#using-func) > | **[listeners](/_doxybook/Classes/structlava_1_1mouse__active__event.md#using-listeners)** <br>List of mouse active event listeners.  |
| using std::vector< [mouse_active_event](/_doxybook/Classes/structlava_1_1mouse__active__event.md) > | **[list](/_doxybook/Classes/structlava_1_1mouse__active__event.md#using-list)** <br>List of mouse active events.  |

## Public Attributes

|                | Name           |
| -------------- | -------------- |
| [id](/_doxybook/Classes/structlava_1_1id.md) | **[sender](/_doxybook/Classes/structlava_1_1mouse__active__event.md#variable-sender)** <br>Sender id.  |
| bool | **[active](/_doxybook/Classes/structlava_1_1mouse__active__event.md#variable-active)** <br>Active state.  |

## Public Types Documentation

### using ref

```cpp
using lava::mouse_active_event::ref =  mouse_active_event const&;
```

Reference to mouse active event. 

### using func

```cpp
using lava::mouse_active_event::func =  std::function<bool(ref)>;
```

Mouse active event function. 

### using listeners

```cpp
using lava::mouse_active_event::listeners =  std::map<id, func>;
```

List of mouse active event listeners. 

### using list

```cpp
using lava::mouse_active_event::list =  std::vector<mouse_active_event>;
```

List of mouse active events. 

## Public Attributes Documentation

### variable sender

```cpp
id sender;
```

Sender id. 

### variable active

```cpp
bool active = false;
```

Active state. 

-------------------------------

Updated on 2026-02-01 at 18:13:39 +0000