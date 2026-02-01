---
title: liblava/engine/producer.hpp
summary: Producer. 

---

# liblava/engine/producer.hpp

Producer.  [More...](#detailed-description)

## Namespaces

| Name           |
| -------------- |
| **[lava](/_doxybook/Namespaces/namespacelava.md)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| struct | **[lava::producer](/_doxybook/Classes/structlava_1_1producer.md)** <br>Producer.  |

## Detailed Description

Producer. 

**Author**: Lava Block OÜ and contributors 

**Copyright**: Copyright (c) 2018-present, MIT License 



## Source code

```cpp


#pragma once

#include "liblava/fwd.hpp"
#include "liblava/resource.hpp"

namespace lava {

constexpr name _shader_path_ = "shader/";

constexpr name _temp_path_ = "temp/";

constexpr name _hash_json_ = "hash.json";

struct producer {
    using ptr = producer*;

    engine* app = nullptr;

    mesh::s_ptr create_mesh(mesh_type mesh_type);

    mesh::s_ptr get_mesh(string_ref name);

    bool add_mesh(mesh::s_ptr mesh);

    texture::s_ptr create_texture(uv2 size);

    texture::s_ptr get_texture(string_ref name);

    bool add_texture(texture::s_ptr product);

    c_data get_shader(string_ref name,
                      bool reload = false);

    c_data reload_shader(string_ref name) {
        return get_shader(name, true);
    }

    data compile_shader(c_data product,
                        string_ref name,
                        string_ref filename) const;

    void destroy();

    void clear();

    id_registry<mesh, string> meshes;

    id_registry<texture, string> textures;

    enum shader_optimization : index {
        none = 0,
        size,
        performance
    };

    shader_optimization shader_opt = shader_optimization::performance;

    enum shader_language : index {
        glsl = 0,
        hlsl
    };

    shader_language shader_lang = shader_language::glsl;

    bool shader_debug = false;

private:
    void update_hash(string_ref name,
                     string_map_ref file_hash_map) const;

    bool valid_shader(string_ref name) const;

    using shader_map = std::map<string, data>;

    shader_map m_shaders;
};

} // namespace lava
```


-------------------------------

Updated on 2026-02-01 at 18:13:39 +0000
