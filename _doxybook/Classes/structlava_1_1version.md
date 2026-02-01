---
title: lava::version
summary: Version. 

---

# lava::version



Version. 


`#include <version.hpp>`

## Public Attributes

|                | Name           |
| -------------- | -------------- |
| [ui32](/_doxybook/Namespaces/namespacelava.md#using-ui32) | **[year](/_doxybook/Classes/structlava_1_1version.md#variable-year)** <br>Version year.  |
| [ui32](/_doxybook/Namespaces/namespacelava.md#using-ui32) | **[release](/_doxybook/Classes/structlava_1_1version.md#variable-release)** <br>Version release.  |
| [version_stage](/_doxybook/Namespaces/namespacelava.md#enum-version-stage) | **[stage](/_doxybook/Classes/structlava_1_1version.md#variable-stage)** <br>Version stage.  |
| [ui32](/_doxybook/Namespaces/namespacelava.md#using-ui32) | **[rev](/_doxybook/Classes/structlava_1_1version.md#variable-rev)** <br>Version revision.  |

## Public Attributes Documentation

### variable year

```cpp
ui32 year = 2024;
```

Version year. 

### variable release

```cpp
ui32 release = 0;
```

Version release. 

### variable stage

```cpp
version_stage stage = version_stage::rolling;
```

Version stage. 

### variable rev

```cpp
ui32 rev = 0;
```

Version revision. 

-------------------------------

Updated on 2026-02-01 at 18:13:39 +0000