---
title: lava::vertex
summary: Vertex. 

---

# lava::vertex



Vertex. 


`#include <primitive.hpp>`

## Public Types

|                | Name           |
| -------------- | -------------- |
| using std::vector< [vertex](/_doxybook/Classes/structlava_1_1vertex.md) > | **[list](/_doxybook/Classes/structlava_1_1vertex.md#using-list)** <br>List of vertices.  |

## Public Functions

|                | Name           |
| -------------- | -------------- |
| bool | **[operator==](/_doxybook/Classes/structlava_1_1vertex.md#function-operator==)**([vertex](/_doxybook/Classes/structlava_1_1vertex.md) const & other) const<br>Equal compare operator.  |

## Public Attributes

|                | Name           |
| -------------- | -------------- |
| [v3](/_doxybook/Namespaces/namespacelava.md#using-v3) | **[position](/_doxybook/Classes/structlava_1_1vertex.md#variable-position)** <br>Vertex position.  |
| [v4](/_doxybook/Namespaces/namespacelava.md#using-v4) | **[color](/_doxybook/Classes/structlava_1_1vertex.md#variable-color)** <br>Vertex color.  |
| [v2](/_doxybook/Namespaces/namespacelava.md#using-v2) | **[uv](/_doxybook/Classes/structlava_1_1vertex.md#variable-uv)** <br>Vertex uv.  |
| [v3](/_doxybook/Namespaces/namespacelava.md#using-v3) | **[normal](/_doxybook/Classes/structlava_1_1vertex.md#variable-normal)** <br>Vertex normal.  |

## Public Types Documentation

### using list

```cpp
using lava::vertex::list =  std::vector<vertex>;
```

List of vertices. 

## Public Functions Documentation

### function operator==

```cpp
inline bool operator==(
    vertex const & other
) const
```

Equal compare operator. 

**Parameters**: 

  * **other** Another vertex 


**Return**: Another vertex is equal or not 

## Public Attributes Documentation

### variable position

```cpp
v3 position;
```

Vertex position. 

### variable color

```cpp
v4 color;
```

Vertex color. 

### variable uv

```cpp
v2 uv;
```

Vertex uv. 

### variable normal

```cpp
v3 normal;
```

Vertex normal. 

-------------------------------

Updated on 2026-02-01 at 18:13:39 +0000