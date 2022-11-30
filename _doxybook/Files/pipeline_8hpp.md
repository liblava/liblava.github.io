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

#include <liblava/block/pipeline_layout.hpp>

namespace lava {

struct pipeline : entity {
    using ptr = std::shared_ptr<pipeline>;

    using list = std::vector<ptr>;

    using process_func = std::function<void(VkCommandBuffer)>;

    process_func on_process;

    explicit pipeline(device_p device,
                      VkPipelineCache pipeline_cache = 0);

    ~pipeline() override;

    bool create();

    void destroy();

    virtual void bind(VkCommandBuffer cmd_buf) = 0;

    void set_active(bool value = true) {
        active = value;
    }

    bool activated() const {
        return active;
    }

    void toggle() {
        active = !active;
    }

    void set_auto_bind(bool value = true) {
        auto_bind_active = value;
    }

    bool auto_bind() const {
        return auto_bind_active;
    }

    bool ready() const {
        return vk_pipeline != VK_NULL_HANDLE;
    }

    VkPipeline get() const {
        return vk_pipeline;
    }

    device_p get_device() {
        return device;
    }

    pipeline_layout::ptr get_layout() const {
        return layout;
    }

    void set_layout(pipeline_layout::ptr const& value) {
        layout = value;
    }

    struct shader_stage {
        using ptr = std::shared_ptr<shader_stage>;

        using list = std::vector<ptr>;

        static ptr make(VkShaderStageFlagBits stage) {
            auto result = std::make_shared<shader_stage>();
            result->set_stage(stage);
            return result;
        }

        explicit shader_stage();

        ~shader_stage();

        void set_stage(VkShaderStageFlagBits stage) {
            create_info.stage = stage;
        }

        void add_specialization_entry(VkSpecializationMapEntry const& specialization);

        bool create(device_p device,
                    cdata::ref shader_data,
                    cdata::ref specialization_data = data());

        void destroy();

        VkPipelineShaderStageCreateInfo const& get_create_info() const {
            return create_info;
        }

    private:
        device_p device = nullptr;

        VkPipelineShaderStageCreateInfo create_info;

        VkSpecializationInfo specialization_info;

        VkSpecializationMapEntries specialization_entries;

        data specialization_data_copy;
    };

protected:
    virtual bool setup() = 0;

    virtual void teardown() = 0;

    device_p device = nullptr;

    VkPipeline vk_pipeline = VK_NULL_HANDLE;

    VkPipelineCache pipeline_cache = VK_NULL_HANDLE;

    pipeline_layout::ptr layout;

private:
    bool active = true;

    bool auto_bind_active = true;
};

pipeline::shader_stage::ptr create_pipeline_shader_stage(device_p device,
                                                         cdata::ref data,
                                                         VkShaderStageFlagBits stage);

} // namespace lava
```


-------------------------------

Updated on 2022-11-30 at 01:16:04 +0000
