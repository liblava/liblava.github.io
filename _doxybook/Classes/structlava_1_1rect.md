---
title: lava::rect
summary: Rectangle. 

---

# lava::rect



Rectangle. 


`#include <math.hpp>`

## Public Types

|                | Name           |
| -------------- | -------------- |
| using [rect](/_doxybook/Classes/structlava_1_1rect.md) const  & | **[ref](/_doxybook/Classes/structlava_1_1rect.md#using-ref)** <br>Reference to rect.  |

## Public Functions

|                | Name           |
| -------------- | -------------- |
| | **[rect](/_doxybook/Classes/structlava_1_1rect.md#function-rect)**() =default<br>Construct a new rectangle.  |
| | **[rect](/_doxybook/Classes/structlava_1_1rect.md#function-rect)**([i32](/_doxybook/Namespaces/namespacelava.md#using-i32) left, [i32](/_doxybook/Namespaces/namespacelava.md#using-i32) top, [ui32](/_doxybook/Namespaces/namespacelava.md#using-ui32) width, [ui32](/_doxybook/Namespaces/namespacelava.md#using-ui32) height)<br>Construct a new rectangle.  |
| | **[rect](/_doxybook/Classes/structlava_1_1rect.md#function-rect)**([iv2](/_doxybook/Namespaces/namespacelava.md#using-iv2) const & left_top, [ui32](/_doxybook/Namespaces/namespacelava.md#using-ui32) width, [ui32](/_doxybook/Namespaces/namespacelava.md#using-ui32) height)<br>Construct a new rectangle.  |
| | **[rect](/_doxybook/Classes/structlava_1_1rect.md#function-rect)**([iv2](/_doxybook/Namespaces/namespacelava.md#using-iv2) const & left_top, [uv2](/_doxybook/Namespaces/namespacelava.md#using-uv2) const & size)<br>Construct a new rectangle.  |
| [iv2](/_doxybook/Namespaces/namespacelava.md#using-iv2) const & | **[get_origin](/_doxybook/Classes/structlava_1_1rect.md#function-get-origin)**() const<br>Get the origin.  |
| [iv2](/_doxybook/Namespaces/namespacelava.md#using-iv2) const & | **[get_end_point](/_doxybook/Classes/structlava_1_1rect.md#function-get-end-point)**() const<br>Get the end point.  |
| [uv2](/_doxybook/Namespaces/namespacelava.md#using-uv2) | **[get_size](/_doxybook/Classes/structlava_1_1rect.md#function-get-size)**() const<br>Get the size.  |
| void | **[set_size](/_doxybook/Classes/structlava_1_1rect.md#function-set-size)**([uv2](/_doxybook/Namespaces/namespacelava.md#using-uv2) const & size)<br>Set the size.  |
| void | **[move](/_doxybook/Classes/structlava_1_1rect.md#function-move)**([iv2](/_doxybook/Namespaces/namespacelava.md#using-iv2) const & offset)<br>Move the rectangle.  |
| bool | **[contains](/_doxybook/Classes/structlava_1_1rect.md#function-contains)**([iv2](/_doxybook/Namespaces/namespacelava.md#using-iv2) point) const<br>Check if point is inside the rectangle.  |

## Public Types Documentation

### using ref

```cpp
using lava::rect::ref =  rect const&;
```

Reference to rect. 

## Public Functions Documentation

### function rect

```cpp
rect() =default
```

Construct a new rectangle. 

### function rect

```cpp
inline rect(
    i32 left,
    i32 top,
    ui32 width,
    ui32 height
)
```

Construct a new rectangle. 

**Parameters**: 

  * **left** Left position 
  * **top** Top position 
  * **width** Rectangle width 
  * **height** Rectangle height 


### function rect

```cpp
inline rect(
    iv2 const & left_top,
    ui32 width,
    ui32 height
)
```

Construct a new rectangle. 

**Parameters**: 

  * **left_top** Left top position 
  * **width** Rectangle width 
  * **height** Rectangle height 


### function rect

```cpp
inline rect(
    iv2 const & left_top,
    uv2 const & size
)
```

Construct a new rectangle. 

**Parameters**: 

  * **left_top** Left top position 
  * **size** Size of rectangle 


### function get_origin

```cpp
inline iv2 const & get_origin() const
```

Get the origin. 

**Return**: [iv2](/_doxybook/Namespaces/namespacelava.md#using-iv2) const& Left top position 

### function get_end_point

```cpp
inline iv2 const & get_end_point() const
```

Get the end point. 

**Return**: [iv2](/_doxybook/Namespaces/namespacelava.md#using-iv2) const& Right bottom position 

### function get_size

```cpp
inline uv2 get_size() const
```

Get the size. 

**Return**: [uv2](/_doxybook/Namespaces/namespacelava.md#using-uv2) Width and height 

### function set_size

```cpp
inline void set_size(
    uv2 const & size
)
```

Set the size. 

**Parameters**: 

  * **size** Width and height 


### function move

```cpp
inline void move(
    iv2 const & offset
)
```

Move the rectangle. 

**Parameters**: 

  * **offset** Offset to move 


### function contains

```cpp
inline bool contains(
    iv2 point
) const
```

Check if point is inside the rectangle. 

**Parameters**: 

  * **point** Point to check 


**Return**: Point is inside or out 

-------------------------------

Updated on 2026-02-01 at 18:13:39 +0000