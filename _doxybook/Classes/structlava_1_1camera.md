---
title: lava::camera
summary: First Person / Look At camera. 

---

# lava::camera



First Person / Look At camera. 


`#include <camera.hpp>`

Inherits from [lava::entity](/_doxybook/Classes/structlava_1_1entity.md), [lava::no_copy_no_move](/_doxybook/Classes/structlava_1_1no__copy__no__move.md), [lava::interface](/_doxybook/Classes/structlava_1_1interface.md)

## Public Types

|                | Name           |
| -------------- | -------------- |
| enum class [index](/_doxybook/Namespaces/namespacelava.md#using-index) | **[mode](/_doxybook/Classes/structlava_1_1camera.md#enum-mode)** { first_person = 0, look_at}<br>Camera modes.  |
| using [camera](/_doxybook/Classes/structlava_1_1camera.md) * | **[ptr](/_doxybook/Classes/structlava_1_1camera.md#using-ptr)** <br>Pointer to camera.  |
| using std::shared_ptr< [camera](/_doxybook/Classes/structlava_1_1camera.md) > | **[s_ptr](/_doxybook/Classes/structlava_1_1camera.md#using-s-ptr)** <br>Shared pointer to camera.  |
| using std::map< [id](/_doxybook/Classes/structlava_1_1id.md), [s_ptr](/_doxybook/Classes/structlava_1_1camera.md#using-s-ptr) > | **[s_map](/_doxybook/Classes/structlava_1_1camera.md#using-s-map)** <br>Map of cameras.  |
| using std::vector< [s_ptr](/_doxybook/Classes/structlava_1_1camera.md#using-s-ptr) > | **[s_list](/_doxybook/Classes/structlava_1_1camera.md#using-s-list)** <br>List of cameras.  |

## Public Functions

|                | Name           |
| -------------- | -------------- |
| bool | **[create](/_doxybook/Classes/structlava_1_1camera.md#function-create)**([device::ptr](/_doxybook/Classes/structlava_1_1device.md#using-ptr) device)<br>Create a camera.  |
| void | **[destroy](/_doxybook/Classes/structlava_1_1camera.md#function-destroy)**()<br>Destroy the camera.  |
| void | **[update_projection](/_doxybook/Classes/structlava_1_1camera.md#function-update-projection)**()<br>Update the projection.  |
| void | **[update_view](/_doxybook/Classes/structlava_1_1camera.md#function-update-view)**([delta](/_doxybook/Namespaces/namespacelava.md#using-delta) dt, [mouse_position](/_doxybook/Classes/structlava_1_1mouse__position.md) mouse_pos)<br>Update the view with mouse position.  |
| void | **[update_view](/_doxybook/Classes/structlava_1_1camera.md#function-update-view)**([delta](/_doxybook/Namespaces/namespacelava.md#using-delta) dt, [gamepad::ref](/_doxybook/Classes/structlava_1_1gamepad.md#using-ref) pad)<br>Update the view with gamepad.  |
| [mat4](/_doxybook/Namespaces/namespacelava.md#using-mat4) | **[get_view](/_doxybook/Classes/structlava_1_1camera.md#function-get-view)**() const<br>Get the camera's 4x4 view matrix.  |
| [mat4](/_doxybook/Namespaces/namespacelava.md#using-mat4) | **[get_projection](/_doxybook/Classes/structlava_1_1camera.md#function-get-projection)**() const<br>Get the camera's 4x4 projection matrix.  |
| [mat4](/_doxybook/Namespaces/namespacelava.md#using-mat4) | **[calc_view_projection](/_doxybook/Classes/structlava_1_1camera.md#function-calc-view-projection)**() const<br>Calc the camera's combined 4x4 view/projection matrix.  |
| bool | **[handle](/_doxybook/Classes/structlava_1_1camera.md#function-handle)**([key_event::ref](/_doxybook/Classes/structlava_1_1key__event.md#using-ref) event)<br>Handle key event.  |
| bool | **[handle](/_doxybook/Classes/structlava_1_1camera.md#function-handle)**([mouse_button_event::ref](/_doxybook/Classes/structlava_1_1mouse__button__event.md#using-ref) event, [mouse_position](/_doxybook/Classes/structlava_1_1mouse__position.md) mouse_pos)<br>Handle mouse button event.  |
| bool | **[handle](/_doxybook/Classes/structlava_1_1camera.md#function-handle)**([scroll_event::ref](/_doxybook/Classes/structlava_1_1scroll__event.md#using-ref) event)<br>Handle scroll event.  |
| bool | **[valid](/_doxybook/Classes/structlava_1_1camera.md#function-valid)**() const<br>Check if camera is valid.  |
| VkDescriptorBufferInfo const * | **[get_descriptor_info](/_doxybook/Classes/structlava_1_1camera.md#function-get-descriptor-info)**() const<br>Get the descriptor buffer info.  |
| void | **[upload](/_doxybook/Classes/structlava_1_1camera.md#function-upload)**()<br>Upload camera state.  |
| void | **[stop](/_doxybook/Classes/structlava_1_1camera.md#function-stop)**()<br>Stop camera movement.  |
| void | **[reset](/_doxybook/Classes/structlava_1_1camera.md#function-reset)**()<br>Reset camera.  |
| void | **[set_active](/_doxybook/Classes/structlava_1_1camera.md#function-set-active)**(bool value =true)<br>Set camera active.  |
| bool | **[activated](/_doxybook/Classes/structlava_1_1camera.md#function-activated)**() const<br>Check if camera is activated.  |
| bool | **[moving](/_doxybook/Classes/structlava_1_1camera.md#function-moving)**() const<br>Check if camera is moving.  |
| void | **[set_movement_keys](/_doxybook/Classes/structlava_1_1camera.md#function-set-movement-keys)**([keys_ref](/_doxybook/Namespaces/namespacelava.md#using-keys-ref) up, [keys_ref](/_doxybook/Namespaces/namespacelava.md#using-keys-ref) down, [keys_ref](/_doxybook/Namespaces/namespacelava.md#using-keys-ref) left, [keys_ref](/_doxybook/Namespaces/namespacelava.md#using-keys-ref) right)<br>Set keys for moving this camera.  |

## Public Attributes

|                | Name           |
| -------------- | -------------- |
| [v3](/_doxybook/Namespaces/namespacelava.md#using-v3) | **[position](/_doxybook/Classes/structlava_1_1camera.md#variable-position)** <br>Camera position.  |
| [v3](/_doxybook/Namespaces/namespacelava.md#using-v3) | **[rotation](/_doxybook/Classes/structlava_1_1camera.md#variable-rotation)** <br>Camera rotation.  |
| [r32](/_doxybook/Namespaces/namespacelava.md#using-r32) | **[rotation_speed](/_doxybook/Classes/structlava_1_1camera.md#variable-rotation-speed)** <br>Camera rotation speed.  |
| [r32](/_doxybook/Namespaces/namespacelava.md#using-r32) | **[movement_speed](/_doxybook/Classes/structlava_1_1camera.md#variable-movement-speed)** <br>Camera movement speed.  |
| [r32](/_doxybook/Namespaces/namespacelava.md#using-r32) | **[zoom_speed](/_doxybook/Classes/structlava_1_1camera.md#variable-zoom-speed)** <br>Camera zoom speed.  |
| [r32](/_doxybook/Namespaces/namespacelava.md#using-r32) | **[fov](/_doxybook/Classes/structlava_1_1camera.md#variable-fov)** <br>Field of view.  |
| [r32](/_doxybook/Namespaces/namespacelava.md#using-r32) | **[z_near](/_doxybook/Classes/structlava_1_1camera.md#variable-z-near)** <br>Distance to near clipping plane along the -Z axis.  |
| [r32](/_doxybook/Namespaces/namespacelava.md#using-r32) | **[z_far](/_doxybook/Classes/structlava_1_1camera.md#variable-z-far)** <br>Distance to far clipping plane along the -Z axis.  |
| [r32](/_doxybook/Namespaces/namespacelava.md#using-r32) | **[aspect_ratio](/_doxybook/Classes/structlava_1_1camera.md#variable-aspect-ratio)** <br>Camera aspect ratio.  |
| [mode](/_doxybook/Classes/structlava_1_1camera.md#enum-mode) | **[mode](/_doxybook/Classes/structlava_1_1camera.md#variable-mode)** <br>Camera mode.  |
| bool | **[lock_z](/_doxybook/Classes/structlava_1_1camera.md#variable-lock-z)** <br>Lock Z axis movement.  |
| bool | **[lock_rotation](/_doxybook/Classes/structlava_1_1camera.md#variable-lock-rotation)** <br>Lock camera rotation.  |

## Additional inherited members

**Public Functions inherited from [lava::entity](/_doxybook/Classes/structlava_1_1entity.md)**

|                | Name           |
| -------------- | -------------- |
| | **[entity](/_doxybook/Classes/structlava_1_1entity.md#function-entity)**()<br>Construct a new entity.  |
| [id::ref](/_doxybook/Classes/structlava_1_1id.md#using-ref) | **[get_id](/_doxybook/Classes/structlava_1_1entity.md#function-get-id)**() const<br>Get the id of entity.  |

**Public Functions inherited from [lava::no_copy_no_move](/_doxybook/Classes/structlava_1_1no__copy__no__move.md)**

|                | Name           |
| -------------- | -------------- |
| | **[no_copy_no_move](/_doxybook/Classes/structlava_1_1no__copy__no__move.md#function-no-copy-no-move)**() =default<br>Construct a new object.  |
| | **[no_copy_no_move](/_doxybook/Classes/structlava_1_1no__copy__no__move.md#function-no-copy-no-move)**([no_copy_no_move](/_doxybook/Classes/structlava_1_1no__copy__no__move.md) const & ) =delete<br>No copy.  |
| void | **[operator=](/_doxybook/Classes/structlava_1_1no__copy__no__move.md#function-operator=)**([no_copy_no_move](/_doxybook/Classes/structlava_1_1no__copy__no__move.md) const & ) =delete<br>No move.  |

**Public Functions inherited from [lava::interface](/_doxybook/Classes/structlava_1_1interface.md)**

|                | Name           |
| -------------- | -------------- |
| virtual | **[~interface](/_doxybook/Classes/structlava_1_1interface.md#function-~interface)**() =default<br>Destroy the interface.  |


## Public Types Documentation

### enum mode

| Enumerator | Value | Description |
| ---------- | ----- | ----------- |
| first_person | 0|   |
| look_at | |   |



Camera modes. 

### using ptr

```cpp
using lava::camera::ptr =  camera*;
```

Pointer to camera. 

### using s_ptr

```cpp
using lava::camera::s_ptr =  std::shared_ptr<camera>;
```

Shared pointer to camera. 

### using s_map

```cpp
using lava::camera::s_map =  std::map<id, s_ptr>;
```

Map of cameras. 

### using s_list

```cpp
using lava::camera::s_list =  std::vector<s_ptr>;
```

List of cameras. 

## Public Functions Documentation

### function create

```cpp
bool create(
    device::ptr device
)
```

Create a camera. 

**Parameters**: 

  * **device** Vulkan device 


**Return**: Create was successful or failed 

### function destroy

```cpp
void destroy()
```

Destroy the camera. 

### function update_projection

```cpp
void update_projection()
```

Update the projection. 

### function update_view

```cpp
void update_view(
    delta dt,
    mouse_position mouse_pos
)
```

Update the view with mouse position. 

**Parameters**: 

  * **dt** Delta time 
  * **mouse_pos** Mouse position 


### function update_view

```cpp
void update_view(
    delta dt,
    gamepad::ref pad
)
```

Update the view with gamepad. 

**Parameters**: 

  * **dt** Delta time 
  * **pad** Gamepad 


### function get_view

```cpp
mat4 get_view() const
```

Get the camera's 4x4 view matrix. 

**Return**: [mat4](/_doxybook/Namespaces/namespacelava.md#using-mat4) View matrix 

### function get_projection

```cpp
mat4 get_projection() const
```

Get the camera's 4x4 projection matrix. 

**Return**: [mat4](/_doxybook/Namespaces/namespacelava.md#using-mat4) Projection matrix 

### function calc_view_projection

```cpp
mat4 calc_view_projection() const
```

Calc the camera's combined 4x4 view/projection matrix. 

**Return**: [mat4](/_doxybook/Namespaces/namespacelava.md#using-mat4) Combined view/projection matrix 

### function handle

```cpp
bool handle(
    key_event::ref event
)
```

Handle key event. 

**Parameters**: 

  * **event** Key event 


**Return**: Event was handled or ignored 

### function handle

```cpp
bool handle(
    mouse_button_event::ref event,
    mouse_position mouse_pos
)
```

Handle mouse button event. 

**Parameters**: 

  * **event** Mouse button event 
  * **mouse_pos** Mouse position 


**Return**: Event was handled or ignored 

### function handle

```cpp
bool handle(
    scroll_event::ref event
)
```

Handle scroll event. 

**Parameters**: 

  * **event** Scroll event 


**Return**: Event was handled or ignored 

### function valid

```cpp
inline bool valid() const
```

Check if camera is valid. 

**Return**: Camera is valid or not 

### function get_descriptor_info

```cpp
inline VkDescriptorBufferInfo const * get_descriptor_info() const
```

Get the descriptor buffer info. 

**Return**: VkDescriptorBufferInfo const* Descriptor buffer info 

### function upload

```cpp
void upload()
```

Upload camera state. 

### function stop

```cpp
void stop()
```

Stop camera movement. 

### function reset

```cpp
void reset()
```

Reset camera. 

### function set_active

```cpp
inline void set_active(
    bool value =true
)
```

Set camera active. 

**Parameters**: 

  * **value** Active state 


### function activated

```cpp
inline bool activated() const
```

Check if camera is activated. 

**Return**: Camera is active or not 

### function moving

```cpp
inline bool moving() const
```

Check if camera is moving. 

**Return**: Camera is moving or does not move 

### function set_movement_keys

```cpp
inline void set_movement_keys(
    keys_ref up,
    keys_ref down,
    keys_ref left,
    keys_ref right
)
```

Set keys for moving this camera. 

**Parameters**: 

  * **up** Up inputs 
  * **down** Down inputs 
  * **left** Left inputs 
  * **right** Right inputs 


## Public Attributes Documentation

### variable position

```cpp
v3 position = v3(0.f);
```

Camera position. 

### variable rotation

```cpp
v3 rotation = v3(0.f);
```

Camera rotation. 

### variable rotation_speed

```cpp
r32 rotation_speed = 20.f;
```

Camera rotation speed. 

### variable movement_speed

```cpp
r32 movement_speed = 1.f;
```

Camera movement speed. 

### variable zoom_speed

```cpp
r32 zoom_speed = 20.f;
```

Camera zoom speed. 

### variable fov

```cpp
r32 fov = 60.f;
```

Field of view. 

### variable z_near

```cpp
r32 z_near = 0.1f;
```

Distance to near clipping plane along the -Z axis. 

### variable z_far

```cpp
r32 z_far = 256.f;
```

Distance to far clipping plane along the -Z axis. 

### variable aspect_ratio

```cpp
r32 aspect_ratio = 1.77f;
```

Camera aspect ratio. 

### variable mode

```cpp
mode mode = mode::first_person;
```

Camera mode. 

### variable lock_z

```cpp
bool lock_z = false;
```

Lock Z axis movement. 

### variable lock_rotation

```cpp
bool lock_rotation = false;
```

Lock camera rotation. 

-------------------------------

Updated on 2026-02-01 at 18:13:39 +0000