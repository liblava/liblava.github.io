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

#include <liblava/resource/texture.hpp>

namespace lava {

texture::ptr load_texture(device_p device,
                          file_format file_format,
                          texture_type type = texture_type::tex_2d);

inline texture::ptr load_texture(device_p device,
                                 string_ref filename,
                                 VkFormat format = VK_FORMAT_R8G8B8A8_SRGB,
                                 texture_type type = texture_type::tex_2d) {
    return load_texture(device, { filename, format }, type);
}

texture::ptr create_default_texture(device_p device,
                                    uv2 size = { 512, 512 },
                                    v3 color = v3(1.f),
                                    r32 alpha = 0.7529f);

} // namespace lava
```


-------------------------------

Updated on 2022-11-30 at 01:16:04 +0000
