---
title: lava::mesh_template_data
summary: Templated mesh data. 

---

# lava::mesh_template_data



Templated mesh data.  [More...](#detailed-description)


`#include <mesh.hpp>`

## Public Functions

|                | Name           |
| -------------- | -------------- |
| template <typename PosType  =r32\> <br>void | **[move](/_doxybook/Classes/structlava_1_1mesh__template__data.md#function-move)**(std::array< PosType, 3 > offset)<br>Move mesh data by offset.  |
| void | **[scale](/_doxybook/Classes/structlava_1_1mesh__template__data.md#function-scale)**(auto factor)<br>Scale mesh data by factor.  |
| template <typename PosType  =r32\> <br>void | **[scale_vector](/_doxybook/Classes/structlava_1_1mesh__template__data.md#function-scale-vector)**(std::array< PosType, 3 > factors)<br>Scale mesh data by vector.  |

## Public Attributes

|                | Name           |
| -------------- | -------------- |
| std::vector< T > | **[vertices](/_doxybook/Classes/structlava_1_1mesh__template__data.md#variable-vertices)** <br>List of vertices.  |
| [index_list](/_doxybook/Namespaces/namespacelava.md#using-index-list) | **[indices](/_doxybook/Classes/structlava_1_1mesh__template__data.md#variable-indices)** <br>List of indices.  |

## Detailed Description

```cpp
template <typename T  =vertex>
struct lava::mesh_template_data;
```

Templated mesh data. 

**Template Parameters**: 

  * **T** Input vertex struct 

## Public Functions Documentation

### function move

```cpp
template <typename PosType  =r32>
inline void move(
    std::array< PosType, 3 > offset
)
```

Move mesh data by offset. 

**Parameters**: 

  * **offset** Position offset 


**Template Parameters**: 

  * **PosType** Coordinate element typename 


### function scale

```cpp
inline void scale(
    auto factor
)
```

Scale mesh data by factor. 

**Parameters**: 

  * **factor** Position scaling factor 


### function scale_vector

```cpp
template <typename PosType  =r32>
inline void scale_vector(
    std::array< PosType, 3 > factors
)
```

Scale mesh data by vector. 

**Parameters**: 

  * **factors** Array of position scaling factors 


**Template Parameters**: 

  * **PosType** Coordinate element typename 


## Public Attributes Documentation

### variable vertices

```cpp
std::vector< T > vertices;
```

List of vertices. 

### variable indices

```cpp
index_list indices;
```

List of indices. 

-------------------------------

Updated on 2026-02-01 at 18:13:39 +0000