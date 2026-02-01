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
| using [renderer](/_doxybook/Classes/structlava_1_1renderer.md) * | **[ptr](/_doxybook/Classes/structlava_1_1renderer.md#using-ptr)** <br>Pointer to renderer.  |
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
| [device::ptr](/_doxybook/Classes/structlava_1_1device.md#using-ptr) | **[get_device](/_doxybook/Classes/structlava_1_1renderer.md#function-get-device)**()<br>Get the device.  |

## Public Attributes

|                | Name           |
| -------------- | -------------- |
| [VkSemaphores](/_doxybook/Namespaces/namespacelava.md#using-vksemaphores) | **[user_frame_wait_semaphores](/_doxybook/Classes/structlava_1_1renderer.md#variable-user-frame-wait-semaphores)** <br>The frame waits additionally for these semaphores (Usefully for additional CommandBuffers)  |
| [VkPipelineStageFlagsList](/_doxybook/Namespaces/namespacelava.md#using-vkpipelinestageflagslist) | **[user_frame_wait_stages](/_doxybook/Classes/structlava_1_1renderer.md#variable-user-frame-wait-stages)** <br>To user_frame_wait_semaphores corresponding pipeline wait stages.  |
| [VkSemaphores](/_doxybook/Namespaces/namespacelava.md#using-vksemaphores) | **[user_frame_signal_semaphores](/_doxybook/Classes/structlava_1_1renderer.md#variable-user-frame-signal-semaphores)** <br>The frame additionally signals these semaphores (Usefully for additional CommandBuffers)  |
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

### using ptr

```cpp
using lava::renderer::ptr =  renderer*;
```

Pointer to renderer. 

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

**Return**: [optional_index](/_doxybook/Namespaces/namespacelava.md#using-optional-index) Frame index 

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
inline device::ptr get_device()
```

Get the device. 

**Return**: [device::ptr](/_doxybook/Classes/structlava_1_1device.md#using-ptr) Vulkan device 

## Public Attributes Documentation

### variable user_frame_wait_semaphores

```cpp
VkSemaphores user_frame_wait_semaphores;
```

The frame waits additionally for these semaphores (Usefully for additional CommandBuffers) 

### variable user_frame_wait_stages

```cpp
VkPipelineStageFlagsList user_frame_wait_stages;
```

To user_frame_wait_semaphores corresponding pipeline wait stages. 

### variable user_frame_signal_semaphores

```cpp
VkSemaphores user_frame_signal_semaphores;
```

The frame additionally signals these semaphores (Usefully for additional CommandBuffers) 

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

Updated on 2026-02-01 at 18:13:39 +0000