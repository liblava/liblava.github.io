---
title: lava::input
summary: Input handling. 

---

# lava::input



Input handling. 


`#include <input.hpp>`

## Public Types

|                | Name           |
| -------------- | -------------- |
| using [input](/_doxybook/Classes/structlava_1_1input.md) * | **[ptr](/_doxybook/Classes/structlava_1_1input.md#using-ptr)** <br>Pointer to input.  |

## Public Functions

|                | Name           |
| -------------- | -------------- |
| void | **[handle_events](/_doxybook/Classes/structlava_1_1input.md#function-handle-events)**()<br>Handle events.  |
| void | **[add](/_doxybook/Classes/structlava_1_1input.md#function-add)**([input_callback::cptr](/_doxybook/Classes/structlava_1_1input__callback.md#using-cptr) callback)<br>Add callback to the input handling.  |
| void | **[remove](/_doxybook/Classes/structlava_1_1input.md#function-remove)**([input_callback::cptr](/_doxybook/Classes/structlava_1_1input__callback.md#using-cptr) callback)<br>Remove callback from the input handling.  |
| [mouse_position_ref](/_doxybook/Namespaces/namespacelava.md#using-mouse-position-ref) | **[get_mouse_position](/_doxybook/Classes/structlava_1_1input.md#function-get-mouse-position)**() const<br>Get the mouse position.  |
| void | **[set_mouse_position](/_doxybook/Classes/structlava_1_1input.md#function-set-mouse-position)**([mouse_position_ref](/_doxybook/Namespaces/namespacelava.md#using-mouse-position-ref) position)<br>Set the mouse position.  |

## Public Attributes

|                | Name           |
| -------------- | -------------- |
| [input_key_events](/_doxybook/Namespaces/namespacelava.md#using-input-key-events) | **[key](/_doxybook/Classes/structlava_1_1input.md#variable-key)** <br>List of key events.  |
| [input_scroll_events](/_doxybook/Namespaces/namespacelava.md#using-input-scroll-events) | **[scroll](/_doxybook/Classes/structlava_1_1input.md#variable-scroll)** <br>List of scroll events.  |
| [input_mouse_move_events](/_doxybook/Namespaces/namespacelava.md#using-input-mouse-move-events) | **[mouse_move](/_doxybook/Classes/structlava_1_1input.md#variable-mouse-move)** <br>List of mouse move events.  |
| [input_mouse_button_events](/_doxybook/Namespaces/namespacelava.md#using-input-mouse-button-events) | **[mouse_button](/_doxybook/Classes/structlava_1_1input.md#variable-mouse-button)** <br>List of mouse button events.  |
| [input_mouse_active_events](/_doxybook/Namespaces/namespacelava.md#using-input-mouse-active-events) | **[mouse_active](/_doxybook/Classes/structlava_1_1input.md#variable-mouse-active)** <br>List of mouse active events.  |
| [input_path_drop_events](/_doxybook/Namespaces/namespacelava.md#using-input-path-drop-events) | **[path_drop](/_doxybook/Classes/structlava_1_1input.md#variable-path-drop)** <br>List of path drop events.  |

## Public Types Documentation

### using ptr

```cpp
using lava::input::ptr =  input*;
```

Pointer to input. 

## Public Functions Documentation

### function handle_events

```cpp
void handle_events()
```

Handle events. 

### function add

```cpp
inline void add(
    input_callback::cptr callback
)
```

Add callback to the input handling. 

**Parameters**: 

  * **callback** Callback to add 


### function remove

```cpp
inline void remove(
    input_callback::cptr callback
)
```

Remove callback from the input handling. 

**Parameters**: 

  * **callback** Callback to remove 


### function get_mouse_position

```cpp
inline mouse_position_ref get_mouse_position() const
```

Get the mouse position. 

**Return**: [mouse_position_ref](/_doxybook/Namespaces/namespacelava.md#using-mouse-position-ref) Current mouse position 

### function set_mouse_position

```cpp
inline void set_mouse_position(
    mouse_position_ref position
)
```

Set the mouse position. 

**Parameters**: 

  * **position** Current mouse position 


## Public Attributes Documentation

### variable key

```cpp
input_key_events key;
```

List of key events. 

### variable scroll

```cpp
input_scroll_events scroll;
```

List of scroll events. 

### variable mouse_move

```cpp
input_mouse_move_events mouse_move;
```

List of mouse move events. 

### variable mouse_button

```cpp
input_mouse_button_events mouse_button;
```

List of mouse button events. 

### variable mouse_active

```cpp
input_mouse_active_events mouse_active;
```

List of mouse active events. 

### variable path_drop

```cpp
input_path_drop_events path_drop;
```

List of path drop events. 

-------------------------------

Updated on 2026-02-01 at 18:13:39 +0000