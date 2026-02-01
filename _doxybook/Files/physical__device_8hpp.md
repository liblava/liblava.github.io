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
    using s_ptr = std::shared_ptr<physical_device>;

    using s_list = std::vector<s_ptr>;

    using ref = physical_device const&;

    static s_ptr make(VkPhysicalDevice vk_physical_device) {
        return std::make_shared<physical_device>(vk_physical_device);
    }

    physical_device() = default;

    physical_device(VkPhysicalDevice vk_physical_device);

    void initialize(VkPhysicalDevice vk_physical_device);

    bool supported(string_ref extension) const;

    bool get_queue_family(index& index, VkQueueFlags flags) const;

    device::create_param create_default_device_param() const;

    VkPhysicalDeviceProperties const& get_properties() const {
        return m_properties;
    }

    VkPhysicalDeviceFeatures const& get_features() const {
        return m_features;
    }

    VkPhysicalDeviceMemoryProperties const& get_memory_properties() const {
        return m_memory_properties;
    }

    VkQueueFamilyPropertiesList const& get_queue_family_properties() const {
        return m_queue_family_properties;
    }

    VkExtensionPropertiesList const& get_extension_properties() const {
        return m_extension_properties;
    }

    VkPhysicalDevice get() const {
        return m_vk_physical_device;
    }

    name get_device_name() const;

    string get_device_type_string() const;

    sem_version get_driver_version() const;

    bool swapchain_supported() const;

    bool surface_supported(index queue_family,
                           VkSurfaceKHR surface) const;

private:
    VkPhysicalDevice m_vk_physical_device = nullptr;

    VkPhysicalDeviceProperties m_properties = {};

    VkPhysicalDeviceFeatures m_features = {};

    VkPhysicalDeviceMemoryProperties m_memory_properties = {};

    VkQueueFamilyPropertiesList m_queue_family_properties;

    VkExtensionPropertiesList m_extension_properties;
};

} // namespace lava
```


-------------------------------

Updated on 2026-02-01 at 18:13:39 +0000
