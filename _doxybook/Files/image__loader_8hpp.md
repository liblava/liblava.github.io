---
title: liblava/asset/image_loader.hpp
summary: Load image data from file and memory. 

---

# liblava/asset/image_loader.hpp

Load image data from file and memory.  [More...](#detailed-description)

## Namespaces

| Name           |
| -------------- |
| **[lava](/_doxybook/Namespaces/namespacelava.md)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| struct | **[lava::image_loader](/_doxybook/Classes/structlava_1_1image__loader.md)** <br>Load image data from file and memory.  |

## Detailed Description

Load image data from file and memory. 

**Author**: Lava Block OÜ and contributors 

**Copyright**: Copyright (c) 2018-present, MIT License 



## Source code

```cpp

#pragma once

#include <liblava/file/file.hpp>
#include <liblava/util/math.hpp>

namespace lava {

struct image_loader {
    explicit image_loader(string_ref filename);

    explicit image_loader(cdata::ref image);

    ~image_loader();

    bool ready() const {
        return data != nullptr;
    }

    data_cptr get() const {
        return data;
    }

    size_t size() const {
        return channels * dimensions.x * dimensions.y;
    }

    uv2 get_dimensions() const {
        return dimensions;
    }

    ui32 get_channels() const {
        return channels;
    }

private:
    data_ptr data = nullptr;

    uv2 dimensions = uv2(0, 0);

    ui32 channels = 0;
};

} // namespace lava
```


-------------------------------

Updated on 2022-11-30 at 01:16:04 +0000
