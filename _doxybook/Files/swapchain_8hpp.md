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
    bool create(device::ptr device,
                VkSurfaceKHR surface,
                VkSurfaceFormatKHR format,
                uv2 size,
                bool v_sync = false,
                bool triple_buffer = true);

    void destroy();

    bool resize(uv2 new_size);

    void request_reload() {
        m_reload_request_active = true;
    }

    bool reload_request() const {
        return m_reload_request_active;
    }

    device::ptr get_device() {
        return m_device;
    }

    uv2 get_size() const {
        return m_size;
    }

    VkFormat get_format() const {
        return m_format.format;
    }

    VkColorSpaceKHR get_color_space() const {
        return m_format.colorSpace;
    }

    VkSwapchainKHR get() const {
        return m_vk_swapchain;
    }

    ui32 get_backbuffer_count() const {
        return to_ui32(m_backbuffers.size());
    }

    image::s_list const& get_backbuffers() const {
        return m_backbuffers;
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
        return m_v_sync_active;
    }

    bool triple_buffer() const {
        return m_triple_buffer_active;
    }

    bool surface_supported(index queue_family) const;

private:
    VkPresentModeKHR choose_present_mode(VkPresentModeKHRs const& present_modes) const;

    VkSwapchainCreateInfoKHR create_info(VkPresentModeKHRs present_modes);

    bool setup();

    void teardown();

    void destroy_backbuffer_views();

    device::ptr m_device = nullptr;

    VkSurfaceKHR m_surface = VK_NULL_HANDLE;

    VkSurfaceFormatKHR m_format = {};

    VkSwapchainKHR m_vk_swapchain = VK_NULL_HANDLE;

    image::s_list m_backbuffers;

    uv2 m_size;

    bool m_reload_request_active = false;

    bool m_v_sync_active = false;

    bool m_triple_buffer_active = true;

    callback::list m_callbacks;
};

} // namespace lava
```


-------------------------------

Updated on 2026-02-01 at 18:13:39 +0000
