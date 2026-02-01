---
title: lava::surface_format_request
summary: Surface format request. 

---

# lava::surface_format_request



Surface format request. 


`#include <format.hpp>`

## Public Attributes

|                | Name           |
| -------------- | -------------- |
| [VkFormats](/_doxybook/Namespaces/namespacelava.md#using-vkformats) | **[formats](/_doxybook/Classes/structlava_1_1surface__format__request.md#variable-formats)** <br>List of formats in request order.  |
| VkColorSpaceKHR | **[color_space](/_doxybook/Classes/structlava_1_1surface__format__request.md#variable-color-space)** <br>Color space to request.  |

## Public Attributes Documentation

### variable formats

```cpp
VkFormats formats = {
        VK_FORMAT_B8G8R8A8_UNORM,
        VK_FORMAT_R8G8B8A8_UNORM,
        VK_FORMAT_B8G8R8_UNORM,
        VK_FORMAT_R8G8B8_UNORM,
        VK_FORMAT_B8G8R8A8_SRGB,
        VK_FORMAT_R8G8B8A8_SRGB,
        VK_FORMAT_B8G8R8_SRGB,
        VK_FORMAT_R8G8B8_SRGB,
    };
```

List of formats in request order. 

### variable color_space

```cpp
VkColorSpaceKHR color_space = VK_COLOR_SPACE_SRGB_NONLINEAR_KHR;
```

Color space to request. 

-------------------------------

Updated on 2026-02-01 at 18:13:39 +0000