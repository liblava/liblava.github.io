---
title: lava::pipeline_layout
summary: Pipeline layout. 

---

# lava::pipeline_layout



Pipeline layout. 


`#include <pipeline_layout.hpp>`

Inherits from [lava::entity](/_doxybook/Classes/structlava_1_1entity.md), [lava::no_copy_no_move](/_doxybook/Classes/structlava_1_1no__copy__no__move.md), [lava::interface](/_doxybook/Classes/structlava_1_1interface.md)

## Public Types

|                | Name           |
| -------------- | -------------- |
| using std::shared_ptr< [pipeline_layout](/_doxybook/Classes/structlava_1_1pipeline__layout.md) > | **[s_ptr](/_doxybook/Classes/structlava_1_1pipeline__layout.md#using-s-ptr)** <br>Shared pointer to pipeline layout.  |
| using std::vector< [s_ptr](/_doxybook/Classes/structlava_1_1pipeline__layout.md#using-s-ptr) > | **[s_list](/_doxybook/Classes/structlava_1_1pipeline__layout.md#using-s-list)** <br>List of pipeline layouts.  |
| using std::vector< [index](/_doxybook/Namespaces/namespacelava.md#using-index) > | **[offset_list](/_doxybook/Classes/structlava_1_1pipeline__layout.md#using-offset-list)** <br>List of offsets.  |

## Public Functions

|                | Name           |
| -------------- | -------------- |
| [s_ptr](/_doxybook/Classes/structlava_1_1pipeline__layout.md#using-s-ptr) | **[make](/_doxybook/Classes/structlava_1_1pipeline__layout.md#function-make)**()<br>Make a new pipeline layout.  |
| void | **[add](/_doxybook/Classes/structlava_1_1pipeline__layout.md#function-add)**([descriptor::s_ptr](/_doxybook/Classes/structlava_1_1descriptor.md#using-s-ptr) const & descriptor) |
| void | **[add](/_doxybook/Classes/structlava_1_1pipeline__layout.md#function-add)**(VkPushConstantRange const & range) |
| void | **[add_descriptor](/_doxybook/Classes/structlava_1_1pipeline__layout.md#function-add-descriptor)**([descriptor::s_ptr](/_doxybook/Classes/structlava_1_1descriptor.md#using-s-ptr) const & descriptor)<br>Add descriptor.  |
| void | **[add_push_constant_range](/_doxybook/Classes/structlava_1_1pipeline__layout.md#function-add-push-constant-range)**(VkPushConstantRange const & range)<br>Add push contant range.  |
| void | **[clear_descriptors](/_doxybook/Classes/structlava_1_1pipeline__layout.md#function-clear-descriptors)**()<br>Clear descriptors.  |
| void | **[clear_ranges](/_doxybook/Classes/structlava_1_1pipeline__layout.md#function-clear-ranges)**()<br>Clear push constant ranges.  |
| void | **[clear](/_doxybook/Classes/structlava_1_1pipeline__layout.md#function-clear)**()<br>Clear descriptors and push constant ranges.  |
| bool | **[create](/_doxybook/Classes/structlava_1_1pipeline__layout.md#function-create)**([device::ptr](/_doxybook/Classes/structlava_1_1device.md#using-ptr) device)<br>Create a new pipeline layout.  |
| void | **[destroy](/_doxybook/Classes/structlava_1_1pipeline__layout.md#function-destroy)**()<br>Destroy the pipeline layout.  |
| VkPipelineLayout | **[get](/_doxybook/Classes/structlava_1_1pipeline__layout.md#function-get)**() const<br>Get the Vulkan pipeline layout.  |
| [device::ptr](/_doxybook/Classes/structlava_1_1device.md#using-ptr) | **[get_device](/_doxybook/Classes/structlava_1_1pipeline__layout.md#function-get-device)**()<br>Get the device.  |
| [descriptor::s_list](/_doxybook/Classes/structlava_1_1descriptor.md#using-s-list) const & | **[get_descriptors](/_doxybook/Classes/structlava_1_1pipeline__layout.md#function-get-descriptors)**() const<br>Get the descriptors.  |
| [VkPushConstantRanges](/_doxybook/Namespaces/namespacelava.md#using-vkpushconstantranges) const & | **[get_push_constant_ranges](/_doxybook/Classes/structlava_1_1pipeline__layout.md#function-get-push-constant-ranges)**() const<br>Get the push constant ranges.  |
| void | **[bind_descriptor_set](/_doxybook/Classes/structlava_1_1pipeline__layout.md#function-bind-descriptor-set)**(VkCommandBuffer cmd_buf, VkDescriptorSet descriptor_set, [index](/_doxybook/Namespaces/namespacelava.md#using-index) first_set =0, [offset_list](/_doxybook/Classes/structlava_1_1pipeline__layout.md#using-offset-list) offsets ={}, VkPipelineBindPoint bind_point =VK_PIPELINE_BIND_POINT_GRAPHICS)<br>Bind descriptor set.  |
| void | **[bind](/_doxybook/Classes/structlava_1_1pipeline__layout.md#function-bind)**(VkCommandBuffer cmd_buf, VkDescriptorSet descriptor_set, [index](/_doxybook/Namespaces/namespacelava.md#using-index) first_set =0, [offset_list](/_doxybook/Classes/structlava_1_1pipeline__layout.md#using-offset-list) offsets ={}, VkPipelineBindPoint bind_point =VK_PIPELINE_BIND_POINT_GRAPHICS) |

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
using lava::pipeline_layout::s_ptr =  std::shared_ptr<pipeline_layout>;
```

Shared pointer to pipeline layout. 

### using s_list

```cpp
using lava::pipeline_layout::s_list =  std::vector<s_ptr>;
```

List of pipeline layouts. 

### using offset_list

```cpp
using lava::pipeline_layout::offset_list =  std::vector<index>;
```

List of offsets. 

## Public Functions Documentation

### function make

```cpp
static inline s_ptr make()
```

Make a new pipeline layout. 

**Return**: ptr Shared pointer to pipeline layout 

### function add

```cpp
inline void add(
    descriptor::s_ptr const & descriptor
)
```


**See**: [add_descriptor](/_doxybook/Classes/structlava_1_1pipeline__layout.md#function-add-descriptor)

### function add

```cpp
inline void add(
    VkPushConstantRange const & range
)
```


**See**: [add_push_constant_range](/_doxybook/Classes/structlava_1_1pipeline__layout.md#function-add-push-constant-range)

### function add_descriptor

```cpp
inline void add_descriptor(
    descriptor::s_ptr const & descriptor
)
```

Add descriptor. 

**Parameters**: 

  * **descriptor** Descriptor 


### function add_push_constant_range

```cpp
inline void add_push_constant_range(
    VkPushConstantRange const & range
)
```

Add push contant range. 

**Parameters**: 

  * **range** Push contant range 


### function clear_descriptors

```cpp
inline void clear_descriptors()
```

Clear descriptors. 

### function clear_ranges

```cpp
inline void clear_ranges()
```

Clear push constant ranges. 

### function clear

```cpp
inline void clear()
```

Clear descriptors and push constant ranges. 

### function create

```cpp
bool create(
    device::ptr device
)
```

Create a new pipeline layout. 

**Parameters**: 

  * **device** Vulkan device 


**Return**: Create was successful or failed 

### function destroy

```cpp
void destroy()
```

Destroy the pipeline layout. 

### function get

```cpp
inline VkPipelineLayout get() const
```

Get the Vulkan pipeline layout. 

**Return**: VkPipelineLayout Pipeline layout 

### function get_device

```cpp
inline device::ptr get_device()
```

Get the device. 

**Return**: [device::ptr](/_doxybook/Classes/structlava_1_1device.md#using-ptr) Vulkan device 

### function get_descriptors

```cpp
inline descriptor::s_list const & get_descriptors() const
```

Get the descriptors. 

**Return**: [descriptor::s_list](/_doxybook/Classes/structlava_1_1descriptor.md#using-s-list) const& List of descriptors 

### function get_push_constant_ranges

```cpp
inline VkPushConstantRanges const & get_push_constant_ranges() const
```

Get the push constant ranges. 

**Return**: [VkPushConstantRanges](/_doxybook/Namespaces/namespacelava.md#using-vkpushconstantranges) const& List of push constant ranges 

### function bind_descriptor_set

```cpp
void bind_descriptor_set(
    VkCommandBuffer cmd_buf,
    VkDescriptorSet descriptor_set,
    index first_set =0,
    offset_list offsets ={},
    VkPipelineBindPoint bind_point =VK_PIPELINE_BIND_POINT_GRAPHICS
)
```

Bind descriptor set. 

**Parameters**: 

  * **cmd_buf** Command buffer 
  * **descriptor_set** Descriptor set 
  * **first_set** Index to first descriptor set 
  * **offsets** List of offsets 
  * **bind_point** Pipeline bind point 


### function bind

```cpp
inline void bind(
    VkCommandBuffer cmd_buf,
    VkDescriptorSet descriptor_set,
    index first_set =0,
    offset_list offsets ={},
    VkPipelineBindPoint bind_point =VK_PIPELINE_BIND_POINT_GRAPHICS
)
```


**See**: [bind_descriptor_set](/_doxybook/Classes/structlava_1_1pipeline__layout.md#function-bind-descriptor-set)

-------------------------------

Updated on 2026-02-01 at 18:13:39 +0000