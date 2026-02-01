---
title: liblava/asset/write_image.hpp
summary: Write image data to file. 

---

# liblava/asset/write_image.hpp

Write image data to file.  [More...](#detailed-description)

## Namespaces

| Name           |
| -------------- |
| **[lava](/_doxybook/Namespaces/namespacelava.md)**  |

## Detailed Description

Write image data to file. 

**Author**: Lava Block OÜ and contributors 

**Copyright**: Copyright (c) 2018-present, MIT License 



## Source code

```cpp


#pragma once

#include "liblava/resource/image.hpp"

namespace lava {

bool write_image_png(device::ptr device,
                     image::s_ptr image,
                     string_ref filename,
                     bool swizzle);

} // namespace lava
```


-------------------------------

Updated on 2026-02-01 at 18:13:39 +0000
