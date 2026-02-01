---
title: liblava/block/render_pipeline.hpp
summary: Render pipeline (Graphics) 

---

# liblava/block/render_pipeline.hpp

Render pipeline (Graphics)  [More...](#detailed-description)

## Namespaces

| Name           |
| -------------- |
| **[lava](/_doxybook/Namespaces/namespacelava.md)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| struct | **[lava::render_pipeline](/_doxybook/Classes/structlava_1_1render__pipeline.md)** <br>Render pipeline (Graphics)  |
| struct | **[lava::render_pipeline::create_info](/_doxybook/Classes/structlava_1_1render__pipeline_1_1create__info.md)** <br>Render pipeline create information.  |

## Detailed Description

Render pipeline (Graphics) 

**Author**: Lava Block OÜ and contributors 

**Copyright**: Copyright (c) 2018-present, MIT License 



## Source code

```cpp


#pragma once

#include "liblava/block/pipeline.hpp"

namespace lava {

struct render_pipeline : pipeline {
    using s_ptr = std::shared_ptr<render_pipeline>;

    using s_map = std::map<id, s_ptr>;

    using s_list = std::vector<s_ptr>;

    enum class sizing_mode : index {
        input = 0,
        absolute,
        relative
    };

    struct create_info {
        VkPipelineVertexInputStateCreateInfo vertex_input_state;

        VkPipelineInputAssemblyStateCreateInfo input_assembly_state;

        VkPipelineViewportStateCreateInfo viewport_state;

        VkPipelineMultisampleStateCreateInfo multisample_state;

        VkPipelineDepthStencilStateCreateInfo depth_stencil_state;

        VkPipelineRasterizationStateCreateInfo rasterization_state;
    };

    static s_ptr make(device::ptr device,
                      VkPipelineCache pipeline_cache = 0) {
        return std::make_shared<render_pipeline>(device, pipeline_cache);
    }

    explicit render_pipeline(device::ptr device,
                             VkPipelineCache pipeline_cache);

    void bind(VkCommandBuffer cmd_buf) override;

    void set_viewport_and_scissor(VkCommandBuffer cmd_buf,
                                  uv2 size);

    void set_render_pass(VkRenderPass pass) {
        m_render_pass = pass;
    }

    void set(VkRenderPass pass) {
        set_render_pass(pass);
    }

    VkRenderPass get_render_pass() const {
        return m_render_pass;
    }

    index get_subpass() const {
        return m_subpass;
    }

    void set_subpass(index value) {
        m_subpass = value;
    }

    bool create(VkRenderPass pass) {
        set(pass);

        return pipeline::create();
    }

    void set_vertex_input_binding(VkVertexInputBindingDescription const& description);

    void set_vertex_input_bindings(VkVertexInputBindingDescriptions const& descriptions);

    void set_vertex_input_attribute(VkVertexInputAttributeDescription const& attribute);

    void set_vertex_input_attributes(VkVertexInputAttributeDescriptions const& attributes);

    void set_input_topology(VkPrimitiveTopology const& topology);

    void set_depth_test_and_write(bool test_enable = true,
                                  bool write_enable = true);

    void set_depth_compare_op(VkCompareOp compare_op);

    void set_rasterization_cull_mode(VkCullModeFlags cull_mode);

    void set_rasterization_front_face(VkFrontFace front_face);

    void set_rasterization_polygon_mode(VkPolygonMode polygon_mode);

    void add_color_blend_attachment(VkPipelineColorBlendAttachmentState const& attachment);

    void add_color_blend_attachment();

    void clear_color_blend_attachment();

    void set_dynamic_states(VkDynamicStates const& states);

    void add_dynamic_state(VkDynamicState state);

    void clear_dynamic_states();

    bool add_shader_stage(c_data::ref data,
                          VkShaderStageFlagBits stage);

    bool add_shader(c_data::ref data,
                    VkShaderStageFlagBits stage) {
        return add_shader_stage(data, stage);
    }

    void add(shader_stage::s_ptr const& shader_stage) {
        m_shader_stages.push_back(shader_stage);
    }

    shader_stage::s_list const& get_shader_stages() const {
        return m_shader_stages;
    }

    void clear_shader_stages() {
        m_shader_stages.clear();
    }

    void clear() {
        clear_color_blend_attachment();
        clear_shader_stages();
    }

    void set_auto_size(bool value = true) {
        m_auto_size = value;
    }

    bool auto_sizing() const {
        return m_auto_size;
    }

    VkViewport get_viewport() const {
        return m_viewport;
    }

    void set_viewport(VkViewport value) {
        m_viewport = value;
    }

    VkRect2D get_scissor() const {
        return m_scissor;
    }

    void set_scissor(VkRect2D value) {
        m_scissor = value;
    }

    sizing_mode get_sizing() const {
        return m_sizing;
    }

    void set_sizing(sizing_mode value) {
        m_sizing = value;
    }

    void copy_to(render_pipeline* target) const;

    void copy_from(s_ptr const& source) {
        source->copy_to(this);
    }

    void set_line_width(r32 value) {
        m_line_width = value;
    }

    r32 get_line_width() const {
        return m_line_width;
    }

    bool auto_line_width() const {
        return m_auto_line_width_state;
    }

    void set_auto_line_width(bool value = true) {
        m_auto_line_width_state = value;
    }

    void set_line_width(VkCommandBuffer cmd_buf) {
        vkCmdSetLineWidth(cmd_buf, m_line_width);
    }

    using create_func = std::function<bool(create_info&)>;

    create_func on_create;

private:
    bool setup() override;

    void teardown() override;

    VkRenderPass m_render_pass = VK_NULL_HANDLE;

    index m_subpass = 0;

    create_info m_info;

    VkVertexInputBindingDescriptions m_vertex_input_bindings;

    VkVertexInputAttributeDescriptions m_vertex_input_attributes;

    VkPipelineColorBlendAttachmentStates m_color_blend_attachment_states;

    VkPipelineColorBlendStateCreateInfo m_color_blend_state;

    VkPipelineDynamicStateCreateInfo m_dynamic_state;

    VkDynamicStates m_dynamic_states;

    shader_stage::s_list m_shader_stages;

    sizing_mode m_sizing = sizing_mode::input;

    VkViewport m_viewport;

    VkRect2D m_scissor;

    bool m_auto_size = true;

    bool m_auto_line_width_state = false;

    r32 m_line_width = 1.f;
};

VkPipelineColorBlendAttachmentState create_pipeline_color_blend_attachment();

} // namespace lava
```


-------------------------------

Updated on 2026-02-01 at 18:13:39 +0000
