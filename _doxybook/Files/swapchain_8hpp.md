---
title: liblava/frame/swapchain.hpp
summary: Swapchain. 

---

# liblava/frame/swapchain.hpp

Swapchain.  [More...](#detailed-description)

## Namespaces

| Name           |
| -------------- |
| **[lava](/_doxybook/Namespaces/namespacelava.md)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| struct | **[lava::swapchain](/_doxybook/Classes/structlava_1_1swapchain.md)** <br>Swaphchain.  |
| struct | **[lava::swapchain::callback](/_doxybook/Classes/structlava_1_1swapchain_1_1callback.md)** <br>Swapchain callback.  |

## Detailed Description

Swapchain. 

**Author**: Lava Block OÜ and contributors 

**Copyright**: Copyright (c) 2018-present, MIT License 



## Source code

```cpp

#pragma once

#include "liblava/resource/image.hpp"

namespace lava {

struct swapchain : entity {
    bool create(device_p device,
                VkSurfaceKHR surface,
                VkSurfaceFormatKHR format,
                uv2 size,
                bool v_sync = false,
                bool triple_buffer = true);

    void destroy();

    bool resize(uv2 new_size);

    void request_reload() {
        reload_request_active = true;
    }

    bool reload_request() const {
        return reload_request_active;
    }

    device_p get_device() {
        return device;
    }

    uv2 get_size() const {
        return size;
    }

    VkFormat get_format() const {
        return format.format;
    }

    VkColorSpaceKHR get_color_space() const {
        return format.colorSpace;
    }

    VkSwapchainKHR get() const {
        return vk_swapchain;
    }

    ui32 get_backbuffer_count() const {
        return to_ui32(backbuffers.size());
    }

    image::list const& get_backbuffers() const {
        return backbuffers;
    }

    struct callback {
        using list = std::vector<callback*>;

        using created_func = std::function<bool()>;

        created_func on_created;

        using destroyed_func = std::function<void()>;

        destroyed_func on_destroyed;
    };

    void add_callback(callback* cb);

    void remove_callback(callback* cb);

    bool v_sync() const {
        return v_sync_active;
    }

    bool triple_buffer() const {
        return triple_buffer_active;
    }

    bool surface_supported(index queue_family) const;

private:
    VkPresentModeKHR choose_present_mode(VkPresentModeKHRs const& present_modes) const;

    VkSwapchainCreateInfoKHR create_info(VkPresentModeKHRs present_modes);

    bool setup();

    void teardown();

    void destroy_backbuffer_views();

    device_p device = nullptr;

    VkSurfaceKHR surface = VK_NULL_HANDLE;

    VkSurfaceFormatKHR format = {};

    VkSwapchainKHR vk_swapchain = VK_NULL_HANDLE;

    image::list backbuffers;

    uv2 size;

    bool reload_request_active = false;

    bool v_sync_active = false;

    bool triple_buffer_active = true;

    callback::list callbacks;
};

} // namespace lava
```


-------------------------------

Updated on 2024-03-22 at 21:51:38 +0000
