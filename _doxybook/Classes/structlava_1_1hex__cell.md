---
title: lava::hex_cell
summary: Hex cell. 

---

# lava::hex_cell



Hex cell. 


`#include <hex.hpp>`

## Public Types

|                | Name           |
| -------------- | -------------- |
| using std::vector< [hex_cell](/_doxybook/Classes/structlava_1_1hex__cell.md) > | **[list](/_doxybook/Classes/structlava_1_1hex__cell.md#using-list)** <br>List of hex cells.  |
| using std::pair< [i32](/_doxybook/Namespaces/namespacelava.md#using-i32), [i32](/_doxybook/Namespaces/namespacelava.md#using-i32) > | **[pair](/_doxybook/Classes/structlava_1_1hex__cell.md#using-pair)** <br>Hex pair (Q and R)  |
| using std::unordered_map< [pair](/_doxybook/Classes/structlava_1_1hex__cell.md#using-pair), [index](/_doxybook/Namespaces/namespacelava.md#using-index), [pair_hash](/_doxybook/Classes/structlava_1_1pair__hash.md) > | **[map](/_doxybook/Classes/structlava_1_1hex__cell.md#using-map)** <br>Map of hex cells.  |

## Public Functions

|                | Name           |
| -------------- | -------------- |
| auto | **[operator<=>](/_doxybook/Classes/structlava_1_1hex__cell.md#function-operator<=>)**([hex_cell](/_doxybook/Classes/structlava_1_1hex__cell.md) const & ) const =default<br>Compare operator.  |
| [pair](/_doxybook/Classes/structlava_1_1hex__cell.md#using-pair) | **[to_pair](/_doxybook/Classes/structlava_1_1hex__cell.md#function-to-pair)**() const<br>Get the pair.  |
| void | **[add](/_doxybook/Classes/structlava_1_1hex__cell.md#function-add)**([hex_cell](/_doxybook/Classes/structlava_1_1hex__cell.md) const & cell)<br>Add hex cell.  |
| void | **[substract](/_doxybook/Classes/structlava_1_1hex__cell.md#function-substract)**([hex_cell](/_doxybook/Classes/structlava_1_1hex__cell.md) const & cell)<br>Substract hex cell.  |
| void | **[scale](/_doxybook/Classes/structlava_1_1hex__cell.md#function-scale)**([i32](/_doxybook/Namespaces/namespacelava.md#using-i32) factor)<br>Scale the hex cell.  |
| void | **[rotate_left](/_doxybook/Classes/structlava_1_1hex__cell.md#function-rotate-left)**()<br>Rotate to left.  |
| void | **[rotate_right](/_doxybook/Classes/structlava_1_1hex__cell.md#function-rotate-right)**()<br>Rotate to right.  |

## Public Attributes

|                | Name           |
| -------------- | -------------- |
| [i32](/_doxybook/Namespaces/namespacelava.md#using-i32) | **[q](/_doxybook/Classes/structlava_1_1hex__cell.md#variable-q)** <br>Q axis.  |
| [i32](/_doxybook/Namespaces/namespacelava.md#using-i32) | **[r](/_doxybook/Classes/structlava_1_1hex__cell.md#variable-r)** <br>R axis.  |
| [i32](/_doxybook/Namespaces/namespacelava.md#using-i32) | **[s](/_doxybook/Classes/structlava_1_1hex__cell.md#variable-s)** <br>S axis.  |

## Public Types Documentation

### using list

```cpp
using lava::hex_cell::list =  std::vector<hex_cell>;
```

List of hex cells. 

### using pair

```cpp
using lava::hex_cell::pair =  std::pair<i32, i32>;
```

Hex pair (Q and R) 

### using map

```cpp
using lava::hex_cell::map =  std::unordered_map<pair, index, pair_hash>;
```

Map of hex cells. 

## Public Functions Documentation

### function operator<=>

```cpp
auto operator<=>(
    hex_cell const & 
) const =default
```

Compare operator. 

### function to_pair

```cpp
inline pair to_pair() const
```

Get the pair. 

**Return**: pair Hex pair 

### function add

```cpp
inline void add(
    hex_cell const & cell
)
```

Add hex cell. 

**Parameters**: 

  * **cell** Another hex cell 


### function substract

```cpp
inline void substract(
    hex_cell const & cell
)
```

Substract hex cell. 

**Parameters**: 

  * **cell** Another hex cell 


### function scale

```cpp
inline void scale(
    i32 factor
)
```

Scale the hex cell. 

**Parameters**: 

  * **factor** Scaling factor 


### function rotate_left

```cpp
inline void rotate_left()
```

Rotate to left. 

### function rotate_right

```cpp
inline void rotate_right()
```

Rotate to right. 

## Public Attributes Documentation

### variable q

```cpp
i32 q {};
```

Q axis. 

### variable r

```cpp
i32 r {};
```

R axis. 

### variable s

```cpp
i32 s {};
```

S axis. 

-------------------------------

Updated on 2026-02-01 at 18:13:39 +0000