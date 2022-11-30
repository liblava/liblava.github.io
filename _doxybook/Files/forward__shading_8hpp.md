---
title: liblava/app/forward_shading.hpp
summary: Forward shading. 

---

# liblava/app/forward_shading.hpp

Forward shading.  [More...](#detailed-description)

## Namespaces

| Name           |
| -------------- |
| **[lava](/_doxybook/Namespaces/namespacelava.md)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| struct | **[lava::forward_shading](/_doxybook/Classes/structlava_1_1forward__shading.md)** <br>Forward shading.  |

## Detailed Description

Forward shading. 

**Author**: Lava Block OÜ and contributors 

**Copyright**: Copyright (c) 2018-present, MIT License 



## Source code

```cpp

#pragma once

#include <liblava/block/render_pass.hpp>
#include <liblava/frame/render_target.hpp>

namespace lava {

struct forward_shading {
    explicit forward_shading() = default;

    ~forward_shading() {
        destroy();
    }

    bool create(render_target::ptr target);

    void destroy();

    render_pass::ptr get_pass() const {
        return pass;
    }

    VkRenderPass get_vk_pass() const {
        return pass->get();
    }

    image::ptr get_depth_stencil() const {
        return depth_stencil;
    }

private:
    render_target::ptr target;

    render_pass::ptr pass;

    image::ptr depth_stencil;
};

} // namespace lava
```


-------------------------------

Updated on 2022-11-30 at 01:16:04 +0000
