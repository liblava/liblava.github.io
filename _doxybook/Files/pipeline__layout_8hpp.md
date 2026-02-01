---
title: liblava/block/pipeline_layout.hpp
summary: Pipeline layout. 

---

# liblava/block/pipeline_layout.hpp

Pipeline layout.  [More...](#detailed-description)

## Namespaces

| Name           |
| -------------- |
| **[lava](/_doxybook/Namespaces/namespacelava.md)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| struct | **[lava::pipeline_layout](/_doxybook/Classes/structlava_1_1pipeline__layout.md)** <br>Pipeline layout.  |

## Detailed Description

Pipeline layout. 

**Author**: Lava Block OÜ and contributors 

**Copyright**: Copyright (c) 2018-present, MIT License 



## Source code

```cpp


#pragma once

#include "liblava/block/descriptor.hpp"

namespace lava {

struct pipeline_layout : entity {
    using s_ptr = std::shared_ptr<pipeline_layout>;

    using s_list = std::vector<s_ptr>;

    static s_ptr make() {
        return std::make_shared<pipeline_layout>();
    }

    void add(descriptor::s_ptr const& descriptor) {
        m_descriptors.push_back(descriptor);
    }

    void add(VkPushConstantRange const& range) {
        m_push_constant_ranges.push_back(range);
    }

    void add_descriptor(descriptor::s_ptr const& descriptor) {
        add(descriptor);
    }

    void add_push_constant_range(VkPushConstantRange const& range) {
        add(range);
    }

    void clear_descriptors() {
        m_descriptors.clear();
    }

    void clear_ranges() {
        m_push_constant_ranges.clear();
    }

    void clear() {
        clear_descriptors();
        clear_ranges();
    }

    bool create(device::ptr device);

    void destroy();

    VkPipelineLayout get() const {
        return m_layout;
    }

    device::ptr get_device() {
        return m_device;
    }

    descriptor::s_list const& get_descriptors() const {
        return m_descriptors;
    }

    VkPushConstantRanges const& get_push_constant_ranges() const {
        return m_push_constant_ranges;
    }

    using offset_list = std::vector<index>;

    void bind_descriptor_set(VkCommandBuffer cmd_buf,
                             VkDescriptorSet descriptor_set,
                             index first_set = 0,
                             offset_list offsets = {},
                             VkPipelineBindPoint bind_point = VK_PIPELINE_BIND_POINT_GRAPHICS);

    void bind(VkCommandBuffer cmd_buf,
              VkDescriptorSet descriptor_set,
              index first_set = 0,
              offset_list offsets = {},
              VkPipelineBindPoint bind_point = VK_PIPELINE_BIND_POINT_GRAPHICS) {
        bind_descriptor_set(cmd_buf,
                            descriptor_set,
                            first_set,
                            offsets,
                            bind_point);
    }

private:
    device::ptr m_device = nullptr;

    VkPipelineLayout m_layout = VK_NULL_HANDLE;

    descriptor::s_list m_descriptors;

    VkPushConstantRanges m_push_constant_ranges;
};

} // namespace lava
```


-------------------------------

Updated on 2026-02-01 at 18:13:39 +0000
