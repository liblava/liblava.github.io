---
title: lava::device_table
summary: Device functions. 

---

# lava::device_table



Device functions. 


`#include <device_table.hpp>`

Inherited by [lava::device](/_doxybook/Classes/structlava_1_1device.md)

## Public Functions

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

## Public Attributes

|                | Name           |
| -------------- | -------------- |
| VkDevice | **[vk_device](/_doxybook/Classes/structlava_1_1device__table.md#variable-vk-device)** <br>Vulkan device.  |
| VolkDeviceTable | **[table](/_doxybook/Classes/structlava_1_1device__table.md#variable-table)** <br>Volk device table.  |

## Public Functions Documentation

### function load_table

```cpp
inline void load_table()
```

Load device table. 

### function vkCreateImageView

```cpp
inline vk_result vkCreateImageView(
    const VkImageViewCreateInfo * pCreateInfo,
    const VkAllocationCallbacks * pAllocator,
    VkImageView * pView
)
```


**See**: [https://www.khronos.org/registry/vulkan/specs/1.3/html/vkspec.html#vkCreateImageView](https://www.khronos.org/registry/vulkan/specs/1.3/html/vkspec.html#vkCreateImageView)

### function vkCreateImageView

```cpp
inline vk_result vkCreateImageView(
    const VkImageViewCreateInfo * pCreateInfo,
    VkImageView * pView
)
```


**See**: [https://www.khronos.org/registry/vulkan/specs/1.3/html/vkspec.html#vkCreateImageView](https://www.khronos.org/registry/vulkan/specs/1.3/html/vkspec.html#vkCreateImageView)

### function vkCreateSampler

```cpp
inline vk_result vkCreateSampler(
    const VkSamplerCreateInfo * pCreateInfo,
    const VkAllocationCallbacks * pAllocator,
    VkSampler * pSampler
)
```


**See**: [https://www.khronos.org/registry/vulkan/specs/1.3/html/vkspec.html#vkCreateSampler](https://www.khronos.org/registry/vulkan/specs/1.3/html/vkspec.html#vkCreateSampler)

### function vkCreateSampler

```cpp
inline vk_result vkCreateSampler(
    const VkSamplerCreateInfo * pCreateInfo,
    VkSampler * pSampler
)
```


**See**: [https://www.khronos.org/registry/vulkan/specs/1.3/html/vkspec.html#vkCreateSampler](https://www.khronos.org/registry/vulkan/specs/1.3/html/vkspec.html#vkCreateSampler)

### function vkCreateShaderModule

```cpp
inline vk_result vkCreateShaderModule(
    const VkShaderModuleCreateInfo * pCreateInfo,
    const VkAllocationCallbacks * pAllocator,
    VkShaderModule * pShaderModule
)
```


**See**: [https://www.khronos.org/registry/vulkan/specs/1.3/html/vkspec.html#vkCreateShaderModule](https://www.khronos.org/registry/vulkan/specs/1.3/html/vkspec.html#vkCreateShaderModule)

### function vkCreateShaderModule

```cpp
inline vk_result vkCreateShaderModule(
    const VkShaderModuleCreateInfo * pCreateInfo,
    VkShaderModule * pShaderModule
)
```


**See**: [https://www.khronos.org/registry/vulkan/specs/1.3/html/vkspec.html#vkCreateShaderModule](https://www.khronos.org/registry/vulkan/specs/1.3/html/vkspec.html#vkCreateShaderModule)

### function vkCreateFence

```cpp
inline vk_result vkCreateFence(
    const VkFenceCreateInfo * pCreateInfo,
    const VkAllocationCallbacks * pAllocator,
    VkFence * pFence
)
```


**See**: [https://www.khronos.org/registry/vulkan/specs/1.3/html/vkspec.html#vkCreateFence](https://www.khronos.org/registry/vulkan/specs/1.3/html/vkspec.html#vkCreateFence)

### function vkCreateFence

```cpp
inline vk_result vkCreateFence(
    const VkFenceCreateInfo * pCreateInfo,
    VkFence * pFence
)
```


**See**: [https://www.khronos.org/registry/vulkan/specs/1.3/html/vkspec.html#vkCreateFence](https://www.khronos.org/registry/vulkan/specs/1.3/html/vkspec.html#vkCreateFence)

### function vkCreateSemaphore

```cpp
inline vk_result vkCreateSemaphore(
    const VkSemaphoreCreateInfo * pCreateInfo,
    const VkAllocationCallbacks * pAllocator,
    VkSemaphore * pSemaphore
)
```


**See**: [https://www.khronos.org/registry/vulkan/specs/1.3/html/vkspec.html#vkCreateSemaphore](https://www.khronos.org/registry/vulkan/specs/1.3/html/vkspec.html#vkCreateSemaphore)

### function vkCreateSemaphore

```cpp
inline vk_result vkCreateSemaphore(
    const VkSemaphoreCreateInfo * pCreateInfo,
    VkSemaphore * pSemaphore
)
```


**See**: [https://www.khronos.org/registry/vulkan/specs/1.3/html/vkspec.html#vkCreateSemaphore](https://www.khronos.org/registry/vulkan/specs/1.3/html/vkspec.html#vkCreateSemaphore)

### function vkWaitForFences

```cpp
inline vk_result vkWaitForFences(
    uint32_t fenceCount,
    const VkFence * pFences,
    VkBool32 waitAll,
    uint64_t timeout
)
```


**See**: [https://www.khronos.org/registry/vulkan/specs/1.3/html/vkspec.html#vkWaitForFences](https://www.khronos.org/registry/vulkan/specs/1.3/html/vkspec.html#vkWaitForFences)

### function vkResetFences

```cpp
inline vk_result vkResetFences(
    uint32_t fenceCount,
    const VkFence * pFences
)
```


**See**: [https://www.khronos.org/registry/vulkan/specs/1.3/html/vkspec.html#vkResetFences](https://www.khronos.org/registry/vulkan/specs/1.3/html/vkspec.html#vkResetFences)

### function vkQueueSubmit

```cpp
inline vk_result vkQueueSubmit(
    VkQueue queue,
    uint32_t submitCount,
    const VkSubmitInfo * pSubmits,
    VkFence fence
)
```


**See**: [https://www.khronos.org/registry/vulkan/specs/1.3/html/vkspec.html#vkQueueSubmit](https://www.khronos.org/registry/vulkan/specs/1.3/html/vkspec.html#vkQueueSubmit)

### function vkAcquireNextImageKHR

```cpp
inline vk_result vkAcquireNextImageKHR(
    VkSwapchainKHR swapchain,
    uint64_t timeout,
    VkSemaphore semaphore,
    VkFence fence,
    uint32_t * pImageIndex
)
```


**See**: [https://www.khronos.org/registry/vulkan/specs/1.3-extensions/man/html/vkAcquireNextImageKHR.html](https://www.khronos.org/registry/vulkan/specs/1.3-extensions/man/html/vkAcquireNextImageKHR.html)

### function vkQueuePresentKHR

```cpp
inline vk_result vkQueuePresentKHR(
    VkQueue queue,
    const VkPresentInfoKHR * pPresentInfo
)
```


**See**: [https://www.khronos.org/registry/vulkan/specs/1.3-extensions/man/html/vkQueuePresentKHR.html](https://www.khronos.org/registry/vulkan/specs/1.3-extensions/man/html/vkQueuePresentKHR.html)

### function vkCreateSwapchainKHR

```cpp
inline vk_result vkCreateSwapchainKHR(
    const VkSwapchainCreateInfoKHR * pCreateInfo,
    const VkAllocationCallbacks * pAllocator,
    VkSwapchainKHR * pSwapchain
)
```


**See**: [https://www.khronos.org/registry/vulkan/specs/1.3-extensions/man/html/vkCreateSwapchainKHR.html](https://www.khronos.org/registry/vulkan/specs/1.3-extensions/man/html/vkCreateSwapchainKHR.html)

### function vkCreateSwapchainKHR

```cpp
inline vk_result vkCreateSwapchainKHR(
    const VkSwapchainCreateInfoKHR * pCreateInfo,
    VkSwapchainKHR * pSwapchain
)
```


**See**: [https://www.khronos.org/registry/vulkan/specs/1.3-extensions/man/html/vkCreateSwapchainKHR.html](https://www.khronos.org/registry/vulkan/specs/1.3-extensions/man/html/vkCreateSwapchainKHR.html)

### function vkDestroySwapchainKHR

```cpp
inline void vkDestroySwapchainKHR(
    VkSwapchainKHR swapchain,
    const VkAllocationCallbacks * pAllocator =memory::instance().alloc()
)
```


**See**: [https://www.khronos.org/registry/vulkan/specs/1.3-extensions/man/html/vkDestroySwapchainKHR.html](https://www.khronos.org/registry/vulkan/specs/1.3-extensions/man/html/vkDestroySwapchainKHR.html)

### function vkGetSwapchainImagesKHR

```cpp
inline vk_result vkGetSwapchainImagesKHR(
    VkSwapchainKHR swapchain,
    uint32_t * pSwapchainImageCount,
    VkImage * pSwapchainImages
)
```


**See**: [https://www.khronos.org/registry/vulkan/specs/1.3-extensions/man/html/vkGetSwapchainImagesKHR.html](https://www.khronos.org/registry/vulkan/specs/1.3-extensions/man/html/vkGetSwapchainImagesKHR.html)

### function vkCreateCommandPool

```cpp
inline vk_result vkCreateCommandPool(
    const VkCommandPoolCreateInfo * pCreateInfo,
    const VkAllocationCallbacks * pAllocator,
    VkCommandPool * pCommandPool
)
```


**See**: [https://www.khronos.org/registry/vulkan/specs/1.3/html/vkspec.html#vkCreateCommandPool](https://www.khronos.org/registry/vulkan/specs/1.3/html/vkspec.html#vkCreateCommandPool)

### function vkCreateCommandPool

```cpp
inline vk_result vkCreateCommandPool(
    const VkCommandPoolCreateInfo * pCreateInfo,
    VkCommandPool * pCommandPool
)
```


**See**: [https://www.khronos.org/registry/vulkan/specs/1.3/html/vkspec.html#vkCreateCommandPool](https://www.khronos.org/registry/vulkan/specs/1.3/html/vkspec.html#vkCreateCommandPool)

### function vkCreateCommandPool

```cpp
inline vk_result vkCreateCommandPool(
    index queue_family,
    VkCommandPool * pCommandPool
)
```


**See**: [https://www.khronos.org/registry/vulkan/specs/1.3/html/vkspec.html#vkCreateCommandPool](https://www.khronos.org/registry/vulkan/specs/1.3/html/vkspec.html#vkCreateCommandPool)

### function vkAllocateCommandBuffers

```cpp
inline vk_result vkAllocateCommandBuffers(
    const VkCommandBufferAllocateInfo * pAllocateInfo,
    VkCommandBuffer * pCommandBuffers
)
```


**See**: [https://www.khronos.org/registry/vulkan/specs/1.3/html/vkspec.html#vkAllocateCommandBuffers](https://www.khronos.org/registry/vulkan/specs/1.3/html/vkspec.html#vkAllocateCommandBuffers)

### function vkAllocateCommandBuffers

```cpp
inline vk_result vkAllocateCommandBuffers(
    VkCommandPool commandPool,
    uint32_t commandBufferCount,
    VkCommandBuffer * pCommandBuffers,
    VkCommandBufferLevel level =VK_COMMAND_BUFFER_LEVEL_PRIMARY
)
```


**See**: [https://www.khronos.org/registry/vulkan/specs/1.3/html/vkspec.html#vkAllocateCommandBuffers](https://www.khronos.org/registry/vulkan/specs/1.3/html/vkspec.html#vkAllocateCommandBuffers)

### function vkDestroyImageView

```cpp
inline void vkDestroyImageView(
    VkImageView imageView,
    const VkAllocationCallbacks * pAllocator =memory::instance().alloc()
)
```


**See**: [https://www.khronos.org/registry/vulkan/specs/1.3/html/vkspec.html#vkDestroyImageView](https://www.khronos.org/registry/vulkan/specs/1.3/html/vkspec.html#vkDestroyImageView)

### function vkDestroyFence

```cpp
inline void vkDestroyFence(
    VkFence fence,
    const VkAllocationCallbacks * pAllocator =memory::instance().alloc()
)
```


**See**: [https://www.khronos.org/registry/vulkan/specs/1.3/html/vkspec.html#vkDestroyFence](https://www.khronos.org/registry/vulkan/specs/1.3/html/vkspec.html#vkDestroyFence)

### function vkDestroySemaphore

```cpp
inline void vkDestroySemaphore(
    VkSemaphore semaphore,
    const VkAllocationCallbacks * pAllocator =memory::instance().alloc()
)
```


**See**: [https://www.khronos.org/registry/vulkan/specs/1.3/html/vkspec.html#vkDestroySemaphore](https://www.khronos.org/registry/vulkan/specs/1.3/html/vkspec.html#vkDestroySemaphore)

### function vkFreeCommandBuffers

```cpp
inline void vkFreeCommandBuffers(
    VkCommandPool commandPool,
    uint32_t commandBufferCount,
    const VkCommandBuffer * pCommandBuffers
)
```


**See**: [https://www.khronos.org/registry/vulkan/specs/1.3/html/vkspec.html#vkFreeCommandBuffers](https://www.khronos.org/registry/vulkan/specs/1.3/html/vkspec.html#vkFreeCommandBuffers)

### function vkDestroyCommandPool

```cpp
inline void vkDestroyCommandPool(
    VkCommandPool commandPool,
    const VkAllocationCallbacks * pAllocator =memory::instance().alloc()
)
```


**See**: [https://www.khronos.org/registry/vulkan/specs/1.3/html/vkspec.html#vkDestroyCommandPool](https://www.khronos.org/registry/vulkan/specs/1.3/html/vkspec.html#vkDestroyCommandPool)

### function vkDestroySampler

```cpp
inline void vkDestroySampler(
    VkSampler sampler,
    const VkAllocationCallbacks * pAllocator =memory::instance().alloc()
)
```


**See**: [https://www.khronos.org/registry/vulkan/specs/1.3/html/vkspec.html#vkDestroySampler](https://www.khronos.org/registry/vulkan/specs/1.3/html/vkspec.html#vkDestroySampler)

### function vkUpdateDescriptorSets

```cpp
inline void vkUpdateDescriptorSets(
    uint32_t descriptorWriteCount,
    const VkWriteDescriptorSet * pDescriptorWrites,
    uint32_t descriptorCopyCount =0,
    const VkCopyDescriptorSet * pDescriptorCopies =nullptr
)
```


**See**: [https://www.khronos.org/registry/vulkan/specs/1.3/html/vkspec.html#vkUpdateDescriptorSets](https://www.khronos.org/registry/vulkan/specs/1.3/html/vkspec.html#vkUpdateDescriptorSets)

### function vkUpdateDescriptorSets

```cpp
template <std::size_t SIZE>
inline void vkUpdateDescriptorSets(
    std::array< VkWriteDescriptorSet, SIZE > const & descriptor_writes
)
```


**See**: [https://www.khronos.org/registry/vulkan/specs/1.3/html/vkspec.html#vkUpdateDescriptorSets](https://www.khronos.org/registry/vulkan/specs/1.3/html/vkspec.html#vkUpdateDescriptorSets)

### function vkUpdateDescriptorSets

```cpp
template <std::size_t SIZE>
inline void vkUpdateDescriptorSets(
    std::array< VkCopyDescriptorSet, SIZE > const & descriptor_copies
)
```


**See**: [https://www.khronos.org/registry/vulkan/specs/1.3/html/vkspec.html#vkUpdateDescriptorSets](https://www.khronos.org/registry/vulkan/specs/1.3/html/vkspec.html#vkUpdateDescriptorSets)

### function vkUpdateDescriptorSets

```cpp
template <std::size_t WRITE_SIZE,
std::size_t COPY_SIZE>
inline void vkUpdateDescriptorSets(
    std::array< VkWriteDescriptorSet, WRITE_SIZE > const & descriptor_writes,
    std::array< VkCopyDescriptorSet, COPY_SIZE > const & descriptor_copies
)
```


**See**: [https://www.khronos.org/registry/vulkan/specs/1.3/html/vkspec.html#vkUpdateDescriptorSets](https://www.khronos.org/registry/vulkan/specs/1.3/html/vkspec.html#vkUpdateDescriptorSets)

### function vkUpdateDescriptorSets

```cpp
inline void vkUpdateDescriptorSets(
    std::initializer_list< VkWriteDescriptorSet > descriptor_writes
)
```


**See**: [https://www.khronos.org/registry/vulkan/specs/1.3/html/vkspec.html#vkUpdateDescriptorSets](https://www.khronos.org/registry/vulkan/specs/1.3/html/vkspec.html#vkUpdateDescriptorSets)

### function vkUpdateDescriptorSets

```cpp
inline void vkUpdateDescriptorSets(
    std::initializer_list< VkCopyDescriptorSet > descriptor_copies
)
```


**See**: [https://www.khronos.org/registry/vulkan/specs/1.3/html/vkspec.html#vkUpdateDescriptorSets](https://www.khronos.org/registry/vulkan/specs/1.3/html/vkspec.html#vkUpdateDescriptorSets)

### function vkUpdateDescriptorSets

```cpp
inline void vkUpdateDescriptorSets(
    std::initializer_list< VkWriteDescriptorSet > descriptor_writes,
    std::initializer_list< VkCopyDescriptorSet > descriptor_copies
)
```


**See**: [https://www.khronos.org/registry/vulkan/specs/1.3/html/vkspec.html#vkUpdateDescriptorSets](https://www.khronos.org/registry/vulkan/specs/1.3/html/vkspec.html#vkUpdateDescriptorSets)

## Public Attributes Documentation

### variable vk_device

```cpp
VkDevice vk_device = nullptr;
```

Vulkan device. 

### variable table

```cpp
VolkDeviceTable table = {};
```

Volk device table. 

-------------------------------

Updated on 2026-02-01 at 18:13:39 +0000