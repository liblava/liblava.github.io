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

#include "liblava/block/render_pass.hpp"
#include "liblava/frame/render_target.hpp"

namespace lava {

struct forward_shading {
    explicit forward_shading() = default;

    ~forward_shading() {
        destroy();
    }

    bool create(render_target::s_ptr target);

    void destroy();

    render_pass::s_ptr get_pass() const {
        return m_pass;
    }

    VkRenderPass get_vk_pass() const {
        return m_pass->get();
    }

    image::s_ptr get_depth_stencil() const {
        return m_depth_stencil;
    }

private:
    render_target::s_ptr m_target;

    render_pass::s_ptr m_pass;

    image::s_ptr m_depth_stencil;
};

} // namespace lava
```


-------------------------------

Updated on 2026-02-01 at 18:13:39 +0000
