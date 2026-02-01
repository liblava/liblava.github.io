---
title: liblava/base/memory.hpp
summary: Vulkan allocator. 

---

# liblava/base/memory.hpp

Vulkan allocator.  [More...](#detailed-description)

## Namespaces

| Name           |
| -------------- |
| **[lava](/_doxybook/Namespaces/namespacelava.md)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| struct | **[lava::allocator](/_doxybook/Classes/structlava_1_1allocator.md)** <br>Vulkan allocator.  |
| struct | **[lava::memory](/_doxybook/Classes/structlava_1_1memory.md)** <br>Vulkan memory.  |

## Detailed Description

Vulkan allocator. 

**Author**: Lava Block OÜ and contributors 

**Copyright**: Copyright (c) 2018-present, MIT License 



## Source code

```cpp


#pragma once

// clang-format off

#include "liblava/base/base.hpp"
#include "liblava/fwd.hpp"
#include "vk_mem_alloc.h"
#include <memory>

// clang-format on

namespace lava {

struct allocator {
    using s_ptr = std::shared_ptr<allocator>;

    using device_c_ptr = device const*;

    static s_ptr make() {
        return std::make_shared<allocator>();
    }

    allocator() = default;

    explicit allocator(VmaAllocator allocator)
    : m_allocator(allocator) {}

    bool create(device_c_ptr device,
                VmaAllocatorCreateFlags flags = 0);

    void destroy();

    bool valid() const {
        return m_allocator != nullptr;
    }

    VmaAllocator get() const {
        return m_allocator;
    }

private:
    VmaAllocator m_allocator = nullptr;
};

inline allocator::s_ptr create_allocator(allocator::device_c_ptr device,
                                         VmaAllocatorCreateFlags flags = 0) {
    auto result = allocator::make();
    if (!result->create(device, flags))
        return nullptr;

    return result;
}

struct memory : no_copy_no_move {
    memory();

    static memory& instance() {
        static memory memory;
        return memory;
    }

    VkAllocationCallbacks* alloc() {
        if (m_use_custom_cpu_callbacks)
            return &m_vk_callbacks;

        return nullptr;
    }

    void set_callbacks(VkAllocationCallbacks const& callbacks) {
        m_vk_callbacks = callbacks;
    }

    void set_use_custom_cpu_callbacks(bool value) {
        m_use_custom_cpu_callbacks = value;
    }

private:
    bool m_use_custom_cpu_callbacks = true;

    VkAllocationCallbacks m_vk_callbacks = {};
};

index find_memory_type_with_properties(VkPhysicalDeviceMemoryProperties properties,
                                       ui32 type_bits,
                                       VkMemoryPropertyFlags required_properties);

index find_memory_type(VkPhysicalDevice gpu,
                       VkMemoryPropertyFlags properties,
                       ui32 type_bits);

} // namespace lava
```


-------------------------------

Updated on 2026-02-01 at 18:13:39 +0000
