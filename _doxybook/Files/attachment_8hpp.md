---
title: liblava/block/attachment.hpp
summary: Attachment description. 

---

# liblava/block/attachment.hpp

Attachment description.  [More...](#detailed-description)

## Namespaces

| Name           |
| -------------- |
| **[lava](/_doxybook/Namespaces/namespacelava.md)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| struct | **[lava::attachment](/_doxybook/Classes/structlava_1_1attachment.md)** <br>Attachment description.  |

## Detailed Description

Attachment description. 

**Author**: Lava Block OÜ and contributors 

**Copyright**: Copyright (c) 2018-present, MIT License 



## Source code

```cpp

#pragma once

#include <memory>
#include "liblava/base/base.hpp"

namespace lava {

struct attachment {
    using ptr = std::shared_ptr<attachment>;

    using list = std::vector<ptr>;

    static ptr make(VkFormat format = VK_FORMAT_UNDEFINED,
                    VkSampleCountFlagBits samples = VK_SAMPLE_COUNT_1_BIT) {
        return std::make_shared<attachment>(format, samples);
    }

    explicit attachment(VkFormat format = VK_FORMAT_UNDEFINED,
                        VkSampleCountFlagBits samples = VK_SAMPLE_COUNT_1_BIT) {
        description.flags = 0;
        description.format = format;
        description.samples = samples;
        description.loadOp = VK_ATTACHMENT_LOAD_OP_LOAD;
        description.storeOp = VK_ATTACHMENT_STORE_OP_STORE;
        description.stencilLoadOp = VK_ATTACHMENT_LOAD_OP_LOAD;
        description.stencilStoreOp = VK_ATTACHMENT_STORE_OP_STORE;
        description.initialLayout = VK_IMAGE_LAYOUT_UNDEFINED;
        description.finalLayout = VK_IMAGE_LAYOUT_UNDEFINED;
    }

    VkAttachmentDescription const& get_description() const {
        return description;
    }

    void set_format(VkFormat format) {
        description.format = format;
    }

    void set_samples(VkSampleCountFlagBits samples) {
        description.samples = samples;
    }

    void set_op(VkAttachmentLoadOp load_op, VkAttachmentStoreOp store_op) {
        set_load_op(load_op);
        set_store_op(store_op);
    }

    void set_load_op(VkAttachmentLoadOp load_op) {
        description.loadOp = load_op;
    }

    void set_store_op(VkAttachmentStoreOp store_op) {
        description.storeOp = store_op;
    }

    void set_stencil_op(VkAttachmentLoadOp load_op,
                        VkAttachmentStoreOp store_op) {
        set_stencil_load_op(load_op);
        set_stencil_store_op(store_op);
    }

    void set_stencil_load_op(VkAttachmentLoadOp load_op) {
        description.stencilLoadOp = load_op;
    }

    void set_stencil_store_op(VkAttachmentStoreOp store_op) {
        description.stencilStoreOp = store_op;
    }

    void set_layouts(VkImageLayout initial,
                     VkImageLayout final) {
        set_initial_layout(initial);
        set_final_layout(final);
    }

    void set_initial_layout(VkImageLayout layout) {
        description.initialLayout = layout;
    }

    void set_final_layout(VkImageLayout layout) {
        description.finalLayout = layout;
    }

private:
    VkAttachmentDescription description;
};

} // namespace lava
```


-------------------------------

Updated on 2024-03-22 at 21:51:38 +0000
