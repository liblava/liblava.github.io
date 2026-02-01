---
title: liblava/asset/load_texture.hpp
summary: Load texture from file. 

---

# liblava/asset/load_texture.hpp

Load texture from file.  [More...](#detailed-description)

## Namespaces

| Name           |
| -------------- |
| **[lava](/_doxybook/Namespaces/namespacelava.md)**  |

## Detailed Description

Load texture from file. 

**Author**: Lava Block OÜ and contributors 

**Copyright**: Copyright (c) 2018-present, MIT License 



## Source code

```cpp


#pragma once

#include "liblava/resource/texture.hpp"

namespace lava {

texture::s_ptr load_texture(device::ptr device,
                            texture_file tex_file,
                            texture_type type = texture_type::tex_2d);

inline texture::s_ptr load_texture(device::ptr device,
                                   string_ref filename,
                                   VkFormat format = VK_FORMAT_R8G8B8A8_SRGB,
                                   texture_type type = texture_type::tex_2d) {
    return load_texture(device, {filename, format}, type);
}

texture::s_ptr create_default_texture(device::ptr device,
                                      uv2 size = {512, 512},
                                      v3 color = v3(1.f),
                                      r32 alpha = 0.7529f);

} // namespace lava
```


-------------------------------

Updated on 2026-02-01 at 18:13:39 +0000
