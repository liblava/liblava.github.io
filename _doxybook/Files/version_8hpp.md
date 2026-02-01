---
title: liblava/core/version.hpp
summary: Version information. 

---

# liblava/core/version.hpp

Version information.  [More...](#detailed-description)

## Namespaces

| Name           |
| -------------- |
| **[lava](/_doxybook/Namespaces/namespacelava.md)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| struct | **[lava::semantic_version](/_doxybook/Classes/structlava_1_1semantic__version.md)** <br>Semantic version.  |
| struct | **[lava::version](/_doxybook/Classes/structlava_1_1version.md)** <br>Version.  |

## Detailed Description

Version information. 

**Author**: Lava Block OÜ and contributors 

**Copyright**: Copyright (c) 2018-present, MIT License 



## Source code

```cpp


#pragma once

#include "liblava/core/types.hpp"

namespace lava {

struct semantic_version {
    ui32 major = LAVA_VERSION_MAJOR;

    ui32 minor = LAVA_VERSION_MINOR;

    ui32 patch = LAVA_VERSION_PATCH;

    auto operator<=>(semantic_version const&) const = default;
};

using sem_version = semantic_version;

inline sem_version to_version(string_ref str) {
    sem_version result{0, 0, 0};
#ifdef _WIN32
    sscanf_s
#else
    sscanf
#endif
        (str.c_str(), "%d.%d.%d", &result.major, &result.minor, &result.patch);
    return result;
}

enum class version_stage : index {
    preview,
    alpha,
    beta,
    rc,
    release,
    rolling
};

struct version {
    ui32 year = 2024;

    ui32 release = 0;

    version_stage stage = version_stage::rolling;

    ui32 rev = 0;
};

constexpr name g_build_date = LAVA_BUILD_DATE;

constexpr name g_build_time = LAVA_BUILD_TIME;

} // namespace lava
```


-------------------------------

Updated on 2026-02-01 at 18:13:39 +0000
