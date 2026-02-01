---
title: lava::hex_grid
summary: Hex grid. 

---

# lava::hex_grid



Hex grid. 


`#include <hex.hpp>`

## Public Functions

|                | Name           |
| -------------- | -------------- |
| | **[hex_grid](/_doxybook/Classes/structlava_1_1hex__grid.md#function-hex-grid)**([r32](/_doxybook/Namespaces/namespacelava.md#using-r32) radius =[hex_default_outer_radius](/_doxybook/Namespaces/namespacelava.md#variable-hex-default-outer-radius))<br>Construct a new hex grid.  |
| void | **[update](/_doxybook/Classes/structlava_1_1hex__grid.md#function-update)**([hex_orientation](/_doxybook/Classes/structlava_1_1hex__orientation.md) orientation =[hex_layout_point_y](/_doxybook/Namespaces/namespacelava.md#variable-hex-layout-point-y))<br>Update the hex grid.  |
| [hex_cell](/_doxybook/Classes/structlava_1_1hex__cell.md) | **[find](/_doxybook/Classes/structlava_1_1hex__grid.md#function-find)**([r32](/_doxybook/Namespaces/namespacelava.md#using-r32) x, [r32](/_doxybook/Namespaces/namespacelava.md#using-r32) y) const<br>Find the hex cell from X and Y coordinates.  |
| [hex_point](/_doxybook/Classes/structlava_1_1hex__point.md) | **[to_pixel](/_doxybook/Classes/structlava_1_1hex__grid.md#function-to-pixel)**([hex_cell](/_doxybook/Classes/structlava_1_1hex__cell.md) const & cell) const<br>Get the hex point from hex cell.  |

## Public Attributes

|                | Name           |
| -------------- | -------------- |
| [r32](/_doxybook/Namespaces/namespacelava.md#using-r32) | **[inner_radius](/_doxybook/Classes/structlava_1_1hex__grid.md#variable-inner-radius)** <br>Hex inner radius.  |
| [r32](/_doxybook/Namespaces/namespacelava.md#using-r32) | **[outer_radius](/_doxybook/Classes/structlava_1_1hex__grid.md#variable-outer-radius)** <br>Hex outer radius.  |
| [hex_layout](/_doxybook/Classes/structlava_1_1hex__layout.md) | **[layout](/_doxybook/Classes/structlava_1_1hex__grid.md#variable-layout)** <br>Hex layout.  |

## Public Functions Documentation

### function hex_grid

```cpp
inline hex_grid(
    r32 radius =hex_default_outer_radius
)
```

Construct a new hex grid. 

**Parameters**: 

  * **radius** Hex outer radius 


### function update

```cpp
inline void update(
    hex_orientation orientation =hex_layout_point_y
)
```

Update the hex grid. 

**Parameters**: 

  * **orientation** Hex orientation 


### function find

```cpp
inline hex_cell find(
    r32 x,
    r32 y
) const
```

Find the hex cell from X and Y coordinates. 

**Parameters**: 

  * **x** X coordinate 
  * **y** Y coordinate 


**Return**: [hex_cell](/_doxybook/Classes/structlava_1_1hex__cell.md) Hex cell 

### function to_pixel

```cpp
inline hex_point to_pixel(
    hex_cell const & cell
) const
```

Get the hex point from hex cell. 

**Parameters**: 

  * **cell** Hex cell 


**Return**: [hex_point](/_doxybook/Classes/structlava_1_1hex__point.md) Hex point 

## Public Attributes Documentation

### variable inner_radius

```cpp
r32 inner_radius = 0.f;
```

Hex inner radius. 

### variable outer_radius

```cpp
r32 outer_radius = hex_default_outer_radius;
```

Hex outer radius. 

### variable layout

```cpp
hex_layout layout;
```

Hex layout. 

-------------------------------

Updated on 2026-02-01 at 18:13:39 +0000