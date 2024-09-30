---
title: liblava/asset/load_image.hpp
summary: Load image data from file and memory. 

---

# liblava/asset/load_image.hpp

Load image data from file and memory.  [More...](#detailed-description)

## Namespaces

| Name           |
| -------------- |
| **[lava](/_doxybook/Namespaces/namespacelava.md)**  |

## Detailed Description

Load image data from file and memory. 

**Author**: Lava Block OÜ and contributors 

**Copyright**: Copyright (c) 2018-present, MIT License 



## Source code

```cpp

#pragma once

#include "liblava/resource/image.hpp"

namespace lava {

image_data::s_ptr load_image(string_ref filename);

image_data::s_ptr load_image(c_data::ref data);

} // namespace lava
```


-------------------------------

Updated on 2024-09-30 at 17:08:14 +0000
