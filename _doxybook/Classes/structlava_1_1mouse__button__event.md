---
title: lava::mouse_button_event
summary: Mouse button event. 

---

# lava::mouse_button_event



Mouse button event. 


`#include <input.hpp>`

## Public Types

|                | Name           |
| -------------- | -------------- |
| using [mouse_button_event](/_doxybook/Classes/structlava_1_1mouse__button__event.md) const  & | **[ref](/_doxybook/Classes/structlava_1_1mouse__button__event.md#using-ref)** <br>Reference to mouse button event.  |
| using std::function< bool([ref](/_doxybook/Classes/structlava_1_1mouse__button__event.md#using-ref))> | **[func](/_doxybook/Classes/structlava_1_1mouse__button__event.md#using-func)** <br>Mouse button event function.  |
| using std::map< [id](/_doxybook/Classes/structlava_1_1id.md), [func](/_doxybook/Classes/structlava_1_1mouse__button__event.md#using-func) > | **[listeners](/_doxybook/Classes/structlava_1_1mouse__button__event.md#using-listeners)** <br>List of mouse button event listeners.  |
| using std::vector< [mouse_button_event](/_doxybook/Classes/structlava_1_1mouse__button__event.md) > | **[list](/_doxybook/Classes/structlava_1_1mouse__button__event.md#using-list)** <br>List of mouse button events.  |

## Public Functions

|                | Name           |
| -------------- | -------------- |
| bool | **[pressed](/_doxybook/Classes/structlava_1_1mouse__button__event.md#function-pressed)**([mouse_button_ref](/_doxybook/Namespaces/namespacelava.md#using-mouse-button-ref) b) const<br>Check if mouse button is pressed.  |
| bool | **[released](/_doxybook/Classes/structlava_1_1mouse__button__event.md#function-released)**([mouse_button_ref](/_doxybook/Namespaces/namespacelava.md#using-mouse-button-ref) b) const<br>Check if mouse button is released.  |

## Public Attributes

|                | Name           |
| -------------- | -------------- |
| [id](/_doxybook/Classes/structlava_1_1id.md) | **[sender](/_doxybook/Classes/structlava_1_1mouse__button__event.md#variable-sender)** <br>Sender id.  |
| [mouse_button](/_doxybook/Namespaces/namespacelava.md#enum-mouse-button) | **[button](/_doxybook/Classes/structlava_1_1mouse__button__event.md#variable-button)** <br>Input mouse button.  |
| [lava::action](/_doxybook/Namespaces/namespacelava.md#enum-action) | **[action](/_doxybook/Classes/structlava_1_1mouse__button__event.md#variable-action)** <br>Input action.  |
| [lava::mod](/_doxybook/Namespaces/namespacelava.md#enum-mod) | **[mod](/_doxybook/Classes/structlava_1_1mouse__button__event.md#variable-mod)** <br>Input mod.  |

## Public Types Documentation

### using ref

```cpp
using lava::mouse_button_event::ref =  mouse_button_event const&;
```

Reference to mouse button event. 

### using func

```cpp
using lava::mouse_button_event::func =  std::function<bool(ref)>;
```

Mouse button event function. 

### using listeners

```cpp
using lava::mouse_button_event::listeners =  std::map<id, func>;
```

List of mouse button event listeners. 

### using list

```cpp
using lava::mouse_button_event::list =  std::vector<mouse_button_event>;
```

List of mouse button events. 

## Public Functions Documentation

### function pressed

```cpp
inline bool pressed(
    mouse_button_ref b
) const
```

Check if mouse button is pressed. 

**Parameters**: 

  * **b** Mouse button to check 


**Return**: Mouse button is pressed or not 

### function released

```cpp
inline bool released(
    mouse_button_ref b
) const
```

Check if mouse button is released. 

**Parameters**: 

  * **b** Mouse button to check 


**Return**: Mouse button is released or not 

## Public Attributes Documentation

### variable sender

```cpp
id sender;
```

Sender id. 

### variable button

```cpp
mouse_button button;
```

Input mouse button. 

### variable action

```cpp
lava::action action;
```

Input action. 

### variable mod

```cpp
lava::mod mod;
```

Input mod. 

-------------------------------

Updated on 2026-02-01 at 18:13:39 +0000