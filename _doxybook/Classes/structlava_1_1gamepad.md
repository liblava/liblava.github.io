---
title: lava::gamepad
summary: Gamepad. 

---

# lava::gamepad



Gamepad. 


`#include <gamepad.hpp>`

## Public Types

|                | Name           |
| -------------- | -------------- |
| using std::vector< [gamepad](/_doxybook/Classes/structlava_1_1gamepad.md) > | **[list](/_doxybook/Classes/structlava_1_1gamepad.md#using-list)** <br>List of gamepads.  |
| using [gamepad](/_doxybook/Classes/structlava_1_1gamepad.md) const  & | **[ref](/_doxybook/Classes/structlava_1_1gamepad.md#using-ref)** <br>Reference to gamepad.  |

## Public Functions

|                | Name           |
| -------------- | -------------- |
| | **[gamepad](/_doxybook/Classes/structlava_1_1gamepad.md#function-gamepad)**([gamepad_id_ref](/_doxybook/Namespaces/namespacelava.md#using-gamepad-id-ref) pad_id =gamepad_id::_1)<br>Construct a new gamepad.  |
| bool | **[ready](/_doxybook/Classes/structlava_1_1gamepad.md#function-ready)**() const<br>Check if gamepad is active.  |
| bool | **[update](/_doxybook/Classes/structlava_1_1gamepad.md#function-update)**()<br>Update gamepad.  |
| bool | **[pressed](/_doxybook/Classes/structlava_1_1gamepad.md#function-pressed)**([gamepad_button_ref](/_doxybook/Namespaces/namespacelava.md#using-gamepad-button-ref) button) const<br>Check if gamepad button is pressed.  |
| [r32](/_doxybook/Namespaces/namespacelava.md#using-r32) | **[value](/_doxybook/Classes/structlava_1_1gamepad.md#function-value)**([gamepad_axis_ref](/_doxybook/Namespaces/namespacelava.md#using-gamepad-axis-ref) axis) const<br>Get value of axis.  |
| [gamepad_id_ref](/_doxybook/Namespaces/namespacelava.md#using-gamepad-id-ref) | **[get_pad_id](/_doxybook/Classes/structlava_1_1gamepad.md#function-get-pad-id)**() const<br>Get the gamepad id.  |
| [ui32](/_doxybook/Namespaces/namespacelava.md#using-ui32) | **[get_id](/_doxybook/Classes/structlava_1_1gamepad.md#function-get-id)**() const<br>Get the gamepad id as integer.  |
| [name](/_doxybook/Namespaces/namespacelava.md#using-name) | **[get_name](/_doxybook/Classes/structlava_1_1gamepad.md#function-get-name)**() const<br>Get the name.  |

## Public Types Documentation

### using list

```cpp
using lava::gamepad::list =  std::vector<gamepad>;
```

List of gamepads. 

### using ref

```cpp
using lava::gamepad::ref =  gamepad const&;
```

Reference to gamepad. 

## Public Functions Documentation

### function gamepad

```cpp
explicit gamepad(
    gamepad_id_ref pad_id =gamepad_id::_1
)
```

Construct a new gamepad. 

**Parameters**: 

  * **pad_id** Gamepad id 


### function ready

```cpp
bool ready() const
```

Check if gamepad is active. 

**Return**: Gamepad is active or not 

### function update

```cpp
bool update()
```

Update gamepad. 

**Return**: Update was successful or failed 

### function pressed

```cpp
inline bool pressed(
    gamepad_button_ref button
) const
```

Check if gamepad button is pressed. 

**Parameters**: 

  * **button** Gamepad button to check 


**Return**: Button is pressed or not 

### function value

```cpp
inline r32 value(
    gamepad_axis_ref axis
) const
```

Get value of axis. 

**Parameters**: 

  * **axis** Target axis 


**Return**: [r32](/_doxybook/Namespaces/namespacelava.md#using-r32) Axis value 

### function get_pad_id

```cpp
inline gamepad_id_ref get_pad_id() const
```

Get the gamepad id. 

**Return**: [gamepad_id_ref](/_doxybook/Namespaces/namespacelava.md#using-gamepad-id-ref) Gamepad id 

### function get_id

```cpp
inline ui32 get_id() const
```

Get the gamepad id as integer. 

**Return**: [ui32](/_doxybook/Namespaces/namespacelava.md#using-ui32) Integer gamepad id 

### function get_name

```cpp
name get_name() const
```

Get the name. 

**Return**: name Name of gamepad 

-------------------------------

Updated on 2026-02-01 at 18:13:39 +0000