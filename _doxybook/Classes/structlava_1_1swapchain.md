---
title: lava::swapchain
summary: Swaphchain. 

---

# lava::swapchain



Swaphchain. 


`#include <swapchain.hpp>`

Inherits from [lava::entity](/_doxybook/Classes/structlava_1_1entity.md), [lava::no_copy_no_move](/_doxybook/Classes/structlava_1_1no__copy__no__move.md), [lava::interface](/_doxybook/Classes/structlava_1_1interface.md)

## Public Classes

|                | Name           |
| -------------- | -------------- |
| struct | **[callback](/_doxybook/Classes/structlava_1_1swapchain_1_1callback.md)** <br>Swapchain callback.  |

## Public Functions

|                | Name           |
| -------------- | -------------- |
| bool | **[create](/_doxybook/Classes/structlava_1_1swapchain.md#function-create)**([device::ptr](/_doxybook/Classes/structlava_1_1device.md#using-ptr) device, VkSurfaceKHR surface, VkSurfaceFormatKHR format, [uv2](/_doxybook/Namespaces/namespacelava.md#using-uv2) size, bool v_sync =false, bool triple_buffer =true)<br>Create a new swapchain.  |
| void | **[destroy](/_doxybook/Classes/structlava_1_1swapchain.md#function-destroy)**()<br>Destroy the swapchain.  |
| bool | **[resize](/_doxybook/Classes/structlava_1_1swapchain.md#function-resize)**([uv2](/_doxybook/Namespaces/namespacelava.md#using-uv2) new_size)<br>Resize the swapchain.  |
| void | **[request_reload](/_doxybook/Classes/structlava_1_1swapchain.md#function-request-reload)**()<br>Request a reload of the swapchain.  |
| bool | **[reload_request](/_doxybook/Classes/structlava_1_1swapchain.md#function-reload-request)**() const<br>Check if reload of the swapchain is requested.  |
| [device::ptr](/_doxybook/Classes/structlava_1_1device.md#using-ptr) | **[get_device](/_doxybook/Classes/structlava_1_1swapchain.md#function-get-device)**()<br>Get the device.  |
| [uv2](/_doxybook/Namespaces/namespacelava.md#using-uv2) | **[get_size](/_doxybook/Classes/structlava_1_1swapchain.md#function-get-size)**() const<br>Get the size of the swapchain.  |
| VkFormat | **[get_format](/_doxybook/Classes/structlava_1_1swapchain.md#function-get-format)**() const<br>Get the format of the swapchain.  |
| VkColorSpaceKHR | **[get_color_space](/_doxybook/Classes/structlava_1_1swapchain.md#function-get-color-space)**() const<br>Get the color space of the swapchain.  |
| VkSwapchainKHR | **[get](/_doxybook/Classes/structlava_1_1swapchain.md#function-get)**() const<br>Get the swapchain.  |
| [ui32](/_doxybook/Namespaces/namespacelava.md#using-ui32) | **[get_backbuffer_count](/_doxybook/Classes/structlava_1_1swapchain.md#function-get-backbuffer-count)**() const<br>Get the backbuffer count.  |
| [image::s_list](/_doxybook/Classes/structlava_1_1image.md#using-s-list) const & | **[get_backbuffers](/_doxybook/Classes/structlava_1_1swapchain.md#function-get-backbuffers)**() const<br>Get the backbuffers.  |
| void | **[add_callback](/_doxybook/Classes/structlava_1_1swapchain.md#function-add-callback)**([callback](/_doxybook/Classes/structlava_1_1swapchain_1_1callback.md) * cb)<br>Add callback to swapchain.  |
| void | **[remove_callback](/_doxybook/Classes/structlava_1_1swapchain.md#function-remove-callback)**([callback](/_doxybook/Classes/structlava_1_1swapchain_1_1callback.md) * cb)<br>Remove callback from swapchain.  |
| bool | **[v_sync](/_doxybook/Classes/structlava_1_1swapchain.md#function-v-sync)**() const<br>Check if V-Sync is enabled.  |
| bool | **[triple_buffer](/_doxybook/Classes/structlava_1_1swapchain.md#function-triple-buffer)**() const<br>Check if VK_PRESENT_MODE_MAILBOX_KHR is preferred over VK_PRESENT_MODE_IMMEDIATE_KHR.  |
| bool | **[surface_supported](/_doxybook/Classes/structlava_1_1swapchain.md#function-surface-supported)**([index](/_doxybook/Namespaces/namespacelava.md#using-index) queue_family) const<br>Check if surface is supported by queue family index.  |

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


## Public Functions Documentation

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

Create a new swapchain. 

**Parameters**: 

  * **device** Vulkan device 
  * **surface** Vulkan surface 
  * **format** Surface format 
  * **size** Size of swapchain 
  * **v_sync** V-Sync enabled 
  * **triple_buffer** VK_PRESENT_MODE_MAILBOX_KHR preferred over VK_PRESENT_MODE_IMMEDIATE_KHR 


**Return**: Create was successful or failed 

### function destroy

```cpp
void destroy()
```

Destroy the swapchain. 

### function resize

```cpp
bool resize(
    uv2 new_size
)
```

Resize the swapchain. 

**Parameters**: 

  * **new_size** New size of swapchain 


**Return**: Resize was successful or failed 

### function request_reload

```cpp
inline void request_reload()
```

Request a reload of the swapchain. 

### function reload_request

```cpp
inline bool reload_request() const
```

Check if reload of the swapchain is requested. 

**Return**: Reload is requested or not 

### function get_device

```cpp
inline device::ptr get_device()
```

Get the device. 

**Return**: [device::ptr](/_doxybook/Classes/structlava_1_1device.md#using-ptr) Vulkan device 

### function get_size

```cpp
inline uv2 get_size() const
```

Get the size of the swapchain. 

**Return**: [uv2](/_doxybook/Namespaces/namespacelava.md#using-uv2) Swapchain size 

### function get_format

```cpp
inline VkFormat get_format() const
```

Get the format of the swapchain. 

**Return**: VkFormat Swapchain format 

### function get_color_space

```cpp
inline VkColorSpaceKHR get_color_space() const
```

Get the color space of the swapchain. 

**Return**: VkColorSpaceKHR Swapchain color space 

### function get

```cpp
inline VkSwapchainKHR get() const
```

Get the swapchain. 

**Return**: VkSwapchainKHR Vulkan swapchain 

### function get_backbuffer_count

```cpp
inline ui32 get_backbuffer_count() const
```

Get the backbuffer count. 

**Return**: [ui32](/_doxybook/Namespaces/namespacelava.md#using-ui32) Number of backbuffers 

### function get_backbuffers

```cpp
inline image::s_list const & get_backbuffers() const
```

Get the backbuffers. 

**Return**: [image::s_list](/_doxybook/Classes/structlava_1_1image.md#using-s-list) const& List of backbuffer images 

### function add_callback

```cpp
void add_callback(
    callback * cb
)
```

Add callback to swapchain. 

**Parameters**: 

  * **cb** Callback to add 


### function remove_callback

```cpp
void remove_callback(
    callback * cb
)
```

Remove callback from swapchain. 

**Parameters**: 

  * **cb** Callback to remove 


### function v_sync

```cpp
inline bool v_sync() const
```

Check if V-Sync is enabled. 

**Return**: V-Sync is active or not 

### function triple_buffer

```cpp
inline bool triple_buffer() const
```

Check if VK_PRESENT_MODE_MAILBOX_KHR is preferred over VK_PRESENT_MODE_IMMEDIATE_KHR. 

**Return**: VK_PRESENT_MODE_MAILBOX_KHR preferred over VK_PRESENT_MODE_IMMEDIATE_KHR or not 

### function surface_supported

```cpp
bool surface_supported(
    index queue_family
) const
```

Check if surface is supported by queue family index. 

**Parameters**: 

  * **queue_family** Queue family index 


**Return**: Surface is supported by queue family or not 

-------------------------------

Updated on 2026-02-01 at 18:13:39 +0000