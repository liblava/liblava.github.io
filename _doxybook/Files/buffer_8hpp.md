---
title: liblava/resource/buffer.hpp
summary: Vulkan buffer. 

---

# liblava/resource/buffer.hpp

Vulkan buffer.  [More...](#detailed-description)

## Namespaces

| Name           |
| -------------- |
| **[lava](/_doxybook/Namespaces/namespacelava.md)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| struct | **[lava::buffer](/_doxybook/Classes/structlava_1_1buffer.md)** <br>Buffer.  |

## Detailed Description

Vulkan buffer. 

**Author**: Lava Block OÜ and contributors 

**Copyright**: Copyright (c) 2018-present, MIT License 



## Source code

```cpp

#pragma once

#include <liblava/base/device.hpp>

namespace lava {

struct buffer : entity {
    using ptr = std::shared_ptr<buffer>;

    using list = std::vector<ptr>;

    static ptr make() {
        return std::make_shared<buffer>();
    }

    ~buffer() {
        destroy();
    }

    bool create(device_p device,
                void const* data,
                size_t size,
                VkBufferUsageFlags usage,
                bool mapped = false,
                VmaMemoryUsage memory_usage = VMA_MEMORY_USAGE_GPU_ONLY);

    bool create_mapped(device_p device,
                       void const* data,
                       size_t size,
                       VkBufferUsageFlags usage,
                       VmaMemoryUsage memory_usage = VMA_MEMORY_USAGE_CPU_TO_GPU);

    void destroy();

    device_p get_device() {
        return device;
    }

    bool valid() const {
        return vk_buffer != VK_NULL_HANDLE;
    }

    VkBuffer get() const {
        return vk_buffer;
    }

    VkDescriptorBufferInfo const* get_descriptor_info() const {
        return &descriptor;
    }

    VkDeviceAddress get_address() const;

    VkDeviceSize get_size() const {
        return allocation_info.size;
    }

    void* get_mapped_data() const {
        return allocation_info.pMappedData;
    }

    VkDeviceMemory get_device_memory() const {
        return allocation_info.deviceMemory;
    }

    void flush(VkDeviceSize offset = 0,
               VkDeviceSize size = VK_WHOLE_SIZE);

    VmaAllocation const& get_allocation() const {
        return allocation;
    }

    VmaAllocationInfo const& get_allocation_info() const {
        return allocation_info;
    }

private:
    device_p device = nullptr;

    VkBuffer vk_buffer = VK_NULL_HANDLE;

    VmaAllocation allocation = nullptr;

    VmaAllocationInfo allocation_info = {};

    VkDescriptorBufferInfo descriptor = {};
};

VkPipelineStageFlags buffer_usage_to_possible_stages(VkBufferUsageFlags usage);

VkAccessFlags buffer_usage_to_possible_access(VkBufferUsageFlags usage);

} // namespace lava
```


-------------------------------

Updated on 2022-11-30 at 01:16:04 +0000
