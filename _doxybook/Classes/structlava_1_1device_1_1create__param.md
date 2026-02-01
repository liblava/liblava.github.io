---
title: lava::device::create_param
summary: Device create parameters. 

---

# lava::device::create_param



Device create parameters. 


`#include <device.hpp>`

## Public Types

|                | Name           |
| -------------- | -------------- |
| using [create_param](/_doxybook/Classes/structlava_1_1device_1_1create__param.md) const  & | **[ref](/_doxybook/Classes/structlava_1_1device_1_1create__param.md#using-ref)** <br>Reference to device create parameters.  |

## Public Functions

|                | Name           |
| -------------- | -------------- |
| void | **[add_swapchain_extension](/_doxybook/Classes/structlava_1_1device_1_1create__param.md#function-add-swapchain-extension)**()<br>Add swapchain extension.  |
| void | **[add_portability_subset_extension](/_doxybook/Classes/structlava_1_1device_1_1create__param.md#function-add-portability-subset-extension)**()<br>Add portability subset extension.  |
| void | **[set_default_queues](/_doxybook/Classes/structlava_1_1device_1_1create__param.md#function-set-default-queues)**()<br>Set the default queues.  |
| void | **[set_all_queues](/_doxybook/Classes/structlava_1_1device_1_1create__param.md#function-set-all-queues)**()<br>Set the all queues.  |
| bool | **[add_queue](/_doxybook/Classes/structlava_1_1device_1_1create__param.md#function-add-queue)**(VkQueueFlags flags, [r32](/_doxybook/Namespaces/namespacelava.md#using-r32) priority =1.f)<br>Add queue.  |
| bool | **[add_queues](/_doxybook/Classes/structlava_1_1device_1_1create__param.md#function-add-queues)**(VkQueueFlags flags, [ui32](/_doxybook/Namespaces/namespacelava.md#using-ui32) count, [r32](/_doxybook/Namespaces/namespacelava.md#using-r32) priority =1.f)<br>Add queues.  |
| bool | **[add_dedicated_queues](/_doxybook/Classes/structlava_1_1device_1_1create__param.md#function-add-dedicated-queues)**([r32](/_doxybook/Namespaces/namespacelava.md#using-r32) priority =1.f)<br>Add all dedicated queues.  |
| [verify_queues_result](/_doxybook/Namespaces/namespacelava.md#enum-verify-queues-result) | **[verify_queues](/_doxybook/Classes/structlava_1_1device_1_1create__param.md#function-verify-queues)**() const<br>Verify queues.  |

## Public Attributes

|                | Name           |
| -------------- | -------------- |
| [physical_device_c_ptr](/_doxybook/Classes/structlava_1_1device.md#using-physical-device-c-ptr) | **[physical_device](/_doxybook/Classes/structlava_1_1device_1_1create__param.md#variable-physical-device)** <br>Physical device.  |
| VmaAllocatorCreateFlags | **[vma_flags](/_doxybook/Classes/structlava_1_1device_1_1create__param.md#variable-vma-flags)** <br>VMA flags.  |
| [names](/_doxybook/Namespaces/namespacelava.md#using-names) | **[extensions](/_doxybook/Classes/structlava_1_1device_1_1create__param.md#variable-extensions)** <br>List of extensions to enable.  |
| VkPhysicalDeviceFeatures | **[features](/_doxybook/Classes/structlava_1_1device_1_1create__param.md#variable-features)** <br>List of physical device features to enable.  |
| bool | **[has_features_2](/_doxybook/Classes/structlava_1_1device_1_1create__param.md#variable-has-features-2)** <br>Must be true if .next points to a VkPhysicalDevice2 instance.  |
| void const  * | **[next](/_doxybook/Classes/structlava_1_1device_1_1create__param.md#variable-next)** <br>Create parameter next pointer (pNext)  |
| [queue_family_info::list](/_doxybook/Classes/structlava_1_1queue__family__info.md#using-list) | **[queue_family_infos](/_doxybook/Classes/structlava_1_1device_1_1create__param.md#variable-queue-family-infos)** <br>List of queue famiy infos.  |

## Public Types Documentation

### using ref

```cpp
using lava::device::create_param::ref =  create_param const&;
```

Reference to device create parameters. 

## Public Functions Documentation

### function add_swapchain_extension

```cpp
inline void add_swapchain_extension()
```

Add swapchain extension. 

### function add_portability_subset_extension

```cpp
inline void add_portability_subset_extension()
```

Add portability subset extension. 

### function set_default_queues

```cpp
inline void set_default_queues()
```

Set the default queues. 

### function set_all_queues

```cpp
void set_all_queues()
```

Set the all queues. 

### function add_queue

```cpp
inline bool add_queue(
    VkQueueFlags flags,
    r32 priority =1.f
)
```

Add queue. 

**Parameters**: 

  * **flags** Queue flags 
  * **priority** Priority for queue 


**Return**: Add was successful or failed 

### function add_queues

```cpp
bool add_queues(
    VkQueueFlags flags,
    ui32 count,
    r32 priority =1.f
)
```

Add queues. 

**Parameters**: 

  * **flags** Queue flags 
  * **count** Number of queues 
  * **priority** Priority for queues 


**Return**: Add was successful or failed 

### function add_dedicated_queues

```cpp
bool add_dedicated_queues(
    r32 priority =1.f
)
```

Add all dedicated queues. 

**Parameters**: 

  * **priority** Priority for queues 


**Return**: Add was successful or failed 

### function verify_queues

```cpp
verify_queues_result verify_queues() const
```

Verify queues. 

**Return**: [verify_queues_result](/_doxybook/Namespaces/namespacelava.md#enum-verify-queues-result) Verification result 

## Public Attributes Documentation

### variable physical_device

```cpp
physical_device_c_ptr physical_device = nullptr;
```

Physical device. 

### variable vma_flags

```cpp
VmaAllocatorCreateFlags vma_flags = 0;
```

VMA flags. 

### variable extensions

```cpp
names extensions;
```

List of extensions to enable. 

### variable features

```cpp
VkPhysicalDeviceFeatures features {};
```

List of physical device features to enable. 

### variable has_features_2

```cpp
bool has_features_2 = false;
```

Must be true if .next points to a VkPhysicalDevice2 instance. 

### variable next

```cpp
void const  * next = nullptr;
```

Create parameter next pointer (pNext) 

### variable queue_family_infos

```cpp
queue_family_info::list queue_family_infos;
```

List of queue famiy infos. 

-------------------------------

Updated on 2026-02-01 at 18:13:39 +0000