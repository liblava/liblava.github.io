---
title: lava::props::item
summary: Prop item. 

---

# lava::props::item



Prop item. 


`#include <props.hpp>`

## Public Types

|                | Name           |
| -------------- | -------------- |
| using std::map< [string](/_doxybook/Namespaces/namespacelava.md#using-string), [item](/_doxybook/Classes/structlava_1_1props_1_1item.md) > | **[map](/_doxybook/Classes/structlava_1_1props_1_1item.md#using-map)** <br>Map of items.  |

## Public Functions

|                | Name           |
| -------------- | -------------- |
| | **[item](/_doxybook/Classes/structlava_1_1props_1_1item.md#function-item)**([string_ref](/_doxybook/Namespaces/namespacelava.md#using-string-ref) filename)<br>Construct a new prop.  |

## Public Attributes

|                | Name           |
| -------------- | -------------- |
| [string](/_doxybook/Namespaces/namespacelava.md#using-string) | **[filename](/_doxybook/Classes/structlava_1_1props_1_1item.md#variable-filename)** <br>File name of prop.  |
| [file_data](/_doxybook/Classes/structlava_1_1file__data.md) | **[data](/_doxybook/Classes/structlava_1_1props_1_1item.md#variable-data)** <br>File data of prop.  |

## Public Types Documentation

### using map

```cpp
using lava::props::item::map =  std::map<string, item>;
```

Map of items. 

## Public Functions Documentation

### function item

```cpp
inline item(
    string_ref filename
)
```

Construct a new prop. 

**Parameters**: 

  * **filename** File name of prop 


## Public Attributes Documentation

### variable filename

```cpp
string filename;
```

File name of prop. 

### variable data

```cpp
file_data data;
```

File data of prop. 

-------------------------------

Updated on 2026-02-01 at 18:13:39 +0000