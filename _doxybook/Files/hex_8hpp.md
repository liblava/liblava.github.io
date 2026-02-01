---
title: liblava/util/hex.hpp
summary: Hex point, cell and grid. 

---

# liblava/util/hex.hpp

Hex point, cell and grid.  [More...](#detailed-description)

## Namespaces

| Name           |
| -------------- |
| **[lava](/_doxybook/Namespaces/namespacelava.md)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| struct | **[lava::hex_point](/_doxybook/Classes/structlava_1_1hex__point.md)** <br>Hex point.  |
| struct | **[lava::hex_cell](/_doxybook/Classes/structlava_1_1hex__cell.md)** <br>Hex cell.  |
| struct | **[lava::hex_fractional_cell](/_doxybook/Classes/structlava_1_1hex__fractional__cell.md)** <br>Hex fractional cell.  |
| struct | **[lava::hex_offset_coord](/_doxybook/Classes/structlava_1_1hex__offset__coord.md)** <br>Hex offset coordinates.  |
| struct | **[lava::hex_orientation](/_doxybook/Classes/structlava_1_1hex__orientation.md)** <br>Hex orientation.  |
| struct | **[lava::hex_layout](/_doxybook/Classes/structlava_1_1hex__layout.md)** <br>Hex layout.  |
| struct | **[lava::hex_grid](/_doxybook/Classes/structlava_1_1hex__grid.md)** <br>Hex grid.  |

## Detailed Description

Hex point, cell and grid. 

**See**: [https://www.redblobgames.com/grids/hexagons/](https://www.redblobgames.com/grids/hexagons/)

**Author**: Lava Block OÜ and contributors 

**Copyright**: Copyright (c) 2018-present, MIT License 



## Source code

```cpp


#pragma once

#include "liblava/core/types.hpp"
#include <cmath>
#include <numbers>
#include <unordered_map>

namespace lava {

struct hex_point {
    using list = std::vector<hex_point>;

    r32 x{};

    r32 y{};
};

struct hex_cell {
    using list = std::vector<hex_cell>;

    i32 q{};

    i32 r{};

    i32 s{};

    auto operator<=>(hex_cell const&) const = default;

    using pair = std::pair<i32, i32>;

    using map = std::unordered_map<pair, index, pair_hash>;

    inline pair to_pair() const {
        return {q, r};
    }

    inline void add(hex_cell const& cell) {
        *this = {q + cell.q,
                 r + cell.r,
                 s + cell.s};
    }

    inline void substract(hex_cell const& cell) {
        *this = {q - cell.q,
                 r - cell.r,
                 s - cell.s};
    }

    inline void scale(i32 factor) {
        *this = {q * factor,
                 r * factor,
                 s * factor};
    }

    inline void rotate_left() {
        *this = {-s, -q, -r};
    }

    inline void rotate_right() {
        *this = {-r, -s, -q};
    }
};

inline i32 hex_get_s(i32 q, i32 r) {
    return -q - r;
}

inline hex_cell hex_cell_from_pair(hex_cell::pair const& pair) {
    return {pair.first, pair.second,
            hex_get_s(pair.first, pair.second)};
}

struct hex_fractional_cell {
    r32 q{};

    r32 r{};

    r32 s{};
};

using hex_frac_cell = hex_fractional_cell;

inline bool hex_is_valid(hex_cell const& cell) {
    return cell.q + cell.r + cell.s == 0;
}

struct hex_offset_coord {
    i32 col{};

    i32 row{};
};

using hex_doubled_coord = hex_offset_coord;

struct hex_orientation {
    r32 f0{};

    r32 f1{};

    r32 f2{};

    r32 f3{};

    r32 b0{};

    r32 b1{};

    r32 b2{};

    r32 b3{};

    r32 start_angle{};
};

struct hex_layout {
    hex_orientation orientation;

    hex_point origin;

    hex_point size;
};

hex_cell::list const hex_directions{
    {1, 0, -1},
    {1, -1, 0},
    {0, -1, 1},
    {-1, 0, 1},
    {-1, 1, 0},
    {0, 1, -1}};

inline hex_cell hex_direction(index direction) {
    return hex_directions[direction];
}

inline hex_cell hex_neighbor(hex_cell const& cell,
                             index direction) {
    auto neighbor = cell;
    neighbor.add(hex_direction(direction));
    return neighbor;
}

hex_cell::list const hex_diagonals{
    {2, -1, -1},
    {-1, -2, 1},
    {-1, -1, 2},
    {-2, 1, 1},
    {-1, 2, -1},
    {1, 1, -2}};

inline hex_cell hex_diagonal(index direction) {
    return hex_diagonals[direction];
}

inline hex_cell hex_diagonal_neighbor(hex_cell const& cell,
                                      index direction) {
    auto neighbor = cell;
    neighbor.add(hex_diagonal(direction));
    return neighbor;
}

inline i32 hex_length(hex_cell const& cell) {
    return to_i32(std::abs(cell.q)
                  + std::abs(cell.r)
                  + std::abs(cell.s) / 2);
}

inline i32 hex_distance(hex_cell const& a,
                        hex_cell const& b) {
    auto dist = a;
    dist.substract(b);
    return hex_length(dist);
}

inline hex_cell hex_round(hex_frac_cell const& cell) {
    auto qi = to_i32(std::round(cell.q));
    auto ri = to_i32(std::round(cell.r));
    auto si = to_i32(std::round(cell.s));

    auto const q_diff = std::abs(qi - cell.q);
    auto const r_diff = std::abs(ri - cell.r);
    auto const s_diff = std::abs(si - cell.s);

    if ((q_diff > r_diff) && (q_diff > s_diff))
        qi = -ri - si;
    else if (r_diff > s_diff)
        ri = -qi - si;
    else
        si = -qi - ri;

    return {qi, ri, si};
}

inline hex_frac_cell hex_lerp(hex_frac_cell const& a,
                              hex_frac_cell const& b,
                              r32 t) {
    return {
        a.q * (1.f - t) + b.q * t,
        a.r * (1.f - t) + b.r * t,
        a.s * (1.f - t) + b.s * t};
}

inline hex_cell::list hex_line(hex_cell const& a,
                               hex_cell const& b) {
    auto const a_nudge = hex_frac_cell{a.q + 0.000001f,
                                       a.r + 0.000001f,
                                       a.s - 0.000002f};
    auto const b_nudge = hex_frac_cell{b.q + 0.000001f,
                                       b.r + 0.000001f,
                                       b.s - 0.000002f};

    ui32 const n = hex_distance(a, b);
    auto const step = 1.f / std::max(n, 1u);

    hex_cell::list results;
    for (auto i = 0u; i <= n; ++i)
        results.push_back(hex_round(hex_lerp(a_nudge,
                                             b_nudge,
                                             step * i)));

    return results;
}

enum class hex_offset : i32 {
    odd = -1,
    even = 1
};

inline hex_offset_coord hex_q_offset_from_cube(hex_offset offset,
                                               hex_cell const& cell) {
    auto const& col = cell.q;
    auto const row = cell.r
                     + to_i32((cell.q + (i32)offset * (cell.q & 1)) / 2);
    return {col, row};
}

inline hex_cell hex_q_offset_to_cube(hex_offset offset,
                                     hex_offset_coord const& coord) {
    auto const& q = coord.col;
    auto const r = coord.row
                   - to_i32((coord.col + (i32)offset * (coord.col & 1)) / 2);
    auto const s = -q - r;
    return {q, r, s};
}

inline hex_offset_coord hex_r_offset_from_cube(hex_offset offset,
                                               hex_cell const& cell) {
    auto const col = cell.q
                     + to_i32((cell.r + (i32)offset * (cell.r & 1)) / 2);
    auto const& row = cell.r;
    return {col, row};
}

inline hex_cell hex_r_offset_to_cube(hex_offset offset,
                                     hex_offset_coord const& coord) {
    auto const q = coord.col
                   - to_i32((coord.row + (i32)offset * (coord.row & 1)) / 2);
    auto const& r = coord.row;
    auto const s = -q - r;
    return {q, r, s};
}

inline hex_doubled_coord hex_q_doubled_from_cube(hex_cell const& cell) {
    auto const& col = cell.q;
    auto const row = 2 * cell.r + cell.q;
    return {col, row};
}

inline hex_cell hex_q_doubled_to_cube(hex_doubled_coord const& coord) {
    auto const& q = coord.col;
    auto const r = to_i32((coord.row - coord.col) / 2);
    auto const s = -q - r;
    return {q, r, s};
}

inline hex_doubled_coord hex_r_doubled_from_cube(hex_cell const& cell) {
    auto const col = 2 * cell.q + cell.r;
    auto const& row = cell.r;
    return {col, row};
}

inline hex_cell hex_r_doubled_to_cube(hex_doubled_coord const& coord) {
    auto const q = to_i32((coord.col - coord.row) / 2);
    auto const& r = coord.row;
    auto const s = -q - r;
    return {q, r, s};
}

hex_orientation const hex_layout_point_y = {
    std::sqrt(3.f),
    std::sqrt(3.f) / 2.f,
    0.f,
    3.f / 2.f,
    std::sqrt(3.f) / 3.f,
    -1.f / 3.f,
    0.f,
    2.f / 3.f,
    0.5f};

hex_orientation const hex_layout_flat = {
    3.f / 2.f,
    0.f,
    std::sqrt(3.f) / 2.f,
    std::sqrt(3.f),
    2.f / 3.f,
    0.f,
    -1.f / 3.f,
    std::sqrt(3.f) / 3.f,
    0.f};

inline hex_point hex_to_pixel(hex_layout const& layout,
                              hex_cell const& cell) {
    auto const& m = layout.orientation;
    auto const& size = layout.size;
    auto const& origin = layout.origin;
    auto const x = (m.f0 * cell.q + m.f1 * cell.r) * size.x;
    auto const y = (m.f2 * cell.q + m.f3 * cell.r) * size.y;
    return {x + origin.x, y + origin.y};
}

inline hex_frac_cell hex_pixel_to_cell(hex_layout const& layout,
                                       hex_point const& p) {
    auto const& m = layout.orientation;
    auto const& size = layout.size;
    auto const& origin = layout.origin;
    auto const pt = hex_point{(p.x - origin.x) / size.x,
                              (p.y - origin.y) / size.y};
    auto const q = m.b0 * pt.x + m.b1 * pt.y;
    auto const r = m.b2 * pt.x + m.b3 * pt.y;
    return {q, r, -q - r};
}

inline hex_point hex_corner_offset(hex_layout const& layout,
                                   i32 corner) {
    auto const& m = layout.orientation;
    auto const& size = layout.size;
    auto const angle = 2.
                       * std::numbers::pi_v<r32> * (m.start_angle - corner)
                       / 6.f;
    return {size.x * (r32)std::cos(angle),
            size.y * (r32)std::sin(angle)};
}

inline hex_point::list hex_polygon_corners(hex_layout const& layout,
                                           hex_cell const& cell) {
    hex_point::list corners = {};
    auto const center = hex_to_pixel(layout, cell);
    for (int i = 0u; i < 6; ++i) {
        auto const offset = hex_corner_offset(layout, i);
        corners.push_back({center.x + offset.x,
                           center.y + offset.y});
    }
    return corners;
}

inline hex_point hex_get_corner(hex_point const& center,
                                r32 size,
                                ui32 corner) {
    auto const angle_deg = 60 * corner - 30;
    auto const angle_rad = std::numbers::pi_v<r32> / 180 * angle_deg;

    return {
        center.x + size * std::cos(angle_rad),
        center.y + size * std::sin(angle_rad)};
}

enum class hex_cardinal_direction : index {
    NE = 0,
    E,
    SE,
    SW,
    W,
    NW
};

inline string to_string(hex_cardinal_direction direction) {
    switch (direction) {
    case hex_cardinal_direction::NE: {
        return "Northeast";
    }
    case hex_cardinal_direction::E: {
        return "East";
    }
    case hex_cardinal_direction::SE: {
        return "Southeast";
    }
    case hex_cardinal_direction::SW: {
        return "Southwest";
    }
    case hex_cardinal_direction::W: {
        return "West";
    }
    case hex_cardinal_direction::NW: {
        return "Northwest";
    }
    }
}

hex_cell::list const hex_cardinal_directions{
    {1, 0, -1},
    {0, 1, -1},
    {-1, 1, 0},
    {-1, 0, 1},
    {0, -1, 1},
    {1, -1, 0}};

inline hex_cell hex_get(hex_cardinal_direction direction) {
    return hex_cardinal_directions[(index)direction];
}

inline hex_cardinal_direction hex_opposite(hex_cardinal_direction direction) {
    if ((index)direction < 3)
        return hex_cardinal_direction((i32)direction + 3);
    else
        return hex_cardinal_direction((i32)direction - 3);
}

constexpr r32 const hex_inner_radius_factor = 0.866025404f;

constexpr r32 const hex_default_outer_radius = 1.f;

inline r32 hex_calculate_inner_radius(r32 outer_radius) {
    return outer_radius * hex_inner_radius_factor;
}

struct hex_grid {
    r32 inner_radius = 0.f;

    r32 outer_radius = hex_default_outer_radius;

    hex_layout layout;

    hex_grid(r32 radius = hex_default_outer_radius)
    : outer_radius(radius) {
        update();
    }

    void update(hex_orientation orientation = hex_layout_point_y) {
        inner_radius = hex_calculate_inner_radius(outer_radius);
        layout = {
            orientation,
            {},
            {outer_radius, outer_radius}};
    }

    hex_cell find(r32 x, r32 y) const {
        return hex_round(hex_pixel_to_cell(layout,
                                           {x, y}));
    }

    hex_point to_pixel(hex_cell const& cell) const {
        return hex_to_pixel(layout, cell);
    }
};

} // namespace lava
```


-------------------------------

Updated on 2026-02-01 at 18:13:39 +0000
