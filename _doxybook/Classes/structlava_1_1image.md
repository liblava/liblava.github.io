---
title: lava::image
summary: Image. 

---

# lava::image



Image. 


`#include <image.hpp>`

Inherits from [lava::entity](/_doxybook/Classes/structlava_1_1entity.md), [lava::no_copy_no_move](/_doxybook/Classes/structlava_1_1no__copy__no__move.md), [lava::interface](/_doxybook/Classes/structlava_1_1interface.md)

## Public Types

|                | Name           |
| -------------- | -------------- |
| using std::shared_ptr< [image](/_doxybook/Classes/structlava_1_1image.md) > | **[s_ptr](/_doxybook/Classes/structlava_1_1image.md#using-s-ptr)** <br>Shared pointer to image.  |
| using std::map< [id](/_doxybook/Classes/structlava_1_1id.md), [s_ptr](/_doxybook/Classes/structlava_1_1image.md#using-s-ptr) > | **[s_map](/_doxybook/Classes/structlava_1_1image.md#using-s-map)** <br>Map of images.  |
| using std::vector< [s_ptr](/_doxybook/Classes/structlava_1_1image.md#using-s-ptr) > | **[s_list](/_doxybook/Classes/structlava_1_1image.md#using-s-list)** <br>List of images.  |

## Public Functions

|                | Name           |
| -------------- | -------------- |
| [s_ptr](/_doxybook/Classes/structlava_1_1image.md#using-s-ptr) | **[make](/_doxybook/Classes/structlava_1_1image.md#function-make)**(VkFormat format, VkImage vk_image =0)<br>Make a new image.  |
| | **[image](/_doxybook/Classes/structlava_1_1image.md#function-image)**(VkFormat format, VkImage vk_image =0)<br>Construct a new image.  |
| bool | **[create](/_doxybook/Classes/structlava_1_1image.md#function-create)**([device::ptr](/_doxybook/Classes/structlava_1_1device.md#using-ptr) device, [uv2](/_doxybook/Namespaces/namespacelava.md#using-uv2) size, VmaMemoryUsage memory_usage =VMA_MEMORY_USAGE_GPU_ONLY, VmaAllocationCreateFlags allocation_flags =0)<br>Create a new image.  |
| void | **[destroy](/_doxybook/Classes/structlava_1_1image.md#function-destroy)**(bool view_only =false)<br>Destroy the image.  |
| void | **[destroy_view](/_doxybook/Classes/structlava_1_1image.md#function-destroy-view)**()<br>Destroy the image view.  |
| [device::ptr](/_doxybook/Classes/structlava_1_1device.md#using-ptr) | **[get_device](/_doxybook/Classes/structlava_1_1image.md#function-get-device)**()<br>Get the device.  |
| VkFormat | **[get_format](/_doxybook/Classes/structlava_1_1image.md#function-get-format)**() const<br>Get the format of the image.  |
| [uv2](/_doxybook/Namespaces/namespacelava.md#using-uv2) | **[get_size](/_doxybook/Classes/structlava_1_1image.md#function-get-size)**() const<br>Get the size of the image.  |
| [ui32](/_doxybook/Namespaces/namespacelava.md#using-ui32) | **[get_depth](/_doxybook/Classes/structlava_1_1image.md#function-get-depth)**() const<br>Get the depth of the image.  |
| VkImage | **[get](/_doxybook/Classes/structlava_1_1image.md#function-get)**() const<br>Get the image.  |
| VkImageView | **[get_view](/_doxybook/Classes/structlava_1_1image.md#function-get-view)**() const<br>Get the image view.  |
| VkImageCreateInfo const & | **[get_info](/_doxybook/Classes/structlava_1_1image.md#function-get-info)**() const<br>Get the image create information.  |
| VkImageViewCreateInfo const & | **[get_view_info](/_doxybook/Classes/structlava_1_1image.md#function-get-view-info)**() const<br>Get the image view create information.  |
| VkImageSubresourceRange const & | **[get_subresource_range](/_doxybook/Classes/structlava_1_1image.md#function-get-subresource-range)**() const<br>Get the subresource range of the image.  |
| void | **[set_flags](/_doxybook/Classes/structlava_1_1image.md#function-set-flags)**(VkImageCreateFlagBits flags)<br>Set the image create flags.  |
| void | **[set_tiling](/_doxybook/Classes/structlava_1_1image.md#function-set-tiling)**(VkImageTiling tiling)<br>Set the image tiling.  |
| void | **[set_usage](/_doxybook/Classes/structlava_1_1image.md#function-set-usage)**(VkImageUsageFlags usage)<br>Set the image usage.  |
| void | **[set_layout](/_doxybook/Classes/structlava_1_1image.md#function-set-layout)**(VkImageLayout initial)<br>Set the initial layout of the image.  |
| void | **[set_aspect_mask](/_doxybook/Classes/structlava_1_1image.md#function-set-aspect-mask)**(VkImageAspectFlags aspectMask)<br>Set the aspect mask of the image.  |
| void | **[set_level_count](/_doxybook/Classes/structlava_1_1image.md#function-set-level-count)**([ui32](/_doxybook/Namespaces/namespacelava.md#using-ui32) levels)<br>Set the level count of the image.  |
| void | **[set_layer_count](/_doxybook/Classes/structlava_1_1image.md#function-set-layer-count)**([ui32](/_doxybook/Namespaces/namespacelava.md#using-ui32) layers)<br>Set the layer count of the image.  |
| void | **[set_component](/_doxybook/Classes/structlava_1_1image.md#function-set-component)**(VkComponentMapping mapping ={})<br>Set the component mapping of the image.  |
| void | **[set_view_type](/_doxybook/Classes/structlava_1_1image.md#function-set-view-type)**(VkImageViewType type)<br>Set the view type of the image.  |
| VmaAllocation const & | **[get_allocation](/_doxybook/Classes/structlava_1_1image.md#function-get-allocation)**() const<br>Get the allocation of the image.  |

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
using lava::image::s_ptr =  std::shared_ptr<image>;
```

Shared pointer to image. 

### using s_map

```cpp
using lava::image::s_map =  std::map<id, s_ptr>;
```

Map of images. 

### using s_list

```cpp
using lava::image::s_list =  std::vector<s_ptr>;
```

List of images. 

## Public Functions Documentation

### function make

```cpp
static inline s_ptr make(
    VkFormat format,
    VkImage vk_image =0
)
```

Make a new image. 

**Parameters**: 

  * **format** Image format 
  * **vk_image** Vulkan image 


**Return**: [s_ptr](/_doxybook/Classes/structlava_1_1image.md#using-s-ptr) Shared pointer to image 

### function image

```cpp
explicit image(
    VkFormat format,
    VkImage vk_image =0
)
```

Construct a new image. 

**Parameters**: 

  * **format** Image format 
  * **vk_image** Vulkan image 


### function create

```cpp
bool create(
    device::ptr device,
    uv2 size,
    VmaMemoryUsage memory_usage =VMA_MEMORY_USAGE_GPU_ONLY,
    VmaAllocationCreateFlags allocation_flags =0
)
```

Create a new image. 

**Parameters**: 

  * **device** Vulkan device 
  * **size** Image size 
  * **memory_usage** Memory usage 
  * **allocation_flags** Allocation flags 


**Return**: Create was successful or failed 

### function destroy

```cpp
void destroy(
    bool view_only =false
)
```

Destroy the image. 

**Parameters**: 

  * **view_only** Destroy only the image view 


### function destroy_view

```cpp
inline void destroy_view()
```

Destroy the image view. 

### function get_device

```cpp
inline device::ptr get_device()
```

Get the device. 

**Return**: [device::ptr](/_doxybook/Classes/structlava_1_1device.md#using-ptr) Vulkan device 

### function get_format

```cpp
inline VkFormat get_format() const
```

Get the format of the image. 

**Return**: VkFormat Image format 

### function get_size

```cpp
inline uv2 get_size() const
```

Get the size of the image. 

**Return**: [uv2](/_doxybook/Namespaces/namespacelava.md#using-uv2) Image size 

### function get_depth

```cpp
inline ui32 get_depth() const
```

Get the depth of the image. 

**Return**: [ui32](/_doxybook/Namespaces/namespacelava.md#using-ui32) Image depth 

### function get

```cpp
inline VkImage get() const
```

Get the image. 

**Return**: VkImage Vulkan image 

### function get_view

```cpp
inline VkImageView get_view() const
```

Get the image view. 

**Return**: VkImageView Vulkan image view 

### function get_info

```cpp
inline VkImageCreateInfo const & get_info() const
```

Get the image create information. 

**Return**: VkImageCreateInfo const& Image create information 

### function get_view_info

```cpp
inline VkImageViewCreateInfo const & get_view_info() const
```

Get the image view create information. 

**Return**: VkImageViewCreateInfo const& Image view create information 

### function get_subresource_range

```cpp
inline VkImageSubresourceRange const & get_subresource_range() const
```

Get the subresource range of the image. 

**Return**: VkImageSubresourceRange const& Image subresource range 

### function set_flags

```cpp
inline void set_flags(
    VkImageCreateFlagBits flags
)
```

Set the image create flags. 

**Parameters**: 

  * **flags** Image create flag bits 


### function set_tiling

```cpp
inline void set_tiling(
    VkImageTiling tiling
)
```

Set the image tiling. 

**Parameters**: 

  * **tiling** Image tiling 


### function set_usage

```cpp
inline void set_usage(
    VkImageUsageFlags usage
)
```

Set the image usage. 

**Parameters**: 

  * **usage** Image usage flags 


### function set_layout

```cpp
inline void set_layout(
    VkImageLayout initial
)
```

Set the initial layout of the image. 

**Parameters**: 

  * **initial** Initial image layout 


### function set_aspect_mask

```cpp
inline void set_aspect_mask(
    VkImageAspectFlags aspectMask
)
```

Set the aspect mask of the image. 

**Parameters**: 

  * **aspectMask** Image aspect flags 


### function set_level_count

```cpp
inline void set_level_count(
    ui32 levels
)
```

Set the level count of the image. 

**Parameters**: 

  * **levels** Number of levels 


### function set_layer_count

```cpp
inline void set_layer_count(
    ui32 layers
)
```

Set the layer count of the image. 

**Parameters**: 

  * **layers** Number of layers 


### function set_component

```cpp
inline void set_component(
    VkComponentMapping mapping ={}
)
```

Set the component mapping of the image. 

**Parameters**: 

  * **mapping** Component mapping 


### function set_view_type

```cpp
inline void set_view_type(
    VkImageViewType type
)
```

Set the view type of the image. 

**Parameters**: 

  * **type** Image view type 


### function get_allocation

```cpp
inline VmaAllocation const & get_allocation() const
```

Get the allocation of the image. 

**Return**: VmaAllocation const& Image allocation 

-------------------------------

Updated on 2026-02-01 at 18:13:39 +0000