---
title: liblava/base/instance.hpp
summary: Vulkan instance. 

---

# liblava/base/instance.hpp

Vulkan instance.  [More...](#detailed-description)

## Namespaces

| Name           |
| -------------- |
| **[lava](/_doxybook/Namespaces/namespacelava.md)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| struct | **[lava::instance_info](/_doxybook/Classes/structlava_1_1instance__info.md)** <br>Vulkan instance information.  |
| struct | **[lava::instance](/_doxybook/Classes/structlava_1_1instance.md)** <br>Vulkan instance.  |
| struct | **[lava::instance::create_param](/_doxybook/Classes/structlava_1_1instance_1_1create__param.md)** <br>Instance create parameters.  |
| struct | **[lava::instance::debug_config](/_doxybook/Classes/structlava_1_1instance_1_1debug__config.md)** <br>Debug configuration.  |

## Detailed Description

Vulkan instance. 

**Author**: Lava Block OÜ and contributors 

**Copyright**: Copyright (c) 2018-present, MIT License 



## Source code

```cpp

#pragma once

#include <liblava/base/physical_device.hpp>

namespace lava {

struct instance_info {
    using ref = instance_info const&;

    name app_name = _lava_;

    name engine_name = _liblava_;

    int_version app_version;

    int_version engine_version;

    api_version req_api_version = api_version::v1_0;
};

struct instance : no_copy_no_move {
    struct create_param {
        using ref = create_param const&;

        names layers{};

        names extensions{};
    };

    struct debug_config {
        using ref = debug_config const&;

        bool validation = false;

        bool render_doc = false;

        bool verbose = false;

        bool utils = false;
    };

    static instance& singleton() {
        static instance instance;
        return instance;
    }

    bool create(create_param& param,
                debug_config::ref debug,
                instance_info::ref info);

    void destroy();

    physical_device::list const& get_physical_devices() const {
        return physical_devices;
    }

    physical_device::ref get_first_physical_device() const {
        return *physical_devices.front().get();
    }

    VkInstance get() const {
        return vk_instance;
    }

    debug_config::ref get_debug_config() const {
        return debug;
    }

    instance_info::ref get_info() const {
        return info;
    }

private:
    explicit instance() = default;

    ~instance();

    bool check_debug(create_param& param) const;

    bool enumerate_physical_devices();

    bool create_validation_report();

    void destroy_validation_report();

    VkInstance vk_instance = nullptr;

    physical_device::list physical_devices;

    debug_config debug;

    instance_info info;

    VkDebugUtilsMessengerEXT debug_messenger = VK_NULL_HANDLE;
};

bool check(instance::create_param::ref param);

int_version get_instance_version();

VkLayerPropertiesList enumerate_layer_properties();

VkExtensionPropertiesList enumerate_extension_properties(name layer_name = nullptr);

} // namespace lava
```


-------------------------------

Updated on 2022-11-30 at 01:16:04 +0000
