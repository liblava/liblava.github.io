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

#include "liblava/base/device.hpp"

namespace lava {

struct buffer : entity {
    using s_ptr = std::shared_ptr<buffer>;

    using s_list = std::vector<s_ptr>;

    static s_ptr make() {
        return std::make_shared<buffer>();
    }

    ~buffer() {
        destroy();
    }

    bool create(device::ptr device,
                void const* data,
                size_t size,
                VkBufferUsageFlags usage,
                bool mapped = false,
                VmaMemoryUsage memory_usage = VMA_MEMORY_USAGE_GPU_ONLY,
                VkSharingMode sharing_mode = VK_SHARING_MODE_EXCLUSIVE,
                std::vector<ui32> const& shared_queue_family_indices = {},
                i32 alignment = undef);

    bool create_mapped(device::ptr device,
                       void const* data,
                       size_t size,
                       VkBufferUsageFlags usage,
                       VmaMemoryUsage memory_usage = VMA_MEMORY_USAGE_CPU_TO_GPU,
                       VkSharingMode sharing_mode = VK_SHARING_MODE_EXCLUSIVE,
                       std::vector<ui32> const& shared_queue_family_indices = {},
                       i32 alignment = undef);

    void destroy();

    device::ptr get_device() {
        return m_device;
    }

    bool valid() const {
        return m_vk_buffer != VK_NULL_HANDLE;
    }

    VkBuffer get() const {
        return m_vk_buffer;
    }

    VkDescriptorBufferInfo const* get_descriptor_info() const {
        return &m_descriptor;
    }

    VkDeviceAddress get_address() const;

    VkDeviceSize get_size() const {
        return m_allocation_info.size;
    }

    void* get_mapped_data() const {
        return m_allocation_info.pMappedData;
    }

    VkDeviceMemory get_device_memory() const {
        return m_allocation_info.deviceMemory;
    }

    void flush(VkDeviceSize offset = 0,
               VkDeviceSize size = VK_WHOLE_SIZE);

    VmaAllocation const& get_allocation() const {
        return m_allocation;
    }

    VmaAllocationInfo const& get_allocation_info() const {
        return m_allocation_info;
    }

private:
    device::ptr m_device = nullptr;

    VkBuffer m_vk_buffer = VK_NULL_HANDLE;

    VmaAllocation m_allocation = nullptr;

    VmaAllocationInfo m_allocation_info = {};

    VkDescriptorBufferInfo m_descriptor = {};
};

VkPipelineStageFlags buffer_usage_to_possible_stages(VkBufferUsageFlags usage);

VkAccessFlags buffer_usage_to_possible_access(VkBufferUsageFlags usage);

} // namespace lava
```


-------------------------------

Updated on 2026-02-01 at 18:13:39 +0000
