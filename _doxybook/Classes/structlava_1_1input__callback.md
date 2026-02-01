---
title: lava::input_callback
summary: Input callback. 

---

# lava::input_callback



Input callback. 


`#include <input.hpp>`

## Public Types

|                | Name           |
| -------------- | -------------- |
| using [input_callback](/_doxybook/Classes/structlava_1_1input__callback.md) const  * | **[cptr](/_doxybook/Classes/structlava_1_1input__callback.md#using-cptr)** <br>Const pointer to input callback.  |
| using std::vector< [input_callback](/_doxybook/Classes/structlava_1_1input__callback.md) * > | **[list](/_doxybook/Classes/structlava_1_1input__callback.md#using-list)** <br>List of input callbacks.  |
| using std::vector< [cptr](/_doxybook/Classes/structlava_1_1input__callback.md#using-cptr) > | **[clist](/_doxybook/Classes/structlava_1_1input__callback.md#using-clist)** <br>List of const input callbacks.  |
| template <typename T \> <br>using std::function< bool(typename T::ref)> | **[func](/_doxybook/Classes/structlava_1_1input__callback.md#using-func)** <br>Input callback functions.  |

## Public Attributes

|                | Name           |
| -------------- | -------------- |
| [key_event::func](/_doxybook/Classes/structlava_1_1key__event.md#using-func) | **[on_key_event](/_doxybook/Classes/structlava_1_1input__callback.md#variable-on-key-event)** <br>Called on key event.  |
| [scroll_event::func](/_doxybook/Classes/structlava_1_1scroll__event.md#using-func) | **[on_scroll_event](/_doxybook/Classes/structlava_1_1input__callback.md#variable-on-scroll-event)** <br>Called on scroll event.  |
| [mouse_move_event::func](/_doxybook/Classes/structlava_1_1mouse__move__event.md#using-func) | **[on_mouse_move_event](/_doxybook/Classes/structlava_1_1input__callback.md#variable-on-mouse-move-event)** <br>Called on mouse move event.  |
| [mouse_button_event::func](/_doxybook/Classes/structlava_1_1mouse__button__event.md#using-func) | **[on_mouse_button_event](/_doxybook/Classes/structlava_1_1input__callback.md#variable-on-mouse-button-event)** <br>Called on mouse button event.  |
| [mouse_active_event::func](/_doxybook/Classes/structlava_1_1mouse__active__event.md#using-func) | **[on_mouse_active_event](/_doxybook/Classes/structlava_1_1input__callback.md#variable-on-mouse-active-event)** <br>Called on mouse active event.  |
| [path_drop_event::func](/_doxybook/Classes/structlava_1_1path__drop__event.md#using-func) | **[on_path_drop_event](/_doxybook/Classes/structlava_1_1input__callback.md#variable-on-path-drop-event)** <br>Called on path drop event.  |

## Public Types Documentation

### using cptr

```cpp
using lava::input_callback::cptr =  input_callback const*;
```

Const pointer to input callback. 

### using list

```cpp
using lava::input_callback::list =  std::vector<input_callback*>;
```

List of input callbacks. 

### using clist

```cpp
using lava::input_callback::clist =  std::vector<cptr>;
```

List of const input callbacks. 

### using func

```cpp
template <typename T >
using lava::input_callback::func =  std::function<bool(typename T::ref)>;
```

Input callback functions. 

**Template Parameters**: 

  * **T** Type of callback 


## Public Attributes Documentation

### variable on_key_event

```cpp
key_event::func on_key_event;
```

Called on key event. 

### variable on_scroll_event

```cpp
scroll_event::func on_scroll_event;
```

Called on scroll event. 

### variable on_mouse_move_event

```cpp
mouse_move_event::func on_mouse_move_event;
```

Called on mouse move event. 

### variable on_mouse_button_event

```cpp
mouse_button_event::func on_mouse_button_event;
```

Called on mouse button event. 

### variable on_mouse_active_event

```cpp
mouse_active_event::func on_mouse_active_event;
```

Called on mouse active event. 

### variable on_path_drop_event

```cpp
path_drop_event::func on_path_drop_event;
```

Called on path drop event. 

-------------------------------

Updated on 2026-02-01 at 18:13:39 +0000