---
title: lava::device
summary: Vulkan device. 

---

# lava::device



Vulkan device. 


`#include <device.hpp>`

Inherits from [lava::device_table](/_doxybook/Classes/structlava_1_1device__table.md), [lava::entity](/_doxybook/Classes/structlava_1_1entity.md), [lava::no_copy_no_move](/_doxybook/Classes/structlava_1_1no__copy__no__move.md), [lava::interface](/_doxybook/Classes/structlava_1_1interface.md)

## Public Classes

|                | Name           |
| -------------- | -------------- |
| struct | **[create_param](/_doxybook/Classes/structlava_1_1device_1_1create__param.md)** <br>Device create parameters.  |

## Public Types

|                | Name           |
| -------------- | -------------- |
| using [device](/_doxybook/Classes/structlava_1_1device.md) * | **[ptr](/_doxybook/Classes/structlava_1_1device.md#using-ptr)** <br>Pointer to device.  |
| using [device](/_doxybook/Classes/structlava_1_1device.md) const  * | **[c_ptr](/_doxybook/Classes/structlava_1_1device.md#using-c-ptr)** <br>Const pointer to device.  |
| using std::shared_ptr< [device](/_doxybook/Classes/structlava_1_1device.md) > | **[s_ptr](/_doxybook/Classes/structlava_1_1device.md#using-s-ptr)** <br>Shared pointer to a device.  |
| using std::vector< [s_ptr](/_doxybook/Classes/structlava_1_1device.md#using-s-ptr) > | **[s_list](/_doxybook/Classes/structlava_1_1device.md#using-s-list)** <br>List of devices.  |
| using [physical_device](/_doxybook/Classes/structlava_1_1physical__device.md) const  * | **[physical_device_c_ptr](/_doxybook/Classes/structlava_1_1device.md#using-physical-device-c-ptr)** <br>Const pointer to a physical device.  |

## Public Functions

|                | Name           |
| -------------- | -------------- |
| [s_ptr](/_doxybook/Classes/structlava_1_1device.md#using-s-ptr) | **[make](/_doxybook/Classes/structlava_1_1device.md#function-make)**()<br>Make a new device.  |
| | **[~device](/_doxybook/Classes/structlava_1_1device.md#function-~device)**()<br>Destroy the device.  |
| bool | **[create](/_doxybook/Classes/structlava_1_1device.md#function-create)**([create_param::ref](/_doxybook/Classes/structlava_1_1device_1_1create__param.md#using-ref) param)<br>Create a new device.  |
| void | **[destroy](/_doxybook/Classes/structlava_1_1device.md#function-destroy)**()<br>Destroy the device.  |
| [queue::ref](/_doxybook/Classes/structlava_1_1queue.md#using-ref) | **[get_graphics_queue](/_doxybook/Classes/structlava_1_1device.md#function-get-graphics-queue)**([index](/_doxybook/Namespaces/namespacelava.md#using-index) index =0) const<br>Get a graphics queue by index.  |
| [queue::ref](/_doxybook/Classes/structlava_1_1queue.md#using-ref) | **[graphics_queue](/_doxybook/Classes/structlava_1_1device.md#function-graphics-queue)**([index](/_doxybook/Namespaces/namespacelava.md#using-index) index =0) const |
| [queue::ref](/_doxybook/Classes/structlava_1_1queue.md#using-ref) | **[get_compute_queue](/_doxybook/Classes/structlava_1_1device.md#function-get-compute-queue)**([index](/_doxybook/Namespaces/namespacelava.md#using-index) index =0) const<br>Get a compute queue by index.  |
| [queue::ref](/_doxybook/Classes/structlava_1_1queue.md#using-ref) | **[compute_queue](/_doxybook/Classes/structlava_1_1device.md#function-compute-queue)**([index](/_doxybook/Namespaces/namespacelava.md#using-index) index =0) const |
| [queue::ref](/_doxybook/Classes/structlava_1_1queue.md#using-ref) | **[get_transfer_queue](/_doxybook/Classes/structlava_1_1device.md#function-get-transfer-queue)**([index](/_doxybook/Namespaces/namespacelava.md#using-index) index =0) const<br>Get a transfer queue by index.  |
| [queue::ref](/_doxybook/Classes/structlava_1_1queue.md#using-ref) | **[transfer_queue](/_doxybook/Classes/structlava_1_1device.md#function-transfer-queue)**([index](/_doxybook/Namespaces/namespacelava.md#using-index) index =0) const |
| [queue::list](/_doxybook/Classes/structlava_1_1queue.md#using-list) const & | **[get_graphics_queues](/_doxybook/Classes/structlava_1_1device.md#function-get-graphics-queues)**() const<br>Get the list of graphics queues.  |
| [queue::list](/_doxybook/Classes/structlava_1_1queue.md#using-list) const & | **[graphics_queues](/_doxybook/Classes/structlava_1_1device.md#function-graphics-queues)**() const |
| [queue::list](/_doxybook/Classes/structlava_1_1queue.md#using-list) const & | **[get_compute_queues](/_doxybook/Classes/structlava_1_1device.md#function-get-compute-queues)**() const<br>Get the list of compute queues.  |
| [queue::list](/_doxybook/Classes/structlava_1_1queue.md#using-list) const & | **[compute_queues](/_doxybook/Classes/structlava_1_1device.md#function-compute-queues)**() const |
| [queue::list](/_doxybook/Classes/structlava_1_1queue.md#using-list) const & | **[get_transfer_queues](/_doxybook/Classes/structlava_1_1device.md#function-get-transfer-queues)**() const<br>Get the list of transfer queues.  |
| [queue::list](/_doxybook/Classes/structlava_1_1queue.md#using-list) const & | **[transfer_queues](/_doxybook/Classes/structlava_1_1device.md#function-transfer-queues)**() const |
| [queue::list](/_doxybook/Classes/structlava_1_1queue.md#using-list) const & | **[get_queues](/_doxybook/Classes/structlava_1_1device.md#function-get-queues)**() const<br>Get all queues.  |
| [queue::list](/_doxybook/Classes/structlava_1_1queue.md#using-list) const & | **[queues](/_doxybook/Classes/structlava_1_1device.md#function-queues)**() const |
| VkDevice | **[get](/_doxybook/Classes/structlava_1_1device.md#function-get)**() const<br>Get the Vulkan device.  |
| VolkDeviceTable const & | **[call](/_doxybook/Classes/structlava_1_1device.md#function-call)**() const<br>Get the Volk device table.  |
| bool | **[wait_for_idle](/_doxybook/Classes/structlava_1_1device.md#function-wait-for-idle)**() const<br>Wait for idle.  |
| [physical_device_c_ptr](/_doxybook/Classes/structlava_1_1device.md#using-physical-device-c-ptr) | **[get_physical_device](/_doxybook/Classes/structlava_1_1device.md#function-get-physical-device)**() const<br>Get the physical device.  |
| VkPhysicalDevice | **[get_vk_physical_device](/_doxybook/Classes/structlava_1_1device.md#function-get-vk-physical-device)**() const<br>Get the Vulkan physical device.  |
| VkPhysicalDeviceFeatures const & | **[get_features](/_doxybook/Classes/structlava_1_1device.md#function-get-features)**() const<br>Get the physical device features.  |
| VkPhysicalDeviceProperties const & | **[get_properties](/_doxybook/Classes/structlava_1_1device.md#function-get-properties)**() const<br>Get the physical device properties.  |
| bool | **[surface_supported](/_doxybook/Classes/structlava_1_1device.md#function-surface-supported)**(VkSurfaceKHR surface) const<br>Check if surface is supported by this device.  |
| void | **[set_allocator](/_doxybook/Classes/structlava_1_1device.md#function-set-allocator)**([allocator::s_ptr](/_doxybook/Classes/structlava_1_1allocator.md#using-s-ptr) value)<br>Set the allocator for this device.  |
| [allocator::s_ptr](/_doxybook/Classes/structlava_1_1allocator.md#using-s-ptr) | **[get_allocator](/_doxybook/Classes/structlava_1_1device.md#function-get-allocator)**()<br>Get the allocator of this device.  |
| VmaAllocator | **[alloc](/_doxybook/Classes/structlava_1_1device.md#function-alloc)**() const<br>Get the VMA allocator.  |

## Additional inherited members

**Public Functions inherited from [lava::device_table](/_doxybook/Classes/structlava_1_1device__table.md)**

|                | Name           |
| -------------- | -------------- |
| void | **[load_table](/_doxybook/Classes/structlava_1_1device__table.md#function-load-table)**()<br>Load device table.  |
| [vk_result](/_doxybook/Classes/structlava_1_1vk__result.md) | **[vkCreateImageView](/_doxybook/Classes/structlava_1_1device__table.md#function-vkcreateimageview)**(const VkImageViewCreateInfo * pCreateInfo, const VkAllocationCallbacks * pAllocator, VkImageView * pView) |
| [vk_result](/_doxybook/Classes/structlava_1_1vk__result.md) | **[vkCreateImageView](/_doxybook/Classes/structlava_1_1device__table.md#function-vkcreateimageview)**(const VkImageViewCreateInfo * pCreateInfo, VkImageView * pView) |
| [vk_result](/_doxybook/Classes/structlava_1_1vk__result.md) | **[vkCreateSampler](/_doxybook/Classes/structlava_1_1device__table.md#function-vkcreatesampler)**(const VkSamplerCreateInfo * pCreateInfo, const VkAllocationCallbacks * pAllocator, VkSampler * pSampler) |
| [vk_result](/_doxybook/Classes/structlava_1_1vk__result.md) | **[vkCreateSampler](/_doxybook/Classes/structlava_1_1device__table.md#function-vkcreatesampler)**(const VkSamplerCreateInfo * pCreateInfo, VkSampler * pSampler) |
| [vk_result](/_doxybook/Classes/structlava_1_1vk__result.md) | **[vkCreateShaderModule](/_doxybook/Classes/structlava_1_1device__table.md#function-vkcreateshadermodule)**(const VkShaderModuleCreateInfo * pCreateInfo, const VkAllocationCallbacks * pAllocator, VkShaderModule * pShaderModule) |
| [vk_result](/_doxybook/Classes/structlava_1_1vk__result.md) | **[vkCreateShaderModule](/_doxybook/Classes/structlava_1_1device__table.md#function-vkcreateshadermodule)**(const VkShaderModuleCreateInfo * pCreateInfo, VkShaderModule * pShaderModule) |
| [vk_result](/_doxybook/Classes/structlava_1_1vk__result.md) | **[vkCreateFence](/_doxybook/Classes/structlava_1_1device__table.md#function-vkcreatefence)**(const VkFenceCreateInfo * pCreateInfo, const VkAllocationCallbacks * pAllocator, VkFence * pFence) |
| [vk_result](/_doxybook/Classes/structlava_1_1vk__result.md) | **[vkCreateFence](/_doxybook/Classes/structlava_1_1device__table.md#function-vkcreatefence)**(const VkFenceCreateInfo * pCreateInfo, VkFence * pFence) |
| [vk_result](/_doxybook/Classes/structlava_1_1vk__result.md) | **[vkCreateSemaphore](/_doxybook/Classes/structlava_1_1device__table.md#function-vkcreatesemaphore)**(const VkSemaphoreCreateInfo * pCreateInfo, const VkAllocationCallbacks * pAllocator, VkSemaphore * pSemaphore) |
| [vk_result](/_doxybook/Classes/structlava_1_1vk__result.md) | **[vkCreateSemaphore](/_doxybook/Classes/structlava_1_1device__table.md#function-vkcreatesemaphore)**(const VkSemaphoreCreateInfo * pCreateInfo, VkSemaphore * pSemaphore) |
| [vk_result](/_doxybook/Classes/structlava_1_1vk__result.md) | **[vkWaitForFences](/_doxybook/Classes/structlava_1_1device__table.md#function-vkwaitforfences)**(uint32_t fenceCount, const VkFence * pFences, VkBool32 waitAll, uint64_t timeout) |
| [vk_result](/_doxybook/Classes/structlava_1_1vk__result.md) | **[vkResetFences](/_doxybook/Classes/structlava_1_1device__table.md#function-vkresetfences)**(uint32_t fenceCount, const VkFence * pFences) |
| [vk_result](/_doxybook/Classes/structlava_1_1vk__result.md) | **[vkQueueSubmit](/_doxybook/Classes/structlava_1_1device__table.md#function-vkqueuesubmit)**(VkQueue queue, uint32_t submitCount, const VkSubmitInfo * pSubmits, VkFence fence) |
| [vk_result](/_doxybook/Classes/structlava_1_1vk__result.md) | **[vkAcquireNextImageKHR](/_doxybook/Classes/structlava_1_1device__table.md#function-vkacquirenextimagekhr)**(VkSwapchainKHR swapchain, uint64_t timeout, VkSemaphore semaphore, VkFence fence, uint32_t * pImageIndex) |
| [vk_result](/_doxybook/Classes/structlava_1_1vk__result.md) | **[vkQueuePresentKHR](/_doxybook/Classes/structlava_1_1device__table.md#function-vkqueuepresentkhr)**(VkQueue queue, const VkPresentInfoKHR * pPresentInfo) |
| [vk_result](/_doxybook/Classes/structlava_1_1vk__result.md) | **[vkCreateSwapchainKHR](/_doxybook/Classes/structlava_1_1device__table.md#function-vkcreateswapchainkhr)**(const VkSwapchainCreateInfoKHR * pCreateInfo, const VkAllocationCallbacks * pAllocator, VkSwapchainKHR * pSwapchain) |
| [vk_result](/_doxybook/Classes/structlava_1_1vk__result.md) | **[vkCreateSwapchainKHR](/_doxybook/Classes/structlava_1_1device__table.md#function-vkcreateswapchainkhr)**(const VkSwapchainCreateInfoKHR * pCreateInfo, VkSwapchainKHR * pSwapchain) |
| void | **[vkDestroySwapchainKHR](/_doxybook/Classes/structlava_1_1device__table.md#function-vkdestroyswapchainkhr)**(VkSwapchainKHR swapchain, const VkAllocationCallbacks * pAllocator =[memory::instance](/_doxybook/Classes/structlava_1_1memory.md#function-instance)().alloc()) |
| [vk_result](/_doxybook/Classes/structlava_1_1vk__result.md) | **[vkGetSwapchainImagesKHR](/_doxybook/Classes/structlava_1_1device__table.md#function-vkgetswapchainimageskhr)**(VkSwapchainKHR swapchain, uint32_t * pSwapchainImageCount, VkImage * pSwapchainImages) |
| [vk_result](/_doxybook/Classes/structlava_1_1vk__result.md) | **[vkCreateCommandPool](/_doxybook/Classes/structlava_1_1device__table.md#function-vkcreatecommandpool)**(const VkCommandPoolCreateInfo * pCreateInfo, const VkAllocationCallbacks * pAllocator, VkCommandPool * pCommandPool) |
| [vk_result](/_doxybook/Classes/structlava_1_1vk__result.md) | **[vkCreateCommandPool](/_doxybook/Classes/structlava_1_1device__table.md#function-vkcreatecommandpool)**(const VkCommandPoolCreateInfo * pCreateInfo, VkCommandPool * pCommandPool) |
| [vk_result](/_doxybook/Classes/structlava_1_1vk__result.md) | **[vkCreateCommandPool](/_doxybook/Classes/structlava_1_1device__table.md#function-vkcreatecommandpool)**([index](/_doxybook/Namespaces/namespacelava.md#using-index) queue_family, VkCommandPool * pCommandPool) |
| [vk_result](/_doxybook/Classes/structlava_1_1vk__result.md) | **[vkAllocateCommandBuffers](/_doxybook/Classes/structlava_1_1device__table.md#function-vkallocatecommandbuffers)**(const VkCommandBufferAllocateInfo * pAllocateInfo, VkCommandBuffer * pCommandBuffers) |
| [vk_result](/_doxybook/Classes/structlava_1_1vk__result.md) | **[vkAllocateCommandBuffers](/_doxybook/Classes/structlava_1_1device__table.md#function-vkallocatecommandbuffers)**(VkCommandPool commandPool, uint32_t commandBufferCount, VkCommandBuffer * pCommandBuffers, VkCommandBufferLevel level =VK_COMMAND_BUFFER_LEVEL_PRIMARY) |
| void | **[vkDestroyImageView](/_doxybook/Classes/structlava_1_1device__table.md#function-vkdestroyimageview)**(VkImageView imageView, const VkAllocationCallbacks * pAllocator =[memory::instance](/_doxybook/Classes/structlava_1_1memory.md#function-instance)().alloc()) |
| void | **[vkDestroyFence](/_doxybook/Classes/structlava_1_1device__table.md#function-vkdestroyfence)**(VkFence fence, const VkAllocationCallbacks * pAllocator =[memory::instance](/_doxybook/Classes/structlava_1_1memory.md#function-instance)().alloc()) |
| void | **[vkDestroySemaphore](/_doxybook/Classes/structlava_1_1device__table.md#function-vkdestroysemaphore)**(VkSemaphore semaphore, const VkAllocationCallbacks * pAllocator =[memory::instance](/_doxybook/Classes/structlava_1_1memory.md#function-instance)().alloc()) |
| void | **[vkFreeCommandBuffers](/_doxybook/Classes/structlava_1_1device__table.md#function-vkfreecommandbuffers)**(VkCommandPool commandPool, uint32_t commandBufferCount, const VkCommandBuffer * pCommandBuffers) |
| void | **[vkDestroyCommandPool](/_doxybook/Classes/structlava_1_1device__table.md#function-vkdestroycommandpool)**(VkCommandPool commandPool, const VkAllocationCallbacks * pAllocator =[memory::instance](/_doxybook/Classes/structlava_1_1memory.md#function-instance)().alloc()) |
| void | **[vkDestroySampler](/_doxybook/Classes/structlava_1_1device__table.md#function-vkdestroysampler)**(VkSampler sampler, const VkAllocationCallbacks * pAllocator =[memory::instance](/_doxybook/Classes/structlava_1_1memory.md#function-instance)().alloc()) |
| void | **[vkUpdateDescriptorSets](/_doxybook/Classes/structlava_1_1device__table.md#function-vkupdatedescriptorsets)**(uint32_t descriptorWriteCount, const VkWriteDescriptorSet * pDescriptorWrites, uint32_t descriptorCopyCount =0, const VkCopyDescriptorSet * pDescriptorCopies =nullptr) |
| template <std::size_t SIZE\> <br>void | **[vkUpdateDescriptorSets](/_doxybook/Classes/structlava_1_1device__table.md#function-vkupdatedescriptorsets)**(std::array< VkWriteDescriptorSet, SIZE > const & descriptor_writes) |
| template <std::size_t SIZE\> <br>void | **[vkUpdateDescriptorSets](/_doxybook/Classes/structlava_1_1device__table.md#function-vkupdatedescriptorsets)**(std::array< VkCopyDescriptorSet, SIZE > const & descriptor_copies) |
| template <std::size_t WRITE_SIZE,std::size_t COPY_SIZE\> <br>void | **[vkUpdateDescriptorSets](/_doxybook/Classes/structlava_1_1device__table.md#function-vkupdatedescriptorsets)**(std::array< VkWriteDescriptorSet, WRITE_SIZE > const & descriptor_writes, std::array< VkCopyDescriptorSet, COPY_SIZE > const & descriptor_copies) |
| void | **[vkUpdateDescriptorSets](/_doxybook/Classes/structlava_1_1device__table.md#function-vkupdatedescriptorsets)**(std::initializer_list< VkWriteDescriptorSet > descriptor_writes) |
| void | **[vkUpdateDescriptorSets](/_doxybook/Classes/structlava_1_1device__table.md#function-vkupdatedescriptorsets)**(std::initializer_list< VkCopyDescriptorSet > descriptor_copies) |
| void | **[vkUpdateDescriptorSets](/_doxybook/Classes/structlava_1_1device__table.md#function-vkupdatedescriptorsets)**(std::initializer_list< VkWriteDescriptorSet > descriptor_writes, std::initializer_list< VkCopyDescriptorSet > descriptor_copies) |

**Public Attributes inherited from [lava::device_table](/_doxybook/Classes/structlava_1_1device__table.md)**

|                | Name           |
| -------------- | -------------- |
| VkDevice | **[vk_device](/_doxybook/Classes/structlava_1_1device__table.md#variable-vk-device)** <br>Vulkan device.  |
| VolkDeviceTable | **[table](/_doxybook/Classes/structlava_1_1device__table.md#variable-table)** <br>Volk device table.  |

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
using lava::device::ptr =  device*;
```

Pointer to device. 

### using c_ptr

```cpp
using lava::device::c_ptr =  device const*;
```

Const pointer to device. 

### using s_ptr

```cpp
using lava::device::s_ptr =  std::shared_ptr<device>;
```

Shared pointer to a device. 

### using s_list

```cpp
using lava::device::s_list =  std::vector<s_ptr>;
```

List of devices. 

### using physical_device_c_ptr

```cpp
using lava::device::physical_device_c_ptr =  physical_device const*;
```

Const pointer to a physical device. 

## Public Functions Documentation

### function make

```cpp
static inline s_ptr make()
```

Make a new device. 

**Return**: [s_ptr](/_doxybook/Classes/structlava_1_1device.md#using-s-ptr) Shared pointer to device 

### function ~device

```cpp
inline ~device()
```

Destroy the device. 

### function create

```cpp
bool create(
    create_param::ref param
)
```

Create a new device. 

**Parameters**: 

  * **param** Create parameters 


**Return**: Create was successful or failed 

### function destroy

```cpp
void destroy()
```

Destroy the device. 

### function get_graphics_queue

```cpp
inline queue::ref get_graphics_queue(
    index index =0
) const
```

Get a graphics queue by index. 

**Parameters**: 

  * **index** Index of queue 


**Return**: [queue::ref](/_doxybook/Classes/structlava_1_1queue.md#using-ref) Graphics queue 

### function graphics_queue

```cpp
inline queue::ref graphics_queue(
    index index =0
) const
```


**See**: [get_graphics_queue](/_doxybook/Classes/structlava_1_1device.md#function-get-graphics-queue)

### function get_compute_queue

```cpp
inline queue::ref get_compute_queue(
    index index =0
) const
```

Get a compute queue by index. 

**Parameters**: 

  * **index** Index of queue 


**Return**: [queue::ref](/_doxybook/Classes/structlava_1_1queue.md#using-ref) Compute queue 

### function compute_queue

```cpp
inline queue::ref compute_queue(
    index index =0
) const
```


**See**: [get_compute_queue](/_doxybook/Classes/structlava_1_1device.md#function-get-compute-queue)

### function get_transfer_queue

```cpp
inline queue::ref get_transfer_queue(
    index index =0
) const
```

Get a transfer queue by index. 

**Parameters**: 

  * **index** Index of queue 


**Return**: [queue::ref](/_doxybook/Classes/structlava_1_1queue.md#using-ref) Transfer queue 

### function transfer_queue

```cpp
inline queue::ref transfer_queue(
    index index =0
) const
```


**See**: [get_transfer_queue](/_doxybook/Classes/structlava_1_1device.md#function-get-transfer-queue)

### function get_graphics_queues

```cpp
inline queue::list const & get_graphics_queues() const
```

Get the list of graphics queues. 

**Return**: [queue::list](/_doxybook/Classes/structlava_1_1queue.md#using-list) const& Graphics queues 

### function graphics_queues

```cpp
inline queue::list const & graphics_queues() const
```


**See**: [get_graphics_queues](/_doxybook/Classes/structlava_1_1device.md#function-get-graphics-queues)

### function get_compute_queues

```cpp
inline queue::list const & get_compute_queues() const
```

Get the list of compute queues. 

**Return**: [queue::list](/_doxybook/Classes/structlava_1_1queue.md#using-list) const& Compute queues 

### function compute_queues

```cpp
inline queue::list const & compute_queues() const
```


**See**: [get_compute_queues](/_doxybook/Classes/structlava_1_1device.md#function-get-compute-queues)

### function get_transfer_queues

```cpp
inline queue::list const & get_transfer_queues() const
```

Get the list of transfer queues. 

**Return**: [queue::list](/_doxybook/Classes/structlava_1_1queue.md#using-list) const& Transfer queues 

### function transfer_queues

```cpp
inline queue::list const & transfer_queues() const
```


**See**: [get_transfer_queues](/_doxybook/Classes/structlava_1_1device.md#function-get-transfer-queues)

### function get_queues

```cpp
inline queue::list const & get_queues() const
```

Get all queues. 

**Return**: [queue::list](/_doxybook/Classes/structlava_1_1queue.md#using-list) const& List of all queues 

### function queues

```cpp
inline queue::list const & queues() const
```


**See**: [get_queues](/_doxybook/Classes/structlava_1_1device.md#function-get-queues)

### function get

```cpp
inline VkDevice get() const
```

Get the Vulkan device. 

**Return**: VkDevice Vulkan device 

### function call

```cpp
inline VolkDeviceTable const & call() const
```

Get the Volk device table. 

**Return**: VolkDeviceTable const& Volk device table 

### function wait_for_idle

```cpp
inline bool wait_for_idle() const
```

Wait for idle. 

**Return**: Wait was successful or failed 

### function get_physical_device

```cpp
inline physical_device_c_ptr get_physical_device() const
```

Get the physical device. 

**Return**: [physical_device_c_ptr](/_doxybook/Classes/structlava_1_1device.md#using-physical-device-c-ptr) Physical device 

### function get_vk_physical_device

```cpp
VkPhysicalDevice get_vk_physical_device() const
```

Get the Vulkan physical device. 

**Return**: VkPhysicalDevice Vulkan physical device 

### function get_features

```cpp
VkPhysicalDeviceFeatures const & get_features() const
```

Get the physical device features. 

**Return**: VkPhysicalDeviceFeatures const& Features 

### function get_properties

```cpp
VkPhysicalDeviceProperties const & get_properties() const
```

Get the physical device properties. 

**Return**: VkPhysicalDeviceProperties const& Properties 

### function surface_supported

```cpp
bool surface_supported(
    VkSurfaceKHR surface
) const
```

Check if surface is supported by this device. 

**Parameters**: 

  * **surface** Surface to check 


**Return**: Surface is supported or not 

### function set_allocator

```cpp
inline void set_allocator(
    allocator::s_ptr value
)
```

Set the allocator for this device. 

**Parameters**: 

  * **value** Allocator 


### function get_allocator

```cpp
inline allocator::s_ptr get_allocator()
```

Get the allocator of this device. 

**Return**: [allocator::s_ptr](/_doxybook/Classes/structlava_1_1allocator.md#using-s-ptr) Allocator 

### function alloc

```cpp
inline VmaAllocator alloc() const
```

Get the VMA allocator. 

**Return**: VmaAllocator VMA allocator 

-------------------------------

Updated on 2026-02-01 at 18:13:39 +0000