---
title: liblava/block/pipeline.hpp
summary: Pipeline. 

---

# liblava/block/pipeline.hpp

Pipeline.  [More...](#detailed-description)

## Namespaces

| Name           |
| -------------- |
| **[lava](/_doxybook/Namespaces/namespacelava.md)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| struct | **[lava::pipeline](/_doxybook/Classes/structlava_1_1pipeline.md)** <br>Pipeline.  |
| struct | **[lava::pipeline::shader_stage](/_doxybook/Classes/structlava_1_1pipeline_1_1shader__stage.md)** <br>Shader stage.  |

## Detailed Description

Pipeline. 

**Author**: Lava Block OÜ and contributors 

**Copyright**: Copyright (c) 2018-present, MIT License 



## Source code

```cpp


#pragma once

#include "liblava/block/pipeline_layout.hpp"

namespace lava {

struct pipeline : entity {
    using s_ptr = std::shared_ptr<pipeline>;

    using s_list = std::vector<s_ptr>;

    using process_func = std::function<void(VkCommandBuffer)>;

    process_func on_process;

    explicit pipeline(device::ptr device,
                      VkPipelineCache pipeline_cache = 0);

    ~pipeline() override;

    bool create();

    void destroy();

    virtual void bind(VkCommandBuffer cmd_buf) = 0;

    void set_active(bool value = true) {
        m_active = value;
    }

    bool activated() const {
        return m_active;
    }

    void toggle() {
        m_active = !m_active;
    }

    void set_auto_bind(bool value = true) {
        m_auto_bind_active = value;
    }

    bool auto_bind() const {
        return m_auto_bind_active;
    }

    bool ready() const {
        return m_vk_pipeline != VK_NULL_HANDLE;
    }

    VkPipeline get() const {
        return m_vk_pipeline;
    }

    device::ptr get_device() {
        return m_device;
    }

    pipeline_layout::s_ptr get_layout() const {
        return m_layout;
    }

    void set_layout(pipeline_layout::s_ptr const& value) {
        m_layout = value;
    }

    struct shader_stage {
        using s_ptr = std::shared_ptr<shader_stage>;

        using s_list = std::vector<s_ptr>;

        static s_ptr make(VkShaderStageFlagBits stage) {
            auto result = std::make_shared<shader_stage>();
            result->set_stage(stage);
            return result;
        }

        explicit shader_stage();

        ~shader_stage();

        void set_stage(VkShaderStageFlagBits stage) {
            m_create_info.stage = stage;
        }

        void add_specialization_entry(VkSpecializationMapEntry const& specialization);

        bool create(device::ptr device,
                    c_data::ref shader_data,
                    c_data::ref specialization_data = data());

        void destroy();

        VkPipelineShaderStageCreateInfo const& get_create_info() const {
            return m_create_info;
        }

    private:
        device::ptr m_device = nullptr;

        VkPipelineShaderStageCreateInfo m_create_info;

        VkSpecializationInfo m_specialization_info;

        VkSpecializationMapEntries m_specialization_entries;

        data m_specialization_data_copy;
    };

protected:
    virtual bool setup() = 0;

    virtual void teardown() = 0;

    device::ptr m_device = nullptr;

    VkPipeline m_vk_pipeline = VK_NULL_HANDLE;

    VkPipelineCache m_pipeline_cache = VK_NULL_HANDLE;

    pipeline_layout::s_ptr m_layout;

private:
    bool m_active = true;

    bool m_auto_bind_active = true;
};

pipeline::shader_stage::s_ptr create_pipeline_shader_stage(device::ptr device,
                                                           c_data::ref data,
                                                           VkShaderStageFlagBits stage);

} // namespace lava
```


-------------------------------

Updated on 2026-02-01 at 18:13:39 +0000
