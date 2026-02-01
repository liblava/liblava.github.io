---
title: lava::physical_device
summary: Vulkan physical device. 

---

# lava::physical_device



Vulkan physical device. 


`#include <physical_device.hpp>`

Inherits from [lava::entity](/_doxybook/Classes/structlava_1_1entity.md), [lava::no_copy_no_move](/_doxybook/Classes/structlava_1_1no__copy__no__move.md), [lava::interface](/_doxybook/Classes/structlava_1_1interface.md)

## Public Types

|                | Name           |
| -------------- | -------------- |
| using std::shared_ptr< [physical_device](/_doxybook/Classes/structlava_1_1physical__device.md) > | **[s_ptr](/_doxybook/Classes/structlava_1_1physical__device.md#using-s-ptr)** <br>Shared pointer to physical device.  |
| using std::vector< [s_ptr](/_doxybook/Classes/structlava_1_1physical__device.md#using-s-ptr) > | **[s_list](/_doxybook/Classes/structlava_1_1physical__device.md#using-s-list)** <br>List of physical devices.  |
| using [physical_device](/_doxybook/Classes/structlava_1_1physical__device.md) const  & | **[ref](/_doxybook/Classes/structlava_1_1physical__device.md#using-ref)** <br>Reference to physical device.  |

## Public Functions

|                | Name           |
| -------------- | -------------- |
| [s_ptr](/_doxybook/Classes/structlava_1_1physical__device.md#using-s-ptr) | **[make](/_doxybook/Classes/structlava_1_1physical__device.md#function-make)**(VkPhysicalDevice vk_physical_device)<br>Make a new physical device.  |
| | **[physical_device](/_doxybook/Classes/structlava_1_1physical__device.md#function-physical-device)**() =default<br>Construct a new physical device.  |
| | **[physical_device](/_doxybook/Classes/structlava_1_1physical__device.md#function-physical-device)**(VkPhysicalDevice vk_physical_device)<br>Construct and initialize a new physical device.  |
| void | **[initialize](/_doxybook/Classes/structlava_1_1physical__device.md#function-initialize)**(VkPhysicalDevice vk_physical_device)<br>Initialize the physical device.  |
| bool | **[supported](/_doxybook/Classes/structlava_1_1physical__device.md#function-supported)**([string_ref](/_doxybook/Namespaces/namespacelava.md#using-string-ref) extension) const<br>Check if extension is supported.  |
| bool | **[get_queue_family](/_doxybook/Classes/structlava_1_1physical__device.md#function-get-queue-family)**([index](/_doxybook/Namespaces/namespacelava.md#using-index) & index, VkQueueFlags flags) const<br>Get the queue family.  |
| [device::create_param](/_doxybook/Classes/structlava_1_1device_1_1create__param.md) | **[create_default_device_param](/_doxybook/Classes/structlava_1_1physical__device.md#function-create-default-device-param)**() const<br>Create default device parameters.  |
| VkPhysicalDeviceProperties const & | **[get_properties](/_doxybook/Classes/structlava_1_1physical__device.md#function-get-properties)**() const<br>Get the properties.  |
| VkPhysicalDeviceFeatures const & | **[get_features](/_doxybook/Classes/structlava_1_1physical__device.md#function-get-features)**() const<br>Get the features.  |
| VkPhysicalDeviceMemoryProperties const & | **[get_memory_properties](/_doxybook/Classes/structlava_1_1physical__device.md#function-get-memory-properties)**() const<br>Get the memory properties.  |
| [VkQueueFamilyPropertiesList](/_doxybook/Namespaces/namespacelava.md#using-vkqueuefamilypropertieslist) const & | **[get_queue_family_properties](/_doxybook/Classes/structlava_1_1physical__device.md#function-get-queue-family-properties)**() const<br>Get the queue family properties.  |
| [VkExtensionPropertiesList](/_doxybook/Namespaces/namespacelava.md#typedef-vkextensionpropertieslist) const & | **[get_extension_properties](/_doxybook/Classes/structlava_1_1physical__device.md#function-get-extension-properties)**() const<br>Get the extension properties.  |
| VkPhysicalDevice | **[get](/_doxybook/Classes/structlava_1_1physical__device.md#function-get)**() const<br>Get the Vulkan physical device.  |
| [name](/_doxybook/Namespaces/namespacelava.md#using-name) | **[get_device_name](/_doxybook/Classes/structlava_1_1physical__device.md#function-get-device-name)**() const<br>Get the device name.  |
| [string](/_doxybook/Namespaces/namespacelava.md#using-string) | **[get_device_type_string](/_doxybook/Classes/structlava_1_1physical__device.md#function-get-device-type-string)**() const<br>Get the device type as string.  |
| [sem_version](/_doxybook/Namespaces/namespacelava.md#using-sem-version) | **[get_driver_version](/_doxybook/Classes/structlava_1_1physical__device.md#function-get-driver-version)**() const<br>Get the driver version.  |
| bool | **[swapchain_supported](/_doxybook/Classes/structlava_1_1physical__device.md#function-swapchain-supported)**() const<br>Check if swapchain is supported.  |
| bool | **[surface_supported](/_doxybook/Classes/structlava_1_1physical__device.md#function-surface-supported)**([index](/_doxybook/Namespaces/namespacelava.md#using-index) queue_family, VkSurfaceKHR surface) const<br>Check if surface is supported.  |

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
using lava::physical_device::s_ptr =  std::shared_ptr<physical_device>;
```

Shared pointer to physical device. 

### using s_list

```cpp
using lava::physical_device::s_list =  std::vector<s_ptr>;
```

List of physical devices. 

### using ref

```cpp
using lava::physical_device::ref =  physical_device const&;
```

Reference to physical device. 

## Public Functions Documentation

### function make

```cpp
static inline s_ptr make(
    VkPhysicalDevice vk_physical_device
)
```

Make a new physical device. 

**Parameters**: 

  * **vk_physical_device** Vulkan physical device 


**Return**: [s_ptr](/_doxybook/Classes/structlava_1_1physical__device.md#using-s-ptr) Shared pointer to physical device 

### function physical_device

```cpp
physical_device() =default
```

Construct a new physical device. 

### function physical_device

```cpp
physical_device(
    VkPhysicalDevice vk_physical_device
)
```

Construct and initialize a new physical device. 

**Parameters**: 

  * **vk_physical_device** Vulkan physical device 


### function initialize

```cpp
void initialize(
    VkPhysicalDevice vk_physical_device
)
```

Initialize the physical device. 

**Parameters**: 

  * **vk_physical_device** Vulkan physical device 


### function supported

```cpp
bool supported(
    string_ref extension
) const
```

Check if extension is supported. 

**Parameters**: 

  * **extension** Extension to check 


**Return**: Extension is supported or not 

### function get_queue_family

```cpp
bool get_queue_family(
    index & index,
    VkQueueFlags flags
) const
```

Get the queue family. 

**Parameters**: 

  * **index** Returned index of queue family 
  * **flags** Queue flags that must be set 


**Return**: Found a queue family or not 

### function create_default_device_param

```cpp
device::create_param create_default_device_param() const
```

Create default device parameters. 

**Return**: [device::create_param](/_doxybook/Classes/structlava_1_1device_1_1create__param.md) Device create parameters 

### function get_properties

```cpp
inline VkPhysicalDeviceProperties const & get_properties() const
```

Get the properties. 

**Return**: VkPhysicalDeviceProperties const& Physical device properties 

### function get_features

```cpp
inline VkPhysicalDeviceFeatures const & get_features() const
```

Get the features. 

**Return**: VkPhysicalDeviceFeatures const& Physical device features 

### function get_memory_properties

```cpp
inline VkPhysicalDeviceMemoryProperties const & get_memory_properties() const
```

Get the memory properties. 

**Return**: VkPhysicalDeviceMemoryProperties const& Physical device memory properties 

### function get_queue_family_properties

```cpp
inline VkQueueFamilyPropertiesList const & get_queue_family_properties() const
```

Get the queue family properties. 

**Return**: [VkQueueFamilyPropertiesList](/_doxybook/Namespaces/namespacelava.md#using-vkqueuefamilypropertieslist) const& List of queue family properties 

### function get_extension_properties

```cpp
inline VkExtensionPropertiesList const & get_extension_properties() const
```

Get the extension properties. 

**Return**: [VkExtensionPropertiesList](/_doxybook/Namespaces/namespacelava.md#typedef-vkextensionpropertieslist) const& List of extension properties 

### function get

```cpp
inline VkPhysicalDevice get() const
```

Get the Vulkan physical device. 

**Return**: VkPhysicalDevice Vulkan physical device 

### function get_device_name

```cpp
name get_device_name() const
```

Get the device name. 

**Return**: name Name of device 

### function get_device_type_string

```cpp
string get_device_type_string() const
```

Get the device type as string. 

**Return**: string String representation of device type 

### function get_driver_version

```cpp
sem_version get_driver_version() const
```

Get the driver version. 

**Return**: [sem_version](/_doxybook/Namespaces/namespacelava.md#using-sem-version) Driver version 

### function swapchain_supported

```cpp
bool swapchain_supported() const
```

Check if swapchain is supported. 

**Return**: Swapchain is supported or not 

### function surface_supported

```cpp
bool surface_supported(
    index queue_family,
    VkSurfaceKHR surface
) const
```

Check if surface is supported. 

**Parameters**: 

  * **queue_family** Index of queue family 
  * **surface** Vulkan surface 


**Return**: Surface is supported or not 

-------------------------------

Updated on 2026-02-01 at 18:13:39 +0000