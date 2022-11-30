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

#include <liblava/block/descriptor.hpp>

namespace lava {

struct pipeline_layout : entity {
    using ptr = std::shared_ptr<pipeline_layout>;

    using list = std::vector<ptr>;

    static ptr make() {
        return std::make_shared<pipeline_layout>();
    }

    void add(descriptor::ptr const& descriptor) {
        descriptors.push_back(descriptor);
    }

    void add(VkPushConstantRange const& range) {
        push_constant_ranges.push_back(range);
    }

    void add_descriptor(descriptor::ptr const& descriptor) {
        add(descriptor);
    }

    void add_push_constant_range(VkPushConstantRange const& range) {
        add(range);
    }

    void clear_descriptors() {
        descriptors.clear();
    }

    void clear_ranges() {
        push_constant_ranges.clear();
    }

    void clear() {
        clear_descriptors();
        clear_ranges();
    }

    bool create(device_p device);

    void destroy();

    VkPipelineLayout get() const {
        return layout;
    }

    device_p get_device() {
        return device;
    }

    descriptor::list const& get_descriptors() const {
        return descriptors;
    }

    VkPushConstantRanges const& get_push_constant_ranges() const {
        return push_constant_ranges;
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
    device_p device = nullptr;

    VkPipelineLayout layout = VK_NULL_HANDLE;

    descriptor::list descriptors;

    VkPushConstantRanges push_constant_ranges;
};

} // namespace lava
```


-------------------------------

Updated on 2022-11-30 at 01:16:04 +0000
