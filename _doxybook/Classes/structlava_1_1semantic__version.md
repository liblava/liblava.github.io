---
title: lava::semantic_version
summary: Semantic version. 

---

# lava::semantic_version



Semantic version. 


`#include <version.hpp>`

## Public Functions

|                | Name           |
| -------------- | -------------- |
| auto | **[operator<=>](/_doxybook/Classes/structlava_1_1semantic__version.md#function-operator<=>)**([semantic_version](/_doxybook/Classes/structlava_1_1semantic__version.md) const & ) const =default<br>Default compare operators.  |

## Public Attributes

|                | Name           |
| -------------- | -------------- |
| [ui32](/_doxybook/Namespaces/namespacelava.md#using-ui32) | **[major](/_doxybook/Classes/structlava_1_1semantic__version.md#variable-major)** <br>Major version.  |
| [ui32](/_doxybook/Namespaces/namespacelava.md#using-ui32) | **[minor](/_doxybook/Classes/structlava_1_1semantic__version.md#variable-minor)** <br>Minor version.  |
| [ui32](/_doxybook/Namespaces/namespacelava.md#using-ui32) | **[patch](/_doxybook/Classes/structlava_1_1semantic__version.md#variable-patch)** <br>Patch version.  |

## Public Functions Documentation

### function operator<=>

```cpp
auto operator<=>(
    semantic_version const & 
) const =default
```

Default compare operators. 

## Public Attributes Documentation

### variable major

```cpp
ui32 major = LAVA_VERSION_MAJOR;
```

Major version. 

### variable minor

```cpp
ui32 minor = LAVA_VERSION_MINOR;
```

Minor version. 

### variable patch

```cpp
ui32 patch = LAVA_VERSION_PATCH;
```

Patch version. 

-------------------------------

Updated on 2026-02-01 at 18:13:39 +0000