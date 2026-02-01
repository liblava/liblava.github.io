---
title: lava::id
summary: Identification. 

---

# lava::id



Identification. 


`#include <id.hpp>`

## Public Types

|                | Name           |
| -------------- | -------------- |
| using [id](/_doxybook/Classes/structlava_1_1id.md) const  & | **[ref](/_doxybook/Classes/structlava_1_1id.md#using-ref)** <br>Reference to id.  |
| using std::set< [id](/_doxybook/Classes/structlava_1_1id.md) > | **[set](/_doxybook/Classes/structlava_1_1id.md#using-set)** <br>Set of ids.  |
| using [set](/_doxybook/Classes/structlava_1_1id.md#using-set) const  & | **[set_ref](/_doxybook/Classes/structlava_1_1id.md#using-set-ref)** <br>Reference to set of ids.  |
| using std::vector< [id](/_doxybook/Classes/structlava_1_1id.md) > | **[list](/_doxybook/Classes/structlava_1_1id.md#using-list)** <br>List if ids.  |
| using std::map< [id](/_doxybook/Classes/structlava_1_1id.md), [id](/_doxybook/Classes/structlava_1_1id.md) > | **[map](/_doxybook/Classes/structlava_1_1id.md#using-map)** <br>Map of ids.  |
| using std::map< [id](/_doxybook/Classes/structlava_1_1id.md), [index](/_doxybook/Namespaces/namespacelava.md#using-index) > | **[index_map](/_doxybook/Classes/structlava_1_1id.md#using-index-map)** <br>Index map by ids.  |
| using std::map< [id](/_doxybook/Classes/structlava_1_1id.md), [string](/_doxybook/Namespaces/namespacelava.md#using-string) > | **[string_map](/_doxybook/Classes/structlava_1_1id.md#using-string-map)** <br>String map by ids.  |

## Public Functions

|                | Name           |
| -------------- | -------------- |
| | **[id](/_doxybook/Classes/structlava_1_1id.md#function-id)**() =default<br>Construct a new id.  |
| | **[id](/_doxybook/Classes/structlava_1_1id.md#function-id)**([index](/_doxybook/Namespaces/namespacelava.md#using-index) value)<br>Construct a new id.  |
| bool | **[valid](/_doxybook/Classes/structlava_1_1id.md#function-valid)**() const<br>Check if the id is valid.  |
| [string](/_doxybook/Namespaces/namespacelava.md#using-string) | **[to_string](/_doxybook/Classes/structlava_1_1id.md#function-to-string)**() const<br>Convert the id to string.  |
| void | **[invalidate](/_doxybook/Classes/structlava_1_1id.md#function-invalidate)**()<br>Invalidate id.  |
| auto | **[operator<=>](/_doxybook/Classes/structlava_1_1id.md#function-operator<=>)**([id](/_doxybook/Classes/structlava_1_1id.md) const & ) const =default<br>Compare operator.  |

## Public Attributes

|                | Name           |
| -------------- | -------------- |
| [index](/_doxybook/Namespaces/namespacelava.md#using-index) | **[value](/_doxybook/Classes/structlava_1_1id.md#variable-value)** <br>Value.  |

## Public Types Documentation

### using ref

```cpp
using lava::id::ref =  id const&;
```

Reference to id. 

### using set

```cpp
using lava::id::set =  std::set<id>;
```

Set of ids. 

### using set_ref

```cpp
using lava::id::set_ref =  set const&;
```

Reference to set of ids. 

### using list

```cpp
using lava::id::list =  std::vector<id>;
```

List if ids. 

### using map

```cpp
using lava::id::map =  std::map<id, id>;
```

Map of ids. 

### using index_map

```cpp
using lava::id::index_map =  std::map<id, index>;
```

Index map by ids. 

### using string_map

```cpp
using lava::id::string_map =  std::map<id, string>;
```

String map by ids. 

## Public Functions Documentation

### function id

```cpp
id() =default
```

Construct a new id. 

### function id

```cpp
inline id(
    index value
)
```

Construct a new id. 

**Parameters**: 

  * **value** Value of id 


### function valid

```cpp
inline bool valid() const
```

Check if the id is valid. 

**Return**: Id is valid or not 

### function to_string

```cpp
inline string to_string() const
```

Convert the id to string. 

**Return**: string String representation of id 

### function invalidate

```cpp
inline void invalidate()
```

Invalidate id. 

### function operator<=>

```cpp
auto operator<=>(
    id const & 
) const =default
```

Compare operator. 

## Public Attributes Documentation

### variable value

```cpp
index value = no_index;
```

Value. 

-------------------------------

Updated on 2026-02-01 at 18:13:39 +0000