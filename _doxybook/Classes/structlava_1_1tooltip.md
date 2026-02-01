---
title: lava::tooltip
summary: Tooltip. 

---

# lava::tooltip



Tooltip. 


`#include <input.hpp>`

## Public Types

|                | Name           |
| -------------- | -------------- |
| using std::vector< [tooltip](/_doxybook/Classes/structlava_1_1tooltip.md) > | **[list](/_doxybook/Classes/structlava_1_1tooltip.md#using-list)** <br>List of tooltips.  |

## Public Functions

|                | Name           |
| -------------- | -------------- |
| | **[tooltip](/_doxybook/Classes/structlava_1_1tooltip.md#function-tooltip)**([string_ref](/_doxybook/Namespaces/namespacelava.md#using-string-ref) name, [key](/_doxybook/Namespaces/namespacelava.md#enum-key) key, [mod](/_doxybook/Namespaces/namespacelava.md#enum-mod) mod)<br>Construct a new tooltip.  |

## Public Attributes

|                | Name           |
| -------------- | -------------- |
| [string](/_doxybook/Namespaces/namespacelava.md#using-string) | **[name](/_doxybook/Classes/structlava_1_1tooltip.md#variable-name)** <br>Name of tooltip.  |
| [lava::key](/_doxybook/Namespaces/namespacelava.md#enum-key) | **[key](/_doxybook/Classes/structlava_1_1tooltip.md#variable-key)** <br>Input key.  |
| [lava::mod](/_doxybook/Namespaces/namespacelava.md#enum-mod) | **[mod](/_doxybook/Classes/structlava_1_1tooltip.md#variable-mod)** <br>Input mod.  |

## Public Types Documentation

### using list

```cpp
using lava::tooltip::list =  std::vector<tooltip>;
```

List of tooltips. 

## Public Functions Documentation

### function tooltip

```cpp
inline tooltip(
    string_ref name,
    key key,
    mod mod
)
```

Construct a new tooltip. 

**Parameters**: 

  * **name** Name of tooltip 
  * **key** Input key 
  * **mod** Input mod 


## Public Attributes Documentation

### variable name

```cpp
string name;
```

Name of tooltip. 

### variable key

```cpp
lava::key key;
```

Input key. 

### variable mod

```cpp
lava::mod mod;
```

Input mod. 

-------------------------------

Updated on 2026-02-01 at 18:13:39 +0000