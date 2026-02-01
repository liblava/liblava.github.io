---
title: liblava/frame/renderer.hpp
summary: Plain renderer. 

---

# liblava/frame/renderer.hpp

Plain renderer.  [More...](#detailed-description)

## Namespaces

| Name           |
| -------------- |
| **[lava](/_doxybook/Namespaces/namespacelava.md)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| struct | **[lava::renderer](/_doxybook/Classes/structlava_1_1renderer.md)** <br>Plain renderer.  |

## Detailed Description

Plain renderer. 

**Author**: Lava Block OÜ and contributors 

**Copyright**: Copyright (c) 2018-present, MIT License 



## Source code

```cpp


#pragma once

#include "liblava/frame/swapchain.hpp"
#include <optional>

namespace lava {

using optional_index = std::optional<index>;

struct renderer : entity {
    using ptr = renderer*;

    bool create(swapchain* target);

    void destroy();

    optional_index begin_frame();

    bool end_frame(VkCommandBuffers const& cmd_buffers);

    bool frame(VkCommandBuffers const& cmd_buffers) {
        if (!begin_frame())
            return false;

        return end_frame(cmd_buffers);
    }

    index get_frame() const {
        return m_current_frame;
    }

    device::ptr get_device() {
        return m_device;
    }

    VkSemaphores user_frame_wait_semaphores;

    VkPipelineStageFlagsList user_frame_wait_stages;

    VkSemaphores user_frame_signal_semaphores;

    using destroy_func = std::function<void()>;

    destroy_func on_destroy;

    bool active = true;

private:
    device::ptr m_device = nullptr;

    queue m_graphics_queue;

    swapchain* m_target = nullptr;

    index m_current_frame = 0;

    ui32 m_queued_frames = 2;

    ui32 m_current_sync = 0;

    VkFences m_fences = {};

    VkFences m_fences_in_use = {};

    VkSemaphores m_image_acquired_semaphores = {};

    VkSemaphores m_render_complete_semaphores = {};
};

} // namespace lava
```


-------------------------------

Updated on 2026-02-01 at 18:13:39 +0000
