---
title: lava::internal_version
summary: Internal version. 

---

# lava::internal_version



Internal version. 


`#include <version.hpp>`

## Public Functions

|                | Name           |
| -------------- | -------------- |
| auto | **[operator<=>](/_doxybook/Classes/structlava_1_1internal__version.md#function-operator<=>)**([internal_version](/_doxybook/Classes/structlava_1_1internal__version.md) const & ) const =default<br>Default compare operators.  |

## Public Attributes

|                | Name           |
| -------------- | -------------- |
| [i32](/_doxybook/Namespaces/namespacelava.md#using-i32) | **[major](/_doxybook/Classes/structlava_1_1internal__version.md#variable-major)** <br>Major version.  |
| [i32](/_doxybook/Namespaces/namespacelava.md#using-i32) | **[minor](/_doxybook/Classes/structlava_1_1internal__version.md#variable-minor)** <br>Minor version.  |
| [i32](/_doxybook/Namespaces/namespacelava.md#using-i32) | **[patch](/_doxybook/Classes/structlava_1_1internal__version.md#variable-patch)** <br>Patch version.  |

## Public Functions Documentation

### function operator<=>

```cpp
auto operator<=>(
    internal_version const & 
) const =default
```

Default compare operators. 

## Public Attributes Documentation

### variable major

```cpp
i32 major = LAVA_VERSION_MAJOR;
```

Major version. 

### variable minor

```cpp
i32 minor = LAVA_VERSION_MINOR;
```

Minor version. 

### variable patch

```cpp
i32 patch = LAVA_VERSION_PATCH;
```

Patch version. 

-------------------------------

Updated on 2022-11-30 at 01:16:03 +0000