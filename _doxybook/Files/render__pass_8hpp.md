---
title: liblava/block/render_pass.hpp
summary: Render pass. 

---

# liblava/block/render_pass.hpp

Render pass.  [More...](#detailed-description)

## Namespaces

| Name           |
| -------------- |
| **[lava](/_doxybook/Namespaces/namespacelava.md)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| struct | **[lava::render_pass](/_doxybook/Classes/structlava_1_1render__pass.md)** <br>Render pass.  |

## Detailed Description

Render pass. 

**Author**: Lava Block OÜ and contributors 

**Copyright**: Copyright (c) 2018-present, MIT License 



## Source code

```cpp

#pragma once

#include "liblava/base/device.hpp"
#include "liblava/block/attachment.hpp"
#include "liblava/block/subpass.hpp"

namespace lava {

struct render_pass : entity {
    using ptr = std::shared_ptr<render_pass>;

    using list = std::vector<ptr>;

    static ptr make(device_p device) {
        return std::make_shared<render_pass>(device);
    }

    explicit render_pass(device_p device);

    bool create(VkAttachmentsRef target_attachments,
                rect::ref area);

    void destroy();

    void process(VkCommandBuffer cmd_buf,
                 index frame);

    device_p get_device() {
        return device;
    }

    VkRenderPass get() const {
        return vk_render_pass;
    }

    ui32 get_subpass_count() const {
        return to_ui32(subpasses.size());
    }

    bool exists_subpass(index index = 0) const {
        return index < subpasses.size();
    }

    subpass* get_subpass(index index = 0) {
        return subpasses.at(index).get();
    }

    subpass::list const& get_subpasses() const {
        return subpasses;
    }

    void add(attachment::ptr const& attachment) {
        attachments.push_back(attachment);
    }

    void add(subpass_dependency::ptr const& dependency) {
        dependencies.push_back(dependency);
    }

    void add(subpass::ptr const& subpass) {
        subpasses.push_back(subpass);
    }

    void set_clear_values(VkClearValues const& values) {
        clear_values = values;
    }

    VkClearValues const& get_clear_values() const {
        return clear_values;
    }

    void set_clear_color(v3 value = {});

    v3 get_clear_color() const;

    void add(render_pipeline::ptr pipeline,
             index subpass = 0) {
        subpasses.at(subpass)->add(pipeline);
    }

    void add_front(render_pipeline::ptr pipeline,
                   index subpass = 0) {
        subpasses.at(subpass)->add_front(pipeline);
    }

    void remove(render_pipeline::ptr pipeline,
                index subpass = 0) {
        subpasses.at(subpass)->remove(pipeline);
    }

    target_callback const& get_target_callback() const {
        return callback;
    }

private:
    device_p device = nullptr;

    VkRenderPass vk_render_pass = VK_NULL_HANDLE;

    VkFramebuffers framebuffers = {};

    attachment::list attachments;

    subpass_dependency::list dependencies;

    subpass::list subpasses;

    VkClearValues clear_values = {};

    rect area;

    target_callback callback;

    void begin(VkCommandBuffer cmd_buf,
               index frame);

    void end(VkCommandBuffer cmd_buf);

    bool on_target_created(VkAttachmentsRef target_attachments,
                           rect::ref area);

    void on_target_destroyed();
};

} // namespace lava
```


-------------------------------

Updated on 2024-03-22 at 21:51:38 +0000
