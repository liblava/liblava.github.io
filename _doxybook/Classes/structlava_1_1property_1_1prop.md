---
title: lava::property::prop
summary: Prop. 

---

# lava::property::prop



Prop. 


`#include <property.hpp>`

## Public Types

|                | Name           |
| -------------- | -------------- |
| using std::map< [string](/_doxybook/Namespaces/namespacelava.md#using-string), [prop](/_doxybook/Classes/structlava_1_1property_1_1prop.md) > | **[map](/_doxybook/Classes/structlava_1_1property_1_1prop.md#using-map)** <br>Map of props.  |

## Public Functions

|                | Name           |
| -------------- | -------------- |
| | **[prop](/_doxybook/Classes/structlava_1_1property_1_1prop.md#function-prop)**([string_ref](/_doxybook/Namespaces/namespacelava.md#using-string-ref) filename)<br>Construct a new prop.  |

## Public Attributes

|                | Name           |
| -------------- | -------------- |
| [string](/_doxybook/Namespaces/namespacelava.md#using-string) | **[filename](/_doxybook/Classes/structlava_1_1property_1_1prop.md#variable-filename)** <br>File name of prop.  |
| [file_data](/_doxybook/Classes/structlava_1_1file__data.md) | **[data](/_doxybook/Classes/structlava_1_1property_1_1prop.md#variable-data)** <br>File data of prop.  |

## Public Types Documentation

### using map

```cpp
using lava::property::prop::map =  std::map<string, prop>;
```

Map of props. 

## Public Functions Documentation

### function prop

```cpp
inline prop(
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

Updated on 2024-03-22 at 21:51:38 +0000