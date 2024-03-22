---
title: liblava/resource/image.hpp
summary: Vulkan image. 

---

# liblava/resource/image.hpp

Vulkan image.  [More...](#detailed-description)

## Namespaces

| Name           |
| -------------- |
| **[lava](/_doxybook/Namespaces/namespacelava.md)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| struct | **[lava::image](/_doxybook/Classes/structlava_1_1image.md)** <br>Image.  |

## Detailed Description

Vulkan image. 

**Author**: Lava Block OÜ and contributors 

**Copyright**: Copyright (c) 2018-present, MIT License 



## Source code

```cpp

#pragma once

#include "liblava/base/device.hpp"

namespace lava {

struct image : entity {
    using ptr = std::shared_ptr<image>;

    using map = std::map<id, ptr>;

    using list = std::vector<ptr>;

    static ptr make(VkFormat format,
                    VkImage vk_image = 0) {
        return std::make_shared<image>(format, vk_image);
    }

    explicit image(VkFormat format,
                   VkImage vk_image = 0);

    bool create(device_p device,
                uv2 size,
                VmaMemoryUsage memory_usage = VMA_MEMORY_USAGE_GPU_ONLY,
                VmaAllocationCreateFlags allocation_flags = 0);

    void destroy(bool view_only = false);

    void destroy_view() {
        destroy(true);
    }

    device_p get_device() {
        return device;
    }

    VkFormat get_format() const {
        return info.format;
    }

    uv2 get_size() const {
        return { info.extent.width, info.extent.height };
    }

    ui32 get_depth() const {
        return info.extent.depth;
    }

    VkImage get() const {
        return vk_image;
    }

    VkImageView get_view() const {
        return view;
    }

    VkImageCreateInfo const& get_info() const {
        return info;
    }

    VkImageViewCreateInfo const& get_view_info() const {
        return view_info;
    }

    VkImageSubresourceRange const& get_subresource_range() const {
        return subresource_range;
    }

    void set_flags(VkImageCreateFlagBits flags) {
        info.flags = flags;
    }

    void set_tiling(VkImageTiling tiling) {
        info.tiling = tiling;
    }

    void set_usage(VkImageUsageFlags usage) {
        info.usage = usage;
    }

    void set_layout(VkImageLayout initial) {
        info.initialLayout = initial;
    }

    void set_aspect_mask(VkImageAspectFlags aspectMask) {
        subresource_range.aspectMask = aspectMask;
    }

    void set_level_count(ui32 levels) {
        subresource_range.levelCount = levels;
        info.mipLevels = levels;
    }

    void set_layer_count(ui32 layers) {
        subresource_range.layerCount = layers;
        info.arrayLayers = layers;
    }

    void set_component(VkComponentMapping mapping = {}) {
        view_info.components = mapping;
    }

    void set_view_type(VkImageViewType type) {
        view_info.viewType = type;
    }

    VmaAllocation const& get_allocation() const {
        return allocation;
    }

private:
    device_p device = nullptr;

    VkImage vk_image = VK_NULL_HANDLE;

    VkImageCreateInfo info;

    VmaAllocation allocation = nullptr;

    VkImageView view = VK_NULL_HANDLE;

    VkImageViewCreateInfo view_info;

    VkImageSubresourceRange subresource_range;
};

image::ptr create_image(device_p device,
                        VkFormat format,
                        uv2 size,
                        VkImage vk_image = 0);

image::ptr grab_image(image::ptr source);

} // namespace lava
```


-------------------------------

Updated on 2024-03-22 at 21:51:38 +0000
