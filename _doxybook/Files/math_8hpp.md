---
title: liblava/util/math.hpp
summary: Math helpers. 

---

# liblava/util/math.hpp

Math helpers.  [More...](#detailed-description)

## Namespaces

| Name           |
| -------------- |
| **[lava](/_doxybook/Namespaces/namespacelava.md)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| struct | **[lava::rect](/_doxybook/Classes/structlava_1_1rect.md)** <br>Rectangle.  |

## Defines

|                | Name           |
| -------------- | -------------- |
|  | **[GLM_FORCE_RADIANS](/_doxybook/Files/math_8hpp.md#define-glm-force-radians)**  |
|  | **[GLM_FORCE_DEPTH_ZERO_TO_ONE](/_doxybook/Files/math_8hpp.md#define-glm-force-depth-zero-to-one)**  |

## Detailed Description

Math helpers. 

**Author**: Lava Block OÜ and contributors 

**Copyright**: Copyright (c) 2018-present, MIT License 



## Macros Documentation

### define GLM_FORCE_RADIANS

```cpp
#define GLM_FORCE_RADIANS 
```


### define GLM_FORCE_DEPTH_ZERO_TO_ONE

```cpp
#define GLM_FORCE_DEPTH_ZERO_TO_ONE 
```


## Source code

```cpp


#pragma once

#include "liblava/core/types.hpp"
#include "picosha2.h"

#define GLM_FORCE_RADIANS
#define GLM_FORCE_DEPTH_ZERO_TO_ONE
#include "glm/glm.hpp"
#include "glm/gtc/matrix_transform.hpp"
#include "glm/gtc/type_ptr.hpp"

namespace lava {

using v2 = glm::vec2;

using v3 = glm::vec3;

using v4 = glm::vec4;

using uv2 = glm::uvec2;

using mat3 = glm::mat3;

using mat4 = glm::mat4;

using iv2 = glm::ivec2;

using iv3 = glm::ivec3;

struct rect {
    using ref = rect const&;

    rect() = default;

    rect(i32 left, i32 top,
         ui32 width, ui32 height)
    : m_left_top({left, top}) {
        set_size({width, height});
    }

    rect(iv2 const& left_top,
         ui32 width, ui32 height)
    : m_left_top(left_top) {
        set_size({width, height});
    }

    rect(iv2 const& left_top,
         uv2 const& size)
    : m_left_top(left_top) {
        set_size(size);
    }

    iv2 const& get_origin() const {
        return m_left_top;
    }

    iv2 const& get_end_point() const {
        return m_right_bottom;
    }

    uv2 get_size() const {
        LAVA_ASSERT(m_left_top.x <= m_right_bottom.x);
        LAVA_ASSERT(m_left_top.y <= m_right_bottom.y);
        return {m_right_bottom.x - m_left_top.x,
                m_right_bottom.y - m_left_top.y};
    }

    void set_size(uv2 const& size) {
        m_right_bottom.x = m_left_top.x + size.x;
        m_right_bottom.y = m_left_top.y + size.y;
    }

    void move(iv2 const& offset) {
        m_left_top += offset;
        m_right_bottom += offset;
    }

    bool contains(iv2 point) const {
        return (m_left_top.x < point.x)
               && (m_left_top.y < point.y)
               && (m_right_bottom.x > point.x)
               && (m_right_bottom.y > point.y);
    }

private:
    iv2 m_left_top = iv2();

    iv2 m_right_bottom = iv2();
};

inline auto ceil_div(auto x, auto y) {
    return (x + y - 1) / y;
}

v3 const default_color = v3{0.8118f,
                            0.0627f,
                            0.1255f};

inline mat4 perspective_matrix(uv2 size,
                               r32 fov = 90.f,
                               r32 far_plane = 5.f) {
    // Vulkan NDC is right-handed with Y pointing down
    // we flip Y which makes it left-handed
    return glm::scale(glm::identity<glm::mat4>(),
                      {1.f, -1.f, 1.f})
           * glm::perspectiveLH_ZO(
               glm::radians(fov),
               r32(size.x) / size.y,
               0.1f,
               far_plane);
}

inline string hash256(string_ref value) {
    std::vector<uc8> hash(picosha2::k_digest_size);
    picosha2::hash256(value.begin(), value.end(),
                      hash.begin(), hash.end());

    return picosha2::bytes_to_hex_string(hash.begin(), hash.end());
}

} // namespace lava
```


-------------------------------

Updated on 2026-02-01 at 18:13:39 +0000
