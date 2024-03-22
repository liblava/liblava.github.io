---
title: lava::descriptor::pool
summary: Descriptor pool. 

---

# lava::descriptor::pool



Descriptor pool. 


`#include <descriptor.hpp>`

Inherits from [lava::entity](/_doxybook/Classes/structlava_1_1entity.md), [lava::no_copy_no_move](/_doxybook/Classes/structlava_1_1no__copy__no__move.md), [lava::interface](/_doxybook/Classes/structlava_1_1interface.md)

## Public Types

|                | Name           |
| -------------- | -------------- |
| using std::shared_ptr< [pool](/_doxybook/Classes/structlava_1_1descriptor_1_1pool.md) > | **[ptr](/_doxybook/Classes/structlava_1_1descriptor_1_1pool.md#using-ptr)** <br>Shared pointer to pool.  |
| using std::vector< [ptr](/_doxybook/Classes/structlava_1_1descriptor_1_1pool.md#using-ptr) > | **[list](/_doxybook/Classes/structlava_1_1descriptor_1_1pool.md#using-list)** <br>List of pools.  |

## Public Functions

|                | Name           |
| -------------- | -------------- |
| [ptr](/_doxybook/Classes/structlava_1_1descriptor_1_1pool.md#using-ptr) | **[make](/_doxybook/Classes/structlava_1_1descriptor_1_1pool.md#function-make)**()<br>Make a new descriptor pool.  |
| bool | **[create](/_doxybook/Classes/structlava_1_1descriptor_1_1pool.md#function-create)**([device_p](/_doxybook/Namespaces/namespacelava.md#using-device-p) device, [VkDescriptorPoolSizesRef](/_doxybook/Namespaces/namespacelava.md#using-vkdescriptorpoolsizesref) sizes, [ui32](/_doxybook/Namespaces/namespacelava.md#using-ui32) max =1, VkDescriptorPoolCreateFlags flags =VK_DESCRIPTOR_POOL_CREATE_FREE_DESCRIPTOR_SET_BIT)<br>Create a new pool.  |
| void | **[destroy](/_doxybook/Classes/structlava_1_1descriptor_1_1pool.md#function-destroy)**()<br>Destroy the pool.  |
| VkDescriptorPool | **[get](/_doxybook/Classes/structlava_1_1descriptor_1_1pool.md#function-get)**() const<br>Get the descriptor pool.  |
| [device_p](/_doxybook/Namespaces/namespacelava.md#using-device-p) | **[get_device](/_doxybook/Classes/structlava_1_1descriptor_1_1pool.md#function-get-device)**()<br>Get the device.  |
| [VkDescriptorPoolSizes](/_doxybook/Namespaces/namespacelava.md#using-vkdescriptorpoolsizes) const & | **[get_sizes](/_doxybook/Classes/structlava_1_1descriptor_1_1pool.md#function-get-sizes)**() const<br>Get the sizes.  |
| [ui32](/_doxybook/Namespaces/namespacelava.md#using-ui32) | **[get_max](/_doxybook/Classes/structlava_1_1descriptor_1_1pool.md#function-get-max)**() const<br>Get the max.  |

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
using lava::descriptor::pool::ptr =  std::shared_ptr<pool>;
```

Shared pointer to pool. 

### using list

```cpp
using lava::descriptor::pool::list =  std::vector<ptr>;
```

List of pools. 

## Public Functions Documentation

### function make

```cpp
static inline ptr make()
```

Make a new descriptor pool. 

**Return**: ptr Shared pointer to descriptor pool 

### function create

```cpp
bool create(
    device_p device,
    VkDescriptorPoolSizesRef sizes,
    ui32 max =1,
    VkDescriptorPoolCreateFlags flags =VK_DESCRIPTOR_POOL_CREATE_FREE_DESCRIPTOR_SET_BIT
)
```

Create a new pool. 

**Parameters**: 

  * **device** Vulkan device 
  * **sizes** Descriptor pool sizes 
  * **max** Number of pools 
  * **flags** Create flags 


**Return**: Create was successful or failed 

### function destroy

```cpp
void destroy()
```

Destroy the pool. 

### function get

```cpp
inline VkDescriptorPool get() const
```

Get the descriptor pool. 

**Return**: VkDescriptorPool Vulkan descriptor pool 

### function get_device

```cpp
inline device_p get_device()
```

Get the device. 

**Return**: device_p Vulkan device 

### function get_sizes

```cpp
inline VkDescriptorPoolSizes const & get_sizes() const
```

Get the sizes. 

**Return**: VkDescriptorPoolSizes const& Descriptor pool sizes 

### function get_max

```cpp
inline ui32 get_max() const
```

Get the max. 

**Return**: ui32 Number of pools 

-------------------------------

Updated on 2024-03-22 at 21:51:37 +0000