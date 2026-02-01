---
title: liblava/frame/render_target.hpp
summary: Render target. 

---

# liblava/frame/render_target.hpp

Render target.  [More...](#detailed-description)

## Namespaces

| Name           |
| -------------- |
| **[lava](/_doxybook/Namespaces/namespacelava.md)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| struct | **[lava::render_target](/_doxybook/Classes/structlava_1_1render__target.md)** <br>Render target.  |

## Detailed Description

Render target. 

**Author**: Lava Block OÜ and contributors 

**Copyright**: Copyright (c) 2018-present, MIT License 



## Source code

```cpp


#pragma once

#include "liblava/core/misc.hpp"
#include "liblava/frame/swapchain.hpp"
#include "liblava/fwd.hpp"
#include "liblava/resource/format.hpp"

namespace lava {

struct render_target : entity {
    using s_ptr = std::shared_ptr<render_target>;

    static s_ptr make() {
        return std::make_shared<render_target>();
    }

    bool create(device::ptr device,
                VkSurfaceKHR surface,
                VkSurfaceFormatKHR format,
                uv2 size,
                bool v_sync = false,
                bool triple_buffer = true);

    void destroy();

    uv2 get_size() const {
        return m_target.get_size();
    }

    bool resize(uv2 new_size) {
        return m_target.resize(new_size);
    }

    ui32 get_frame_count() const {
        return m_target.get_backbuffer_count();
    }

    bool reload_request() const {
        return m_target.reload_request();
    }

    void reload() {
        m_target.resize(m_target.get_size());
    }

    device::ptr get_device() {
        return m_target.get_device();
    }

    swapchain* get_swapchain() {
        return &m_target;
    }

    VkFormat get_format() const {
        return m_target.get_format();
    }

    image::s_list const& get_backbuffers() const {
        return m_target.get_backbuffers();
    }

    inline image::s_ptr get_backbuffer(index index) {
        auto& backbuffers = get_backbuffers();
        if (index >= backbuffers.size())
            return nullptr;

        return backbuffers.at(index);
    }

    inline VkImage get_backbuffer_image(index index) {
        auto result = get_backbuffer(index);
        return result ? result->get() : 0;
    }

    inline VkImage get_image(index index) {
        return get_backbuffer_image(index);
    }

    void add_callback(target_callback::c_ptr callback) {
        m_target_callbacks.push_back(callback);
    }

    void remove_callback(target_callback::c_ptr callback) {
        remove(m_target_callbacks, callback);
    }

    using swapchain_start_func = std::function<bool()>;

    swapchain_start_func on_swapchain_start;

    using swapchain_stop_func = std::function<void()>;

    swapchain_stop_func on_swapchain_stop;

    using create_attachments_func = std::function<VkAttachments()>;

    create_attachments_func on_create_attachments;

    using destroy_attachments_func = std::function<void()>;

    destroy_attachments_func on_destroy_attachments;

private:
    swapchain m_target;

    swapchain::callback m_swapchain_callback;

    target_callback::c_list m_target_callbacks;
};

render_target::s_ptr create_target(window* window,
                                   device::ptr device,
                                   bool v_sync = false,
                                   bool triple_buffer = true,
                                   surface_format_request request = {});

inline render_target::s_ptr create_target_v_sync(window* window,
                                                 device::ptr device,
                                                 surface_format_request request = {}) {
    return create_target(window,
                         device,
                         true,
                         true,
                         request);
}

inline render_target::s_ptr create_target_no_triple_buffer(window* window,
                                                           device::ptr device,
                                                           surface_format_request request = {}) {
    return create_target(window,
                         device,
                         false,
                         false,
                         request);
}

} // namespace lava
```


-------------------------------

Updated on 2026-02-01 at 18:13:39 +0000
