---
title: liblava/asset/load_mesh.hpp
summary: Load mesh from file. 

---

# liblava/asset/load_mesh.hpp

Load mesh from file.  [More...](#detailed-description)

## Namespaces

| Name           |
| -------------- |
| **[lava](/_doxybook/Namespaces/namespacelava.md)**  |

## Detailed Description

Load mesh from file. 

**Author**: Lava Block OÜ and contributors 

**Copyright**: Copyright (c) 2018-present, MIT License 



## Source code

```cpp


#pragma once

#include "liblava/resource/mesh.hpp"

namespace lava {

mesh::s_ptr load_mesh(device::ptr device,
                      string_ref filename,
                      string_ref temp_dir);

} // namespace lava
```


-------------------------------

Updated on 2026-02-01 at 18:13:39 +0000
