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
| struct | **[lava::file_format](/_doxybook/Classes/structlava_1_1file__format.md)** <br>File format.  |
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

struct file_format {
    using list = std::vector<file_format>;

    string path;

    VkFormat format = VK_FORMAT_UNDEFINED;
};

struct texture : entity {
    using ptr = std::shared_ptr<texture>;

    using map = std::map<id, ptr>;

    using list = std::vector<ptr>;

    struct mip_level {
        using list = std::vector<mip_level>;

        uv2 extent{};

        ui32 size = 0;
    };

    struct layer {
        using list = std::vector<layer>;

        mip_level::list levels;
    };

    static ptr make() {
        return std::make_shared<texture>();
    }

    ~texture() {
        destroy();
    }

    bool create(device_p device,
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
        return &descriptor;
    }

    image::ptr get_image() {
        return img;
    }

    uv2 get_size() const {
        return img ? img->get_size() : uv2();
    }

    texture_type get_type() const {
        return type;
    }

    VkFormat get_format() const {
        return img ? img->get_format() : VK_FORMAT_UNDEFINED;
    }

private:
    image::ptr img;

    texture_type type = texture_type::none;

    layer::list layers;

    VkSampler sampler = 0;

    VkDescriptorImageInfo descriptor = {};

    buffer::ptr upload_buffer;
};

struct staging {
    void add(texture::ptr texture) {
        todo.push_back(texture);
    }

    bool stage(VkCommandBuffer cmd_buf,
               index frame);

    void clear() {
        todo.clear();
        staged.clear();
    }

    bool busy() const {
        return !todo.empty() || !staged.empty();
    }

private:
    texture::list todo;

    using frame_stage_map = std::map<index, texture::list>;

    frame_stage_map staged;
};

using staging_t = staging;

using texture_registry = id_registry<texture, file_format>;

} // namespace lava
```


-------------------------------

Updated on 2024-03-22 at 21:51:38 +0000
