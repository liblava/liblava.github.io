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
    using ptr = std::shared_ptr<compute_pipeline>;

    using map = std::map<id, ptr>;

    using list = std::vector<ptr>;

    static ptr make(device_p device,
                    VkPipelineCache pipeline_cache = 0) {
        return std::make_shared<compute_pipeline>(device, pipeline_cache);
    }

    using pipeline::pipeline;

    void bind(VkCommandBuffer cmdBuffer) override;

    bool set_shader_stage(cdata::ref data,
                          VkShaderStageFlagBits stage);

    void set(shader_stage::ptr const& stage) {
        shader_stage = stage;
    }

    shader_stage::ptr const& get_shader_stage() const {
        return shader_stage;
    }

    void copy_to(compute_pipeline* target) const;

    void copy_from(ptr const& source) {
        source->copy_to(this);
    }

private:
    bool setup() override;

    void teardown() override;

    shader_stage::ptr shader_stage;
};

} // namespace lava
```


-------------------------------

Updated on 2024-03-22 at 21:51:38 +0000
