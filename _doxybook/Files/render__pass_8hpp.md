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
    using s_ptr = std::shared_ptr<render_pass>;

    using s_list = std::vector<s_ptr>;

    static s_ptr make(device::ptr device) {
        return std::make_shared<render_pass>(device);
    }

    explicit render_pass(device::ptr device);

    bool create(VkAttachmentsRef target_attachments,
                rect::ref area);

    void destroy();

    void process(VkCommandBuffer cmd_buf,
                 index frame);

    device::ptr get_device() {
        return m_device;
    }

    VkRenderPass get() const {
        return m_vk_render_pass;
    }

    ui32 get_subpass_count() const {
        return to_ui32(m_subpasses.size());
    }

    bool exists_subpass(index index = 0) const {
        return index < m_subpasses.size();
    }

    subpass* get_subpass(index index = 0) {
        return m_subpasses.at(index).get();
    }

    subpass::s_list const& get_subpasses() const {
        return m_subpasses;
    }

    void add(attachment::s_ptr const& attachment) {
        m_attachments.push_back(attachment);
    }

    void add(subpass_dependency::s_ptr const& dependency) {
        m_dependencies.push_back(dependency);
    }

    void add(subpass::s_ptr const& subpass) {
        m_subpasses.push_back(subpass);
    }

    void set_clear_values(VkClearValues const& values) {
        m_clear_values = values;
    }

    VkClearValues const& get_clear_values() const {
        return m_clear_values;
    }

    void set_clear_color(v3 value = {});

    v3 get_clear_color() const;

    void add(render_pipeline::s_ptr pipeline,
             index subpass = 0) {
        m_subpasses.at(subpass)->add(pipeline);
    }

    void add_front(render_pipeline::s_ptr pipeline,
                   index subpass = 0) {
        m_subpasses.at(subpass)->add_front(pipeline);
    }

    void remove(render_pipeline::s_ptr pipeline,
                index subpass = 0) {
        m_subpasses.at(subpass)->remove(pipeline);
    }

    target_callback const& get_target_callback() const {
        return m_callback;
    }

private:
    device::ptr m_device = nullptr;

    VkRenderPass m_vk_render_pass = VK_NULL_HANDLE;

    VkFramebuffers m_framebuffers = {};

    attachment::s_list m_attachments;

    subpass_dependency::s_list m_dependencies;

    subpass::s_list m_subpasses;

    VkClearValues m_clear_values = {};

    rect m_area;

    target_callback m_callback;

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

Updated on 2026-02-01 at 18:13:39 +0000
