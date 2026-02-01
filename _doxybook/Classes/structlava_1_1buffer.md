---
title: lava::buffer
summary: Buffer. 

---

# lava::buffer



Buffer. 


`#include <buffer.hpp>`

Inherits from [lava::entity](/_doxybook/Classes/structlava_1_1entity.md), [lava::no_copy_no_move](/_doxybook/Classes/structlava_1_1no__copy__no__move.md), [lava::interface](/_doxybook/Classes/structlava_1_1interface.md)

## Public Types

|                | Name           |
| -------------- | -------------- |
| using std::shared_ptr< [buffer](/_doxybook/Classes/structlava_1_1buffer.md) > | **[s_ptr](/_doxybook/Classes/structlava_1_1buffer.md#using-s-ptr)** <br>Shared pointer to buffer.  |
| using std::vector< [s_ptr](/_doxybook/Classes/structlava_1_1buffer.md#using-s-ptr) > | **[s_list](/_doxybook/Classes/structlava_1_1buffer.md#using-s-list)** <br>List of buffers.  |

## Public Functions

|                | Name           |
| -------------- | -------------- |
| [s_ptr](/_doxybook/Classes/structlava_1_1buffer.md#using-s-ptr) | **[make](/_doxybook/Classes/structlava_1_1buffer.md#function-make)**()<br>Make a new buffer.  |
| | **[~buffer](/_doxybook/Classes/structlava_1_1buffer.md#function-~buffer)**()<br>Destroy the buffer.  |
| bool | **[create](/_doxybook/Classes/structlava_1_1buffer.md#function-create)**([device::ptr](/_doxybook/Classes/structlava_1_1device.md#using-ptr) device, void const * data, [size_t](/_doxybook/Namespaces/namespacelava.md#using-size-t) size, VkBufferUsageFlags usage, bool mapped =false, VmaMemoryUsage memory_usage =VMA_MEMORY_USAGE_GPU_ONLY, VkSharingMode sharing_mode =VK_SHARING_MODE_EXCLUSIVE, std::vector< [ui32](/_doxybook/Namespaces/namespacelava.md#using-ui32) > const & shared_queue_family_indices ={}, [i32](/_doxybook/Namespaces/namespacelava.md#using-i32) alignment =[undef](/_doxybook/Namespaces/namespacelava.md#variable-undef))<br>Create a new buffer.  |
| bool | **[create_mapped](/_doxybook/Classes/structlava_1_1buffer.md#function-create-mapped)**([device::ptr](/_doxybook/Classes/structlava_1_1device.md#using-ptr) device, void const * data, [size_t](/_doxybook/Namespaces/namespacelava.md#using-size-t) size, VkBufferUsageFlags usage, VmaMemoryUsage memory_usage =VMA_MEMORY_USAGE_CPU_TO_GPU, VkSharingMode sharing_mode =VK_SHARING_MODE_EXCLUSIVE, std::vector< [ui32](/_doxybook/Namespaces/namespacelava.md#using-ui32) > const & shared_queue_family_indices ={}, [i32](/_doxybook/Namespaces/namespacelava.md#using-i32) alignment =[undef](/_doxybook/Namespaces/namespacelava.md#variable-undef))<br>Create a new mapped buffer.  |
| void | **[destroy](/_doxybook/Classes/structlava_1_1buffer.md#function-destroy)**()<br>Destroy the buffer.  |
| [device::ptr](/_doxybook/Classes/structlava_1_1device.md#using-ptr) | **[get_device](/_doxybook/Classes/structlava_1_1buffer.md#function-get-device)**()<br>Get the device.  |
| bool | **[valid](/_doxybook/Classes/structlava_1_1buffer.md#function-valid)**() const<br>Check if the buffer is valid.  |
| VkBuffer | **[get](/_doxybook/Classes/structlava_1_1buffer.md#function-get)**() const<br>Get the buffer.  |
| VkDescriptorBufferInfo const * | **[get_descriptor_info](/_doxybook/Classes/structlava_1_1buffer.md#function-get-descriptor-info)**() const<br>Get the descriptor information.  |
| VkDeviceAddress | **[get_address](/_doxybook/Classes/structlava_1_1buffer.md#function-get-address)**() const<br>Get the address of the buffer.  |
| VkDeviceSize | **[get_size](/_doxybook/Classes/structlava_1_1buffer.md#function-get-size)**() const<br>Get the size of the buffer.  |
| void * | **[get_mapped_data](/_doxybook/Classes/structlava_1_1buffer.md#function-get-mapped-data)**() const<br>Get the mapped data.  |
| VkDeviceMemory | **[get_device_memory](/_doxybook/Classes/structlava_1_1buffer.md#function-get-device-memory)**() const<br>Get the device memory of the buffer.  |
| void | **[flush](/_doxybook/Classes/structlava_1_1buffer.md#function-flush)**(VkDeviceSize offset =0, VkDeviceSize size =VK_WHOLE_SIZE)<br>Flush the buffer data.  |
| VmaAllocation const & | **[get_allocation](/_doxybook/Classes/structlava_1_1buffer.md#function-get-allocation)**() const<br>Get the allocation.  |
| VmaAllocationInfo const & | **[get_allocation_info](/_doxybook/Classes/structlava_1_1buffer.md#function-get-allocation-info)**() const<br>Get the allocation information.  |

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
using lava::buffer::s_ptr =  std::shared_ptr<buffer>;
```

Shared pointer to buffer. 

### using s_list

```cpp
using lava::buffer::s_list =  std::vector<s_ptr>;
```

List of buffers. 

## Public Functions Documentation

### function make

```cpp
static inline s_ptr make()
```

Make a new buffer. 

**Return**: [s_ptr](/_doxybook/Classes/structlava_1_1buffer.md#using-s-ptr) Shared pointer to buffer 

### function ~buffer

```cpp
inline ~buffer()
```

Destroy the buffer. 

### function create

```cpp
bool create(
    device::ptr device,
    void const * data,
    size_t size,
    VkBufferUsageFlags usage,
    bool mapped =false,
    VmaMemoryUsage memory_usage =VMA_MEMORY_USAGE_GPU_ONLY,
    VkSharingMode sharing_mode =VK_SHARING_MODE_EXCLUSIVE,
    std::vector< ui32 > const & shared_queue_family_indices ={},
    i32 alignment =undef
)
```

Create a new buffer. 

**Parameters**: 

  * **device** Vulkan device 
  * **data** Buffer data 
  * **size** Data size 
  * **usage** Buffer usage flags 
  * **mapped** Map the buffer 
  * **memory_usage** Memory usage 
  * **sharing_mode** Sharing mode 
  * **shared_queue_family_indices** Queue indices (ignored unless sharing_mode == VK_SHARING_MODE_CONCURRENT) 
  * **alignment** Minimum alignment to be used when placing the buffer inside a larger memory block negative -> no minimum alignment 


**Return**: Create was successful or failed 

### function create_mapped

```cpp
bool create_mapped(
    device::ptr device,
    void const * data,
    size_t size,
    VkBufferUsageFlags usage,
    VmaMemoryUsage memory_usage =VMA_MEMORY_USAGE_CPU_TO_GPU,
    VkSharingMode sharing_mode =VK_SHARING_MODE_EXCLUSIVE,
    std::vector< ui32 > const & shared_queue_family_indices ={},
    i32 alignment =undef
)
```

Create a new mapped buffer. 

**Parameters**: 

  * **device** Vulkan device 
  * **data** Buffer data 
  * **size** Data size 
  * **usage** Buffer usage flags 
  * **memory_usage** Memory usage 
  * **sharing_mode** Sharing mode 
  * **shared_queue_family_indices** Queue indices (ignored unless sharing_mode == VK_SHARING_MODE_CONCURRENT) 
  * **alignment** Minimum alignment to be used when placing the buffer inside a larger memory block negative -> no minimum alignment 


**Return**: Create was successful or failed 

### function destroy

```cpp
void destroy()
```

Destroy the buffer. 

### function get_device

```cpp
inline device::ptr get_device()
```

Get the device. 

**Return**: [device::ptr](/_doxybook/Classes/structlava_1_1device.md#using-ptr) Vulkan device 

### function valid

```cpp
inline bool valid() const
```

Check if the buffer is valid. 

**Return**: Buffer is valid or not 

### function get

```cpp
inline VkBuffer get() const
```

Get the buffer. 

**Return**: VkBuffer Vulkan buffer 

### function get_descriptor_info

```cpp
inline VkDescriptorBufferInfo const * get_descriptor_info() const
```

Get the descriptor information. 

**Return**: VkDescriptorBufferInfo const* Descriptor buffer information 

### function get_address

```cpp
VkDeviceAddress get_address() const
```

Get the address of the buffer. 

**Return**: VkDeviceAddress Device address 

### function get_size

```cpp
inline VkDeviceSize get_size() const
```

Get the size of the buffer. 

**Return**: VkDeviceSize Device size 

### function get_mapped_data

```cpp
inline void * get_mapped_data() const
```

Get the mapped data. 

**Return**: void* Pointer to data 

### function get_device_memory

```cpp
inline VkDeviceMemory get_device_memory() const
```

Get the device memory of the buffer. 

**Return**: VkDeviceMemory Device memory 

### function flush

```cpp
void flush(
    VkDeviceSize offset =0,
    VkDeviceSize size =VK_WHOLE_SIZE
)
```

Flush the buffer data. 

**Parameters**: 

  * **offset** Offset device size 
  * **size** Data device size 


### function get_allocation

```cpp
inline VmaAllocation const & get_allocation() const
```

Get the allocation. 

**Return**: VmaAllocation const& Allocation 

### function get_allocation_info

```cpp
inline VmaAllocationInfo const & get_allocation_info() const
```

Get the allocation information. 

**Return**: VmaAllocationInfo const& Allocation information 

-------------------------------

Updated on 2026-02-01 at 18:13:39 +0000