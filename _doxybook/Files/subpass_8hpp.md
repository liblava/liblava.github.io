---
title: liblava/block/subpass.hpp
summary: Subpass. 

---

# liblava/block/subpass.hpp

Subpass.  [More...](#detailed-description)

## Namespaces

| Name           |
| -------------- |
| **[lava](/_doxybook/Namespaces/namespacelava.md)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| struct | **[lava::subpass](/_doxybook/Classes/structlava_1_1subpass.md)** <br>Subpass.  |
| struct | **[lava::subpass_dependency](/_doxybook/Classes/structlava_1_1subpass__dependency.md)** <br>Subpass dependency.  |

## Detailed Description

Subpass. 

**Author**: Lava Block OÜ and contributors 

**Copyright**: Copyright (c) 2018-present, MIT License 



## Source code

```cpp


#pragma once

#include "liblava/block/render_pipeline.hpp"

namespace lava {

struct subpass : entity {
    using s_ptr = std::shared_ptr<subpass>;

    using s_list = std::vector<s_ptr>;

    static s_ptr make(VkPipelineBindPoint pipeline_bind_point =
                          VK_PIPELINE_BIND_POINT_GRAPHICS) {
        auto result = std::make_shared<subpass>();
        result->set(pipeline_bind_point);
        return result;
    }

    explicit subpass();

    void destroy();

    void add(render_pipeline::s_ptr const& pipeline) {
        m_pipelines.push_back(pipeline);
    }

    void add_front(render_pipeline::s_ptr const& pipeline) {
        m_pipelines.insert(m_pipelines.begin(), pipeline);
    }

    void remove(render_pipeline::s_ptr pipeline);

    void clear_pipelines();

    void process(VkCommandBuffer cmd_buf,
                 uv2 size);

    VkSubpassDescription const& get_description() const {
        return m_description;
    }

    void set(VkPipelineBindPoint pipeline_bind_point) {
        m_description.pipelineBindPoint = pipeline_bind_point;
    }

    void set_color_attachment(index attachment,
                              VkImageLayout layout);

    void set_color_attachment(VkAttachmentReference attachment);

    void set_color_attachments(VkAttachmentReferences const& attachments);

    void set_depth_stencil_attachment(index attachment,
                                      VkImageLayout layout);

    void set_depth_stencil_attachment(VkAttachmentReference attachment);

    void set_input_attachment(index attachment,
                              VkImageLayout layout);

    void set_input_attachment(VkAttachmentReference attachment);

    void set_input_attachments(VkAttachmentReferences const& attachments);

    void set_resolve_attachment(index attachment, VkImageLayout layout);

    void set_resolve_attachment(VkAttachmentReference attachment);

    void set_resolve_attachments(VkAttachmentReferences const& attachments);

    void add_preserve_attachment(index attachment);

    void set_preserve_attachments(index_list const& attachments);

    void set_active(bool value = true) {
        m_active = value;
    }

    bool activated() const {
        return m_active;
    }

private:
    VkSubpassDescription m_description;

    bool m_active = true;

    VkAttachmentReferences m_color_attachments;

    VkAttachmentReference m_depth_stencil_attachment{};

    VkAttachmentReferences m_input_attachments;

    VkAttachmentReferences m_resolve_attachments;

    index_list m_preserve_attachments;

    render_pipeline::s_list m_pipelines;
};

struct subpass_dependency {
    using s_ptr = std::shared_ptr<subpass_dependency>;

    using s_list = std::vector<s_ptr>;

    static s_ptr make(ui32 src_subpass,
                      ui32 dst_subpass,
                      VkDependencyFlags dependency_flags =
                          VK_DEPENDENCY_BY_REGION_BIT) {
        auto result = std::make_shared<subpass_dependency>();
        result->set_subpass(src_subpass, dst_subpass);
        result->set_dependency_flags(dependency_flags);
        return result;
    }

    explicit subpass_dependency();

    VkSubpassDependency const& get_dependency() const {
        return m_dependency;
    }

    void set_subpass(ui32 src, ui32 dst) {
        set_src_subpass(src);
        set_dst_subpass(dst);
    }

    void set_src_subpass(ui32 src) {
        m_dependency.srcSubpass = src;
    }

    void set_dst_subpass(ui32 dst) {
        m_dependency.dstSubpass = dst;
    }

    void set_stage_mask(VkPipelineStageFlags src,
                        VkPipelineStageFlags dst) {
        set_src_stage_mask(src);
        set_dst_stage_mask(dst);
    }

    void set_src_stage_mask(VkPipelineStageFlags mask) {
        m_dependency.srcStageMask = mask;
    }

    void set_dst_stage_mask(VkPipelineStageFlags mask) {
        m_dependency.dstStageMask = mask;
    }

    void set_access_mask(VkAccessFlags src,
                         VkAccessFlags dst) {
        set_src_access_mask(src);
        set_dst_access_mask(dst);
    }

    void set_src_access_mask(VkAccessFlags mask) {
        m_dependency.srcAccessMask = mask;
    }

    void set_dst_access_mask(VkAccessFlags mask) {
        m_dependency.dstAccessMask = mask;
    }

    void set_dependency_flags(VkDependencyFlags flags) {
        m_dependency.dependencyFlags = flags;
    }

private:
    VkSubpassDependency m_dependency;
};

} // namespace lava
```


-------------------------------

Updated on 2026-02-01 at 18:13:39 +0000
