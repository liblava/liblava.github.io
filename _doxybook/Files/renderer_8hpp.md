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

#include <liblava/frame/swapchain.hpp>
#include <optional>

namespace lava {

using optional_index = std::optional<index>;

struct renderer : entity {
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
        return current_frame;
    }

    device_p get_device() {
        return device;
    }

    using destroy_func = std::function<void()>;

    destroy_func on_destroy;

    bool active = true;

private:
    device_p device = nullptr;

    queue graphics_queue;

    swapchain* target = nullptr;

    index current_frame = 0;

    ui32 queued_frames = 2;

    ui32 current_sync = 0;

    VkFences fences = {};

    VkFences fences_in_use = {};

    VkSemaphores image_acquired_semaphores = {};

    VkSemaphores render_complete_semaphores = {};
};

using renderer_t = renderer;

} // namespace lava
```


-------------------------------

Updated on 2022-11-30 at 01:16:04 +0000
