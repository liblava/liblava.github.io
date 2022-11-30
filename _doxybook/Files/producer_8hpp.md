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

#include <liblava/fwd.hpp>
#include <liblava/resource.hpp>

namespace lava {

constexpr name _shader_path_ = "shader/";

constexpr name _temp_path_ = "temp/";

constexpr name _hash_json_ = "hash.json";

struct producer {
    engine* context = nullptr;

    mesh::ptr create_mesh(mesh_type mesh_type);

    mesh::ptr get_mesh(string_ref name);

    bool add_mesh(mesh::ptr mesh);

    texture::ptr create_texture(uv2 size);

    texture::ptr get_texture(string_ref name);

    bool add_texture(texture::ptr product);

    cdata get_shader(string_ref name,
                     bool reload = false);

    cdata reload_shader(string_ref name) {
        return get_shader(name, true);
    }

    data compile_shader(cdata product,
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

    shader_map shaders;
};

using producer_t = producer;

} // namespace lava
```


-------------------------------

Updated on 2022-11-30 at 01:16:04 +0000
