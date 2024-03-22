---
title: liblava/base/physical_device.hpp
summary: Vulkan physical device. 

---

# liblava/base/physical_device.hpp

Vulkan physical device.  [More...](#detailed-description)

## Namespaces

| Name           |
| -------------- |
| **[lava](/_doxybook/Namespaces/namespacelava.md)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| struct | **[lava::physical_device](/_doxybook/Classes/structlava_1_1physical__device.md)** <br>Vulkan physical device.  |

## Detailed Description

Vulkan physical device. 

**Author**: Lava Block OÜ and contributors 

**Copyright**: Copyright (c) 2018-present, MIT License 



## Source code

```cpp

#pragma once

#include "liblava/base/device.hpp"

namespace lava {

struct physical_device : entity {
    using ptr = std::shared_ptr<physical_device>;

    using list = std::vector<ptr>;

    using ref = physical_device const&;

    static ptr make(VkPhysicalDevice vk_physical_device) {
        return std::make_shared<physical_device>(vk_physical_device);
    }

    physical_device() = default;

    physical_device(VkPhysicalDevice vk_physical_device);

    void initialize(VkPhysicalDevice vk_physical_device);

    bool supported(string_ref extension) const;

    bool get_queue_family(index& index, VkQueueFlags flags) const;

    device::create_param create_default_device_param() const;

    VkPhysicalDeviceProperties const& get_properties() const {
        return properties;
    }

    VkPhysicalDeviceFeatures const& get_features() const {
        return features;
    }

    VkPhysicalDeviceMemoryProperties const& get_memory_properties() const {
        return memory_properties;
    }

    VkQueueFamilyPropertiesList const& get_queue_family_properties() const {
        return queue_family_properties;
    }

    VkExtensionPropertiesList const& get_extension_properties() const {
        return extension_properties;
    }

    VkPhysicalDevice get() const {
        return vk_physical_device;
    }

    name get_device_name() const;

    string get_device_type_string() const;

    sem_version get_driver_version() const;

    bool swapchain_supported() const;

    bool surface_supported(index queue_family,
                           VkSurfaceKHR surface) const;

private:
    VkPhysicalDevice vk_physical_device = nullptr;

    VkPhysicalDeviceProperties properties = {};

    VkPhysicalDeviceFeatures features = {};

    VkPhysicalDeviceMemoryProperties memory_properties = {};

    VkQueueFamilyPropertiesList queue_family_properties;

    VkExtensionPropertiesList extension_properties;
};

} // namespace lava
```


-------------------------------

Updated on 2024-03-22 at 21:51:38 +0000
