---
title: liblava/resource/primitive.hpp
summary: Vulkan primitives. 

---

# liblava/resource/primitive.hpp

Vulkan primitives.  [More...](#detailed-description)

## Namespaces

| Name           |
| -------------- |
| **[lava](/_doxybook/Namespaces/namespacelava.md)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| struct | **[lava::vertex](/_doxybook/Classes/structlava_1_1vertex.md)** <br>Vertex.  |

## Detailed Description

Vulkan primitives. 

**Author**: Lava Block OÜ and contributors 

**Copyright**: Copyright (c) 2018-present, MIT License 



## Source code

```cpp


#pragma once

#include "liblava/util/math.hpp"

namespace lava {

struct vertex {
    using list = std::vector<vertex>;

    v3 position;

    v4 color;

    v2 uv;

    v3 normal;

    bool operator==(vertex const& other) const {
        return position == other.position
               && color == other.color
               && uv == other.uv
               && normal == other.normal;
    }
};

enum class mesh_type : index {
    none = 0,
    cube,
    triangle,
    quad,
    hexagon,
};

} // namespace lava
```


-------------------------------

Updated on 2026-02-01 at 18:13:39 +0000
