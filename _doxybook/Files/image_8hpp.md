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
| struct | **[lava::image_data](/_doxybook/Classes/structlava_1_1image__data.md)** <br>Image data.  |
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

struct image_data {
    using s_ptr = std::shared_ptr<image_data>;

    uv2 dimensions = uv2(0, 0);

    ui32 channels = 0;

    bool ready() const {
        return m_data != nullptr;
    }

    data::ptr get_data() {
        return m_data;
    }

    void set_data(data::ptr data) {
        m_data = data;
    }

    size_t size() const {
        return channels * dimensions.x * dimensions.y;
    }

    ~image_data();

private:
    data::ptr m_data = nullptr;
};

struct image : entity {
    using s_ptr = std::shared_ptr<image>;

    using s_map = std::map<id, s_ptr>;

    using s_list = std::vector<s_ptr>;

    static s_ptr make(VkFormat format,
                      VkImage vk_image = 0) {
        return std::make_shared<image>(format, vk_image);
    }

    explicit image(VkFormat format,
                   VkImage vk_image = 0);

    bool create(device::ptr device,
                uv2 size,
                VmaMemoryUsage memory_usage = VMA_MEMORY_USAGE_GPU_ONLY,
                VmaAllocationCreateFlags allocation_flags = 0);

    void destroy(bool view_only = false);

    void destroy_view() {
        destroy(true);
    }

    device::ptr get_device() {
        return m_device;
    }

    VkFormat get_format() const {
        return m_info.format;
    }

    uv2 get_size() const {
        return {m_info.extent.width, m_info.extent.height};
    }

    ui32 get_depth() const {
        return m_info.extent.depth;
    }

    VkImage get() const {
        return m_vk_image;
    }

    VkImageView get_view() const {
        return m_view;
    }

    VkImageCreateInfo const& get_info() const {
        return m_info;
    }

    VkImageViewCreateInfo const& get_view_info() const {
        return m_view_info;
    }

    VkImageSubresourceRange const& get_subresource_range() const {
        return m_subresource_range;
    }

    void set_flags(VkImageCreateFlagBits flags) {
        m_info.flags = flags;
    }

    void set_tiling(VkImageTiling tiling) {
        m_info.tiling = tiling;
    }

    void set_usage(VkImageUsageFlags usage) {
        m_info.usage = usage;
    }

    void set_layout(VkImageLayout initial) {
        m_info.initialLayout = initial;
    }

    void set_aspect_mask(VkImageAspectFlags aspectMask) {
        m_subresource_range.aspectMask = aspectMask;
    }

    void set_level_count(ui32 levels) {
        m_subresource_range.levelCount = levels;
        m_info.mipLevels = levels;
    }

    void set_layer_count(ui32 layers) {
        m_subresource_range.layerCount = layers;
        m_info.arrayLayers = layers;
    }

    void set_component(VkComponentMapping mapping = {}) {
        m_view_info.components = mapping;
    }

    void set_view_type(VkImageViewType type) {
        m_view_info.viewType = type;
    }

    VmaAllocation const& get_allocation() const {
        return m_allocation;
    }

private:
    device::ptr m_device = nullptr;

    VkImage m_vk_image = VK_NULL_HANDLE;

    VkImageCreateInfo m_info;

    VmaAllocation m_allocation = nullptr;

    VkImageView m_view = VK_NULL_HANDLE;

    VkImageViewCreateInfo m_view_info;

    VkImageSubresourceRange m_subresource_range;
};

image::s_ptr create_image(device::ptr device,
                          VkFormat format,
                          uv2 size,
                          VkImage vk_image = 0);

image::s_ptr grab_image(image::s_ptr source);

} // namespace lava
```


-------------------------------

Updated on 2026-02-01 at 18:13:39 +0000
