---
title: liblava/block/compute_pipeline.hpp
summary: Compute pipeline. 

---

# liblava/block/compute_pipeline.hpp

Compute pipeline.  [More...](#detailed-description)

## Namespaces

| Name           |
| -------------- |
| **[lava](/_doxybook/Namespaces/namespacelava.md)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| struct | **[lava::compute_pipeline](/_doxybook/Classes/structlava_1_1compute__pipeline.md)** <br>Compute pipeline.  |

## Detailed Description

Compute pipeline. 

**Author**: Lava Block OÜ and contributors 

**Copyright**: Copyright (c) 2018-present, MIT License 



## Source code

```cpp


#pragma once

#include "liblava/block/pipeline.hpp"

namespace lava {

struct compute_pipeline : pipeline {
    using s_ptr = std::shared_ptr<compute_pipeline>;

    using s_map = std::map<id, s_ptr>;

    using s_list = std::vector<s_ptr>;

    static s_ptr make(device::ptr device,
                      VkPipelineCache pipeline_cache = 0) {
        return std::make_shared<compute_pipeline>(device, pipeline_cache);
    }

    using pipeline::pipeline;

    void bind(VkCommandBuffer cmdBuffer) override;

    bool set_shader_stage(c_data::ref data,
                          VkShaderStageFlagBits stage);

    void set(shader_stage::s_ptr const& stage) {
        m_shader_stage = stage;
    }

    shader_stage::s_ptr const& get_shader_stage() const {
        return m_shader_stage;
    }

    void copy_to(compute_pipeline* target) const;

    void copy_from(s_ptr const& source) {
        source->copy_to(this);
    }

private:
    bool setup() override;

    void teardown() override;

    shader_stage::s_ptr m_shader_stage;
};

} // namespace lava
```


-------------------------------

Updated on 2026-02-01 at 18:13:39 +0000
