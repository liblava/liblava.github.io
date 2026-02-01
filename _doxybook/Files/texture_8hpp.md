---
title: liblava/resource/texture.hpp
summary: Vulkan texture. 

---

# liblava/resource/texture.hpp

Vulkan texture.  [More...](#detailed-description)

## Namespaces

| Name           |
| -------------- |
| **[lava](/_doxybook/Namespaces/namespacelava.md)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| struct | **[lava::texture_file](/_doxybook/Classes/structlava_1_1texture__file.md)** <br>Texture file path with format.  |
| struct | **[lava::texture](/_doxybook/Classes/structlava_1_1texture.md)** <br>Texture.  |
| struct | **[lava::texture::mip_level](/_doxybook/Classes/structlava_1_1texture_1_1mip__level.md)** <br>Texture mip level.  |
| struct | **[lava::texture::layer](/_doxybook/Classes/structlava_1_1texture_1_1layer.md)** <br>Texture layer.  |
| struct | **[lava::staging](/_doxybook/Classes/structlava_1_1staging.md)** <br>Texture staging.  |

## Detailed Description

Vulkan texture. 

**Author**: Lava Block OÜ and contributors 

**Copyright**: Copyright (c) 2018-present, MIT License 



## Source code

```cpp


#pragma once

#include "liblava/resource/buffer.hpp"
#include "liblava/resource/image.hpp"

namespace lava {

enum class texture_type : index {
    none = 0,
    tex_2d,
    array,
    cube_map
};

struct texture_file {
    using list = std::vector<texture_file>;

    string path;

    VkFormat format = VK_FORMAT_UNDEFINED;
};

struct texture : entity {
    using s_ptr = std::shared_ptr<texture>;

    using s_map = std::map<id, s_ptr>;

    using s_list = std::vector<s_ptr>;

    struct mip_level {
        using list = std::vector<mip_level>;

        uv2 extent{};

        ui32 size = 0;
    };

    struct layer {
        using list = std::vector<layer>;

        mip_level::list levels;
    };

    static s_ptr make() {
        return std::make_shared<texture>();
    }

    ~texture() {
        destroy();
    }

    bool create(device::ptr device,
                uv2 size,
                VkFormat format,
                layer::list const& layers = {},
                texture_type type = texture_type::tex_2d);

    void destroy();

    bool upload(void const* data,
                size_t data_size);

    bool stage(VkCommandBuffer cmd_buffer);

    void destroy_upload_buffer();

    VkDescriptorImageInfo const* get_descriptor_info() const {
        return &m_descriptor;
    }

    image::s_ptr get_image() {
        return m_img;
    }

    uv2 get_size() const {
        return m_img ? m_img->get_size() : uv2();
    }

    texture_type get_type() const {
        return m_type;
    }

    VkFormat get_format() const {
        return m_img ? m_img->get_format() : VK_FORMAT_UNDEFINED;
    }

private:
    image::s_ptr m_img;

    texture_type m_type = texture_type::none;

    layer::list m_layers;

    VkSampler m_sampler = 0;

    VkDescriptorImageInfo m_descriptor = {};

    buffer::s_ptr m_upload_buffer;
};

struct staging {
    using ptr = staging*;

    void add(texture::s_ptr texture) {
        m_todo.push_back(texture);
    }

    bool stage(VkCommandBuffer cmd_buf,
               index frame);

    void clear() {
        m_todo.clear();
        m_staged.clear();
    }

    bool busy() const {
        return !m_todo.empty() || !m_staged.empty();
    }

private:
    texture::s_list m_todo;

    using frame_stage_map = std::map<index, texture::s_list>;

    frame_stage_map m_staged;
};

using texture_registry = id_registry<texture, texture_file>;

} // namespace lava
```


-------------------------------

Updated on 2026-02-01 at 18:13:39 +0000
