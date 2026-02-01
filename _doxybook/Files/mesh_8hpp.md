---
title: liblava/resource/mesh.hpp
summary: Vulkan mesh. 

---

# liblava/resource/mesh.hpp

Vulkan mesh.  [More...](#detailed-description)

## Namespaces

| Name           |
| -------------- |
| **[lava](/_doxybook/Namespaces/namespacelava.md)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| struct | **[lava::mesh_template_data](/_doxybook/Classes/structlava_1_1mesh__template__data.md)** <br>Templated mesh data.  |
| struct | **[lava::mesh_template](/_doxybook/Classes/structlava_1_1mesh__template.md)** <br>Temporary templated mesh.  |
| struct | **[lava::mesh_meta](/_doxybook/Classes/structlava_1_1mesh__meta.md)** <br>Mesh meta.  |

## Detailed Description

Vulkan mesh. 

**Author**: Lava Block OÜ and contributors 

**Copyright**: Copyright (c) 2018-present, MIT License 



## Source code

```cpp


#pragma once

#include "liblava/core/misc.hpp"
#include "liblava/resource/buffer.hpp"
#include "liblava/resource/primitive.hpp"
#include "liblava/util/hex.hpp"
#include "liblava/util/log.hpp"

namespace lava {

template <typename T = vertex>
struct mesh_template_data {
    std::vector<T> vertices;

    index_list indices;

    template <typename PosType = r32>
    void move(std::array<PosType, 3> offset) {
        for (T& vertex : vertices) {
            for (auto i = 0u; i < 3; ++i) {
                vertex.position[i] += offset[i];
            }
        }
    }

    void scale(auto factor) {
        for (T& vertex : vertices) {
            for (auto i = 0u; i < 3; ++i) {
                vertex.position[i] *= factor;
            }
        }
    }

    template <typename PosType = r32>
    void scale_vector(std::array<PosType, 3> factors) {
        for (T& vertex : vertices) {
            for (auto i = 0u; i < 3; ++i) {
                vertex.position[i] *= factors[i];
            }
        }
    }
};

template <typename T = vertex>
struct mesh_template : entity {
    using s_ptr = std::shared_ptr<mesh_template<T>>;

    using s_map = std::map<id, s_ptr>;

    using s_list = std::vector<s_ptr>;

    using vertex_list = std::vector<T>;

    static s_ptr make() {
        return std::make_shared<mesh_template<T>>();
    }

    ~mesh_template() {
        destroy();
    }

    bool create(device::ptr device,
                bool mapped = false,
                VmaMemoryUsage memory_usage = VMA_MEMORY_USAGE_CPU_TO_GPU);

    void destroy();

    void bind(VkCommandBuffer cmd_buf) const;

    void draw(VkCommandBuffer cmd_buf) const;

    void bind_draw(VkCommandBuffer cmd_buf) const {
        bind(cmd_buf);
        draw(cmd_buf);
    }

    bool empty() const {
        return m_data.vertices.empty();
    }

    void set_data(mesh_template_data<T> const& value) {
        m_data = value;
    }

    mesh_template_data<T>& get_data() {
        return m_data;
    }

    void add_data(mesh_template_data<T> const& value) {
        m_data = value;
    }

    vertex_list& get_vertices() {
        return m_data.vertices;
    }

    vertex_list const& get_vertices() const {
        return m_data.vertices;
    }

    ui32 get_vertices_count() const {
        return to_ui32(m_data.vertices.size());
    }

    index_list& get_indices() {
        return m_data.indices;
    }

    index_list const& get_indices() const {
        return m_data.indices;
    }

    ui32 get_indices_count() const {
        return to_ui32(m_data.indices.size());
    }

    bool reload();

    buffer::s_ptr get_vertex_buffer() {
        return m_vertex_buffer;
    }

    buffer::s_ptr get_index_buffer() {
        return m_index_buffer;
    }

private:
    device::ptr m_device = nullptr;

    mesh_template_data<T> m_data;

    buffer::s_ptr m_vertex_buffer;

    buffer::s_ptr m_index_buffer;

    bool m_mapped = false;

    VmaMemoryUsage m_memory_usage = VMA_MEMORY_USAGE_CPU_TO_GPU;
};

//-----------------------------------------------------------------------------
template <typename T>
void mesh_template<T>::bind(VkCommandBuffer cmd_buf) const {
    if (m_vertex_buffer && m_vertex_buffer->valid()) {
        std::array<VkDeviceSize, 1> const buffer_offsets = {0};
        std::array<VkBuffer, 1> const buffers = {m_vertex_buffer->get()};

        vkCmdBindVertexBuffers(cmd_buf, 0,
                               to_ui32(buffers.size()), buffers.data(),
                               buffer_offsets.data());
    }

    if (m_index_buffer && m_index_buffer->valid())
        vkCmdBindIndexBuffer(cmd_buf,
                             m_index_buffer->get(),
                             0,
                             VK_INDEX_TYPE_UINT32);
}

//-----------------------------------------------------------------------------
template <typename T>
void mesh_template<T>::draw(VkCommandBuffer cmd_buf) const {
    if (!m_data.indices.empty())
        vkCmdDrawIndexed(cmd_buf,
                         to_ui32(m_data.indices.size()),
                         1, 0, 0, 0);
    else
        vkCmdDraw(cmd_buf,
                  to_ui32(m_data.vertices.size()),
                  1, 0, 0);
}

//-----------------------------------------------------------------------------
template <typename T>
void mesh_template<T>::destroy() {
    m_vertex_buffer = nullptr;
    m_index_buffer = nullptr;
    m_device = nullptr;
}

//-----------------------------------------------------------------------------
template <typename T>
bool mesh_template<T>::reload() {
    auto dev = m_device;
    destroy();

    return create(dev, m_mapped, m_memory_usage);
}

template <typename T = vertex,
          bool generate_colors = true,
          bool generate_normals = true,
          bool generate_uvs = true,
          bool has_colors = true,
          bool has_normals = true,
          bool has_uvs = true>
mesh_template_data<T> create_mesh_data(mesh_type type);

template <typename T = vertex,
          bool generate_colors = true,
          bool generate_normals = true,
          bool generate_uvs = true,
          bool has_colors = true,
          bool has_normals = true,
          bool has_uvs = true>
std::shared_ptr<mesh_template<T>> create_mesh(device::ptr& device,
                                              mesh_type type);

//-----------------------------------------------------------------------------
template <typename T>
bool mesh_template<T>::create(device::ptr dev,
                              bool m,
                              VmaMemoryUsage mu) {
    m_device = dev;
    m_mapped = m;
    m_memory_usage = mu;

    if (!m_data.vertices.empty()) {
        m_vertex_buffer = buffer::make();

        if (!m_vertex_buffer->create(m_device,
                                     m_data.vertices.data(),
                                     sizeof(T) * m_data.vertices.size(),
                                     VK_BUFFER_USAGE_VERTEX_BUFFER_BIT,
                                     m_mapped,
                                     m_memory_usage)) {
            logger()->error("create mesh vertex buffer");
            return false;
        }
    }

    if (!m_data.indices.empty()) {
        m_index_buffer = buffer::make();

        if (!m_index_buffer->create(m_device,
                                    m_data.indices.data(),
                                    sizeof(ui32) * m_data.indices.size(),
                                    VK_BUFFER_USAGE_INDEX_BUFFER_BIT,
                                    m_mapped,
                                    m_memory_usage)) {
            logger()->error("create mesh index buffer");
            return false;
        }
    }

    return true;
}

template <typename PosType, size_t vert_count, bool is_complex>
constexpr std::array<PosType, vert_count> make_primitive_positions_cube();

//-----------------------------------------------------------------------------
// NOTE: The C++20 spec allows std::vector<T> to be constexpr
// g++ does not currently implement this feature, however
//-----------------------------------------------------------------------------

template <bool is_complex>
std::vector<index> make_primitive_indices_cube();

template <typename NormType>
constexpr std::array<NormType, 6> make_primitive_normals_cube();

template <typename UVType>
constexpr std::array<UVType, 24> make_primitive_uvs_cube();

//-----------------------------------------------------------------------------
template <typename T,
          bool generate_colors,
          bool generate_normals,
          bool generate_uvs,
          bool has_colors,
          bool has_normals,
          bool has_uvs>
std::shared_ptr<mesh_template<T>> create_mesh(device::ptr& device,
                                              mesh_type type) {
    std::shared_ptr<mesh_template<T>> return_mesh =
        std::make_shared<mesh_template<T>>();

    return_mesh->add_data(create_mesh_data<T,
                                           generate_colors,
                                           generate_normals,
                                           generate_uvs,
                                           has_colors,
                                           has_normals,
                                           has_uvs>(type));
    return_mesh->create(device);
    return return_mesh;
}

//-----------------------------------------------------------------------------
template <typename T,
          bool generate_colors,
          bool generate_normals,
          bool generate_uvs,
          bool has_colors,
          bool has_normals,
          bool has_uvs>
mesh_template_data<T> create_mesh_data(mesh_type type) {
    mesh_template_data<T> return_mesh_data;

    constexpr bool auto_position = requires(const T t) {
        t.position;
    };
    static_assert(auto_position,
                  "Vertex struct `T` must contain field `position`");

    constexpr bool auto_colors = requires(const T t) {
        t.color;
    };
    constexpr bool auto_normals = requires(const T t) {
        t.normal;
    };
    constexpr bool auto_uvs = requires(const T t) {
        t.uv;
    };

    using PosType = decltype(T::position);

    switch (type) {
    case mesh_type::cube: {
        return_mesh_data.indices.reserve(36);
        return_mesh_data.indices = make_primitive_indices_cube<(generate_normals
                                                                && auto_normals)>();
        constexpr size_t vert_count = (generate_normals && auto_normals) ? 24 : 8;
        return_mesh_data.vertices.reserve(vert_count);
        auto positions = make_primitive_positions_cube<PosType, vert_count,
                                                       (generate_normals && auto_normals)>();
        for (size_t i = 0; i < vert_count; i++) {
            T vert;
            vert.position = positions[i];
            if constexpr (generate_normals && auto_normals) {
                // this array is generated inside of every loop because
                // that makes the scoping rules simplest to follow
                // my expectation is that a compiler should be able
                // to trivially optimize this
                using NormType = decltype(T::normal);
                auto normals = make_primitive_normals_cube<NormType>();
                vert.normal = normals[i / 4];
            }
            if constexpr (generate_uvs && auto_uvs) {
                using UVType = decltype(T::uv);
                auto uvs = make_primitive_uvs_cube<UVType>();
                vert.uv = uvs[i];
            }
            return_mesh_data.vertices.push_back(vert);
        }
        break;
    }

    case mesh_type::triangle: {
        return_mesh_data.vertices.reserve(3);
        T vert_one;
        vert_one.position = {1, 1, 0};
        T vert_two;
        vert_two.position = {-1, 1, 0};
        T vert_three;
        vert_three.position = {0, -1, 0};
        if constexpr (generate_uvs && auto_uvs) {
            vert_one.uv = {1, 1};
            vert_two.uv = {0, 1};
            vert_three.uv = {0.5, 0};
        }
        if constexpr (generate_normals && auto_normals) {
            vert_one.normal = {1, 1, 0};
            vert_two.normal = {-1, 1, 0};
            vert_three.normal = {0, -1, 0};
        }
        return_mesh_data.vertices.push_back(vert_one);
        return_mesh_data.vertices.push_back(vert_two);
        return_mesh_data.vertices.push_back(vert_three);
        break;
    }

    case mesh_type::quad: {
        return_mesh_data.vertices.reserve(4);
        return_mesh_data.indices.reserve(6);
        T vert_one;
        vert_one.position = {1, 1, 0};
        T vert_two;
        vert_two.position = {-1, 1, 0};
        T vert_three;
        vert_three.position = {-1, -1, 0};
        T vert_four;
        vert_four.position = {1, -1, 0};
        if constexpr (generate_uvs && auto_uvs) {
            vert_one.uv = {1, 1};
            vert_two.uv = {0, 1};
            vert_three.uv = {0, 0};
            vert_four.uv = {1, 0};
        }
        if constexpr (generate_normals && auto_normals) {
            vert_one.normal = {0, 0, 1};
            vert_two.normal = {0, 0, 1};
            vert_three.normal = {0, 0, 1};
            vert_four.normal = {0, 0, 1};
        }
        // clang-format off
        return_mesh_data.indices = {
            0, 1, 2,
            2, 3, 0,
        };
        // clang-format on
        return_mesh_data.vertices.push_back(vert_one);
        return_mesh_data.vertices.push_back(vert_two);
        return_mesh_data.vertices.push_back(vert_three);
        return_mesh_data.vertices.push_back(vert_four);
        break;
    }

    case mesh_type::hexagon: {
        return_mesh_data.vertices.reserve(7);
        return_mesh_data.indices.reserve(18);
        hex_layout layout;
        layout.orientation = hex_layout_point_y;
        layout.size = {1, 1};
        auto hex_corners = hex_polygon_corners(layout, {});
        T vert_center;
        vert_center.position = {0, 0, 0};
        T vert_sw;
        PosType temp;
        temp[0] = hex_corners.at(0).x;
        temp[1] = hex_corners.at(0).y;
        temp[2] = 0;
        vert_sw.position = temp;
        T vert_nw;
        temp[0] = hex_corners.at(1).x;
        temp[1] = hex_corners.at(1).y;
        vert_nw.position = temp;
        T vert_n;
        temp[0] = hex_corners.at(2).x;
        temp[1] = hex_corners.at(2).y;
        vert_n.position = temp;
        T vert_ne;
        temp[0] = hex_corners.at(3).x;
        temp[1] = hex_corners.at(3).y;
        vert_ne.position = temp;
        T vert_se;
        temp[0] = hex_corners.at(4).x;
        temp[1] = hex_corners.at(4).y;
        vert_se.position = temp;
        T vert_s;
        temp[0] = hex_corners.at(5).x;
        temp[1] = hex_corners.at(5).y;
        vert_s.position = temp;
        if constexpr (generate_uvs && auto_uvs) {
            vert_center.uv = {0, 0};
            vert_sw.uv = {1, 0};
            vert_nw.uv = {0, 1};
            vert_n.uv = {1, 1};
            vert_ne.uv = {1, 0};
            vert_se.uv = {0, 1};
            vert_s.uv = {1, 1};
        }
        if constexpr (generate_normals && auto_normals) {
            vert_center.normal = {0, 0, 1};
            vert_sw.normal = {0, 0, 1};
            vert_nw.normal = {0, 0, 1};
            vert_n.normal = {0, 0, 1};
            vert_ne.normal = {0, 0, 1};
            vert_se.normal = {0, 0, 1};
            vert_s.normal = {0, 0, 1};
        }
        // clang-format off
        return_mesh_data.indices = {
            0, 1, 6, 0, 6, 5, 0, 5, 4, 0, 4, 3, 0, 3, 2, 0, 2, 1
        };
        // clang-format on
        return_mesh_data.vertices.push_back(vert_center);
        return_mesh_data.vertices.push_back(vert_sw);
        return_mesh_data.vertices.push_back(vert_nw);
        return_mesh_data.vertices.push_back(vert_n);
        return_mesh_data.vertices.push_back(vert_ne);
        return_mesh_data.vertices.push_back(vert_se);
        return_mesh_data.vertices.push_back(vert_s);
        break;
    }

    case mesh_type::none:
    default:
        break;
    }

    if constexpr (generate_colors && auto_colors) {
        for (auto& vert : return_mesh_data.vertices) {
            // this does not work on glm vectors
            // for (auto& this_color : vert.color) {
            //     for (auto& color_component : this_color) {
            //         color_component = 1;
            //     }
            // }
            if constexpr (std::is_same_v<decltype(vert.color), glm::vec3>) {
                vert.color = {1, 1, 1};
            } else if constexpr (std::is_same_v<decltype(vert.color), glm::vec4>) {
                vert.color = {1, 1, 1, 1};
            } else {
                for (size_t i = 0; i < vert.color.size(); i++) {
                    vert.color[i] = 1;
                }
            }
        }
    }

    return return_mesh_data;
}

//-----------------------------------------------------------------------------
template <typename PosType,
          size_t vert_count,
          bool is_complex>
constexpr std::array<PosType, vert_count> make_primitive_positions_cube() {
    // clang-format off
    if constexpr (is_complex) {
        std::array<PosType, 24> const positions = {{
            // front
            { 1, 1, 1 }, { -1, 1, 1}, { -1, -1, 1 }, { 1, -1, 1 },
            // back
            { 1, 1, -1 }, { -1, 1, -1 }, { -1, -1, -1 }, { 1, -1, -1 },
            // left
            { -1, 1, 1 }, { -1, 1, -1 }, { -1, -1, -1 }, { -1, -1, 1 },
            // right
            { 1, 1, 1 }, { 1, -1, 1 }, { 1, -1, -1 }, { 1, 1, -1 },
            // bottom
            { 1, 1, 1 }, { -1, 1, 1 }, { -1, 1, -1 }, { 1, 1, -1 },
            // top
            { 1, -1, 1 }, { -1, -1, 1 }, { -1, -1, -1 }, { 1, -1, -1 },
        }};
        return positions;
    } else {
        std::array<PosType, 8> const positions = {{
            { -1, -1, -1 },
            { -1, -1, 1 },
            { -1, 1, -1 },
            { -1, 1, 1 },
            { 1, -1, -1 },
            { 1, -1, 1 },
            { 1, 1, -1 },
            { 1, 1, 1 },
        }};
        return positions;
    }
    // clang-format on
}

//-----------------------------------------------------------------------------
template <bool is_complex>
std::vector<index> make_primitive_indices_cube() {
    // clang-format off
    if constexpr (is_complex) {
        std::vector<index> const indices = {
            0, 1, 2,
            2, 3, 0,
            4, 7, 6,
            6, 5, 4,
            8, 9, 10,
            10, 11, 8,
            12, 13, 14,
            14, 15, 12,
            16, 19, 18,
            18, 17, 16,
            20, 21, 22,
            22, 23, 20,
        };
        return indices;
    } else {
        // clockwise winding order
        std::vector<index> const indices = {
            // left
            0, 1, 2,
            2, 1, 3,
            // right
            4, 5, 6,
            6, 5, 7,
            // top
            0, 1, 4,
            4, 1, 5,
            // bottom
            2, 3, 6,
            6, 3, 7,
            // back
            3, 1, 5,
            5, 7, 3,
            // front
            2, 0, 4,
            4, 6, 2,
        };
        return indices;
    }
    // clang-format on
}

//-----------------------------------------------------------------------------
template <typename NormType>
constexpr std::array<NormType, 6> make_primitive_normals_cube() {
    // clang-format off
    // front, back, left, right, bottom, and top normals, in that order
    std::array<NormType, 6> const normals = {{ { 0, 0, 1 },  { 0, 0, -1 },
                                               { -1, 0, 0 }, { 1, 0, 0 },
                                               { 0, 1, 0 },  { 0, -1, 0 }, }};
    // clang-format on
    return normals;
}

//-----------------------------------------------------------------------------
template <typename UVType>
constexpr std::array<UVType, 24> make_primitive_uvs_cube() {
    // clang-format off
    std::array<UVType, 24> const uvs = {{
        { 1, 1 }, { 0, 1 }, { 0, 0 }, { 1, 0 }, // front
        { 0, 1 }, { 1, 1 }, { 1, 0 }, { 0, 0 }, // back
        { 1, 1 }, { 0, 1 }, { 0, 0 }, { 1, 0 }, // left
        { 0, 1 }, { 0, 0 }, { 1, 0 }, { 1, 1 }, // right
        { 1, 0 }, { 0, 0 }, { 0, 1 }, { 1, 1 }, // bottom
        { 1, 1 }, { 0, 1 }, { 0, 0 }, { 1, 0 }, // top
    }};
    // clang-format on
    return uvs;
}

using mesh_data = mesh_template_data<vertex>;

using mesh = mesh_template<vertex>;

struct mesh_meta {
    string filename;

    mesh_type type = mesh_type::none;
};

using mesh_registry = id_registry<mesh, mesh_meta>;

} // namespace lava
```


-------------------------------

Updated on 2026-02-01 at 18:13:39 +0000
