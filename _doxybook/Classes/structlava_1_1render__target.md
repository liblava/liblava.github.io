---
title: lava::render_target
summary: Render target. 

---

# lava::render_target



Render target. 


`#include <render_target.hpp>`

Inherits from [lava::entity](/_doxybook/Classes/structlava_1_1entity.md), [lava::no_copy_no_move](/_doxybook/Classes/structlava_1_1no__copy__no__move.md), [lava::interface](/_doxybook/Classes/structlava_1_1interface.md)

## Public Types

|                | Name           |
| -------------- | -------------- |
| using std::shared_ptr< [render_target](/_doxybook/Classes/structlava_1_1render__target.md) > | **[s_ptr](/_doxybook/Classes/structlava_1_1render__target.md#using-s-ptr)** <br>Shared pointer to render target.  |
| using std::function< bool()> | **[swapchain_start_func](/_doxybook/Classes/structlava_1_1render__target.md#using-swapchain-start-func)** <br>Swapchain start function.  |
| using std::function< void()> | **[swapchain_stop_func](/_doxybook/Classes/structlava_1_1render__target.md#using-swapchain-stop-func)** <br>Swapchain stop function.  |
| using std::function< [VkAttachments](/_doxybook/Namespaces/namespacelava.md#using-vkattachments)()> | **[create_attachments_func](/_doxybook/Classes/structlava_1_1render__target.md#using-create-attachments-func)** <br>Create attachments function.  |
| using std::function< void()> | **[destroy_attachments_func](/_doxybook/Classes/structlava_1_1render__target.md#using-destroy-attachments-func)** <br>Destroy attachments function.  |

## Public Functions

|                | Name           |
| -------------- | -------------- |
| [s_ptr](/_doxybook/Classes/structlava_1_1render__target.md#using-s-ptr) | **[make](/_doxybook/Classes/structlava_1_1render__target.md#function-make)**()<br>Make a new render target.  |
| bool | **[create](/_doxybook/Classes/structlava_1_1render__target.md#function-create)**([device::ptr](/_doxybook/Classes/structlava_1_1device.md#using-ptr) device, VkSurfaceKHR surface, VkSurfaceFormatKHR format, [uv2](/_doxybook/Namespaces/namespacelava.md#using-uv2) size, bool v_sync =false, bool triple_buffer =true)<br>Create a new render target.  |
| void | **[destroy](/_doxybook/Classes/structlava_1_1render__target.md#function-destroy)**()<br>Destroy the render target.  |
| [uv2](/_doxybook/Namespaces/namespacelava.md#using-uv2) | **[get_size](/_doxybook/Classes/structlava_1_1render__target.md#function-get-size)**() const<br>Get the size of the render target.  |
| bool | **[resize](/_doxybook/Classes/structlava_1_1render__target.md#function-resize)**([uv2](/_doxybook/Namespaces/namespacelava.md#using-uv2) new_size)<br>Resize the render target.  |
| [ui32](/_doxybook/Namespaces/namespacelava.md#using-ui32) | **[get_frame_count](/_doxybook/Classes/structlava_1_1render__target.md#function-get-frame-count)**() const<br>Get the frame count.  |
| bool | **[reload_request](/_doxybook/Classes/structlava_1_1render__target.md#function-reload-request)**() const<br>Check if render target requests a reload.  |
| void | **[reload](/_doxybook/Classes/structlava_1_1render__target.md#function-reload)**()<br>Reload the render target.  |
| [device::ptr](/_doxybook/Classes/structlava_1_1device.md#using-ptr) | **[get_device](/_doxybook/Classes/structlava_1_1render__target.md#function-get-device)**()<br>Get the device.  |
| [swapchain](/_doxybook/Classes/structlava_1_1swapchain.md) * | **[get_swapchain](/_doxybook/Classes/structlava_1_1render__target.md#function-get-swapchain)**()<br>Get the swapchain.  |
| VkFormat | **[get_format](/_doxybook/Classes/structlava_1_1render__target.md#function-get-format)**() const<br>Get the format.  |
| [image::s_list](/_doxybook/Classes/structlava_1_1image.md#using-s-list) const & | **[get_backbuffers](/_doxybook/Classes/structlava_1_1render__target.md#function-get-backbuffers)**() const<br>Get the backbuffers.  |
| [image::s_ptr](/_doxybook/Classes/structlava_1_1image.md#using-s-ptr) | **[get_backbuffer](/_doxybook/Classes/structlava_1_1render__target.md#function-get-backbuffer)**([index](/_doxybook/Namespaces/namespacelava.md#using-index) index)<br>Get the backbuffer by frame index.  |
| VkImage | **[get_backbuffer_image](/_doxybook/Classes/structlava_1_1render__target.md#function-get-backbuffer-image)**([index](/_doxybook/Namespaces/namespacelava.md#using-index) index)<br>Get the backbuffer image by index.  |
| VkImage | **[get_image](/_doxybook/Classes/structlava_1_1render__target.md#function-get-image)**([index](/_doxybook/Namespaces/namespacelava.md#using-index) index) |
| void | **[add_callback](/_doxybook/Classes/structlava_1_1render__target.md#function-add-callback)**([target_callback::c_ptr](/_doxybook/Classes/structlava_1_1target__callback.md#using-c-ptr) callback)<br>Add callback.  |
| void | **[remove_callback](/_doxybook/Classes/structlava_1_1render__target.md#function-remove-callback)**([target_callback::c_ptr](/_doxybook/Classes/structlava_1_1target__callback.md#using-c-ptr) callback)<br>Remove callback.  |

## Public Attributes

|                | Name           |
| -------------- | -------------- |
| [swapchain_start_func](/_doxybook/Classes/structlava_1_1render__target.md#using-swapchain-start-func) | **[on_swapchain_start](/_doxybook/Classes/structlava_1_1render__target.md#variable-on-swapchain-start)** <br>Called on swapchain start.  |
| [swapchain_stop_func](/_doxybook/Classes/structlava_1_1render__target.md#using-swapchain-stop-func) | **[on_swapchain_stop](/_doxybook/Classes/structlava_1_1render__target.md#variable-on-swapchain-stop)** <br>Called on swapchain stop.  |
| [create_attachments_func](/_doxybook/Classes/structlava_1_1render__target.md#using-create-attachments-func) | **[on_create_attachments](/_doxybook/Classes/structlava_1_1render__target.md#variable-on-create-attachments)** <br>Called on create attachments.  |
| [destroy_attachments_func](/_doxybook/Classes/structlava_1_1render__target.md#using-destroy-attachments-func) | **[on_destroy_attachments](/_doxybook/Classes/structlava_1_1render__target.md#variable-on-destroy-attachments)** <br>Called on destroy attachments.  |

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

### using s_ptr

```cpp
using lava::render_target::s_ptr =  std::shared_ptr<render_target>;
```

Shared pointer to render target. 

### using swapchain_start_func

```cpp
using lava::render_target::swapchain_start_func =  std::function<bool()>;
```

Swapchain start function. 

### using swapchain_stop_func

```cpp
using lava::render_target::swapchain_stop_func =  std::function<void()>;
```

Swapchain stop function. 

### using create_attachments_func

```cpp
using lava::render_target::create_attachments_func =  std::function<VkAttachments()>;
```

Create attachments function. 

### using destroy_attachments_func

```cpp
using lava::render_target::destroy_attachments_func =  std::function<void()>;
```

Destroy attachments function. 

## Public Functions Documentation

### function make

```cpp
static inline s_ptr make()
```

Make a new render target. 

**Return**: [s_ptr](/_doxybook/Classes/structlava_1_1render__target.md#using-s-ptr) Shared pointer to render target 

### function create

```cpp
bool create(
    device::ptr device,
    VkSurfaceKHR surface,
    VkSurfaceFormatKHR format,
    uv2 size,
    bool v_sync =false,
    bool triple_buffer =true
)
```

Create a new render target. 

**Parameters**: 

  * **device** Vulkan device 
  * **surface** Vulkan surface 
  * **format** Surface format 
  * **size** Size of target 
  * **v_sync** V-Sync enabled 
  * **triple_buffer** VK_PRESENT_MODE_MAILBOX_KHR preferred over VK_PRESENT_MODE_IMMEDIATE_KHR 


**Return**: Create was successful or failed 

### function destroy

```cpp
void destroy()
```

Destroy the render target. 

### function get_size

```cpp
inline uv2 get_size() const
```

Get the size of the render target. 

**Return**: [uv2](/_doxybook/Namespaces/namespacelava.md#using-uv2) Size of render target 

### function resize

```cpp
inline bool resize(
    uv2 new_size
)
```

Resize the render target. 

**Parameters**: 

  * **new_size** New render target size 


**Return**: Resize was successful or failed 

### function get_frame_count

```cpp
inline ui32 get_frame_count() const
```

Get the frame count. 

**Return**: [ui32](/_doxybook/Namespaces/namespacelava.md#using-ui32) Number of frames 

### function reload_request

```cpp
inline bool reload_request() const
```

Check if render target requests a reload. 

**Return**: Request reload or not 

### function reload

```cpp
inline void reload()
```

Reload the render target. 

### function get_device

```cpp
inline device::ptr get_device()
```

Get the device. 

**Return**: [device::ptr](/_doxybook/Classes/structlava_1_1device.md#using-ptr) Vulkan device 

### function get_swapchain

```cpp
inline swapchain * get_swapchain()
```

Get the swapchain. 

**Return**: swapchain* Target swapchain 

### function get_format

```cpp
inline VkFormat get_format() const
```

Get the format. 

**Return**: VkFormat Target format 

### function get_backbuffers

```cpp
inline image::s_list const & get_backbuffers() const
```

Get the backbuffers. 

**Return**: [image::s_list](/_doxybook/Classes/structlava_1_1image.md#using-s-list) const& List of backbuffer images 

### function get_backbuffer

```cpp
inline image::s_ptr get_backbuffer(
    index index
)
```

Get the backbuffer by frame index. 

**Parameters**: 

  * **index** Frame index 


**Return**: [image::s_ptr](/_doxybook/Classes/structlava_1_1image.md#using-s-ptr) Backbuffer image 

### function get_backbuffer_image

```cpp
inline VkImage get_backbuffer_image(
    index index
)
```

Get the backbuffer image by index. 

**Parameters**: 

  * **index** Frame index 


**Return**: VkImage Vulkan image 

### function get_image

```cpp
inline VkImage get_image(
    index index
)
```


**See**: [get_backbuffer_image](/_doxybook/Classes/structlava_1_1render__target.md#function-get-backbuffer-image)

### function add_callback

```cpp
inline void add_callback(
    target_callback::c_ptr callback
)
```

Add callback. 

**Parameters**: 

  * **callback** Target callback 


### function remove_callback

```cpp
inline void remove_callback(
    target_callback::c_ptr callback
)
```

Remove callback. 

**Parameters**: 

  * **callback** Target callback 


## Public Attributes Documentation

### variable on_swapchain_start

```cpp
swapchain_start_func on_swapchain_start;
```

Called on swapchain start. 

### variable on_swapchain_stop

```cpp
swapchain_stop_func on_swapchain_stop;
```

Called on swapchain stop. 

### variable on_create_attachments

```cpp
create_attachments_func on_create_attachments;
```

Called on create attachments. 

### variable on_destroy_attachments

```cpp
destroy_attachments_func on_destroy_attachments;
```

Called on destroy attachments. 

-------------------------------

Updated on 2026-02-01 at 18:13:39 +0000