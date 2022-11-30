---
title: lava::renderer
summary: Plain renderer. 

---

# lava::renderer



Plain renderer. 


`#include <renderer.hpp>`

Inherits from [lava::entity](/_doxybook/Classes/structlava_1_1entity.md), [lava::no_copy_no_move](/_doxybook/Classes/structlava_1_1no__copy__no__move.md), [lava::interface](/_doxybook/Classes/structlava_1_1interface.md)

## Public Types

|                | Name           |
| -------------- | -------------- |
| using std::function< void()> | **[destroy_func](/_doxybook/Classes/structlava_1_1renderer.md#using-destroy-func)** <br>Destroy function.  |

## Public Functions

|                | Name           |
| -------------- | -------------- |
| bool | **[create](/_doxybook/Classes/structlava_1_1renderer.md#function-create)**([swapchain](/_doxybook/Classes/structlava_1_1swapchain.md) * target)<br>Create a new renderer.  |
| void | **[destroy](/_doxybook/Classes/structlava_1_1renderer.md#function-destroy)**()<br>Destroy the renderer.  |
| [optional_index](/_doxybook/Namespaces/namespacelava.md#using-optional-index) | **[begin_frame](/_doxybook/Classes/structlava_1_1renderer.md#function-begin-frame)**()<br>Begin to render a frame.  |
| bool | **[end_frame](/_doxybook/Classes/structlava_1_1renderer.md#function-end-frame)**([VkCommandBuffers](/_doxybook/Namespaces/namespacelava.md#using-vkcommandbuffers) const & cmd_buffers)<br>End of frame rendering.  |
| bool | **[frame](/_doxybook/Classes/structlava_1_1renderer.md#function-frame)**([VkCommandBuffers](/_doxybook/Namespaces/namespacelava.md#using-vkcommandbuffers) const & cmd_buffers)<br>Render a frame.  |
| [index](/_doxybook/Namespaces/namespacelava.md#using-index) | **[get_frame](/_doxybook/Classes/structlava_1_1renderer.md#function-get-frame)**() const<br>Get the current frame index.  |
| [device_p](/_doxybook/Namespaces/namespacelava.md#using-device-p) | **[get_device](/_doxybook/Classes/structlava_1_1renderer.md#function-get-device)**()<br>Get the device.  |

## Public Attributes

|                | Name           |
| -------------- | -------------- |
| [destroy_func](/_doxybook/Classes/structlava_1_1renderer.md#using-destroy-func) | **[on_destroy](/_doxybook/Classes/structlava_1_1renderer.md#variable-on-destroy)** <br>Called on renderer destroy.  |
| bool | **[active](/_doxybook/Classes/structlava_1_1renderer.md#variable-active)** <br>Active state.  |

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

### using destroy_func

```cpp
using lava::renderer::destroy_func =  std::function<void()>;
```

Destroy function. 

## Public Functions Documentation

### function create

```cpp
bool create(
    swapchain * target
)
```

Create a new renderer. 

**Parameters**: 

  * **target** Swapchain target 


**Return**: Create was successful or failed 

### function destroy

```cpp
void destroy()
```

Destroy the renderer. 

### function begin_frame

```cpp
optional_index begin_frame()
```

Begin to render a frame. 

**Return**: optional_index Frame index 

### function end_frame

```cpp
bool end_frame(
    VkCommandBuffers const & cmd_buffers
)
```

End of frame rendering. 

**Parameters**: 

  * **cmd_buffers** List of command buffers 


**Return**: End was successful or failed 

### function frame

```cpp
inline bool frame(
    VkCommandBuffers const & cmd_buffers
)
```

Render a frame. 

**Parameters**: 

  * **cmd_buffers** List of command buffers 


**Return**: Render was successful or failed 

### function get_frame

```cpp
inline index get_frame() const
```

Get the current frame index. 

**Return**: index Frame index 

### function get_device

```cpp
inline device_p get_device()
```

Get the device. 

**Return**: device_p Vulkan device 

## Public Attributes Documentation

### variable on_destroy

```cpp
destroy_func on_destroy;
```

Called on renderer destroy. 

### variable active

```cpp
bool active = true;
```

Active state. 

-------------------------------

Updated on 2022-11-30 at 01:16:04 +0000