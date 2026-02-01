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

#include "liblava/base/base.hpp"
#include <memory>

namespace lava {

struct attachment {
    using s_ptr = std::shared_ptr<attachment>;

    using s_list = std::vector<s_ptr>;

    static s_ptr make(VkFormat format = VK_FORMAT_UNDEFINED,
                      VkSampleCountFlagBits samples = VK_SAMPLE_COUNT_1_BIT) {
        return std::make_shared<attachment>(format, samples);
    }

    explicit attachment(VkFormat format = VK_FORMAT_UNDEFINED,
                        VkSampleCountFlagBits samples = VK_SAMPLE_COUNT_1_BIT) {
        m_description.flags = 0;
        m_description.format = format;
        m_description.samples = samples;
        m_description.loadOp = VK_ATTACHMENT_LOAD_OP_LOAD;
        m_description.storeOp = VK_ATTACHMENT_STORE_OP_STORE;
        m_description.stencilLoadOp = VK_ATTACHMENT_LOAD_OP_LOAD;
        m_description.stencilStoreOp = VK_ATTACHMENT_STORE_OP_STORE;
        m_description.initialLayout = VK_IMAGE_LAYOUT_UNDEFINED;
        m_description.finalLayout = VK_IMAGE_LAYOUT_UNDEFINED;
    }

    VkAttachmentDescription const& get_description() const {
        return m_description;
    }

    void set_format(VkFormat format) {
        m_description.format = format;
    }

    void set_samples(VkSampleCountFlagBits samples) {
        m_description.samples = samples;
    }

    void set_op(VkAttachmentLoadOp load_op, VkAttachmentStoreOp store_op) {
        set_load_op(load_op);
        set_store_op(store_op);
    }

    void set_load_op(VkAttachmentLoadOp load_op) {
        m_description.loadOp = load_op;
    }

    void set_store_op(VkAttachmentStoreOp store_op) {
        m_description.storeOp = store_op;
    }

    void set_stencil_op(VkAttachmentLoadOp load_op,
                        VkAttachmentStoreOp store_op) {
        set_stencil_load_op(load_op);
        set_stencil_store_op(store_op);
    }

    void set_stencil_load_op(VkAttachmentLoadOp load_op) {
        m_description.stencilLoadOp = load_op;
    }

    void set_stencil_store_op(VkAttachmentStoreOp store_op) {
        m_description.stencilStoreOp = store_op;
    }

    void set_layouts(VkImageLayout initial,
                     VkImageLayout final) {
        set_initial_layout(initial);
        set_final_layout(final);
    }

    void set_initial_layout(VkImageLayout layout) {
        m_description.initialLayout = layout;
    }

    void set_final_layout(VkImageLayout layout) {
        m_description.finalLayout = layout;
    }

private:
    VkAttachmentDescription m_description;
};

} // namespace lava
```


-------------------------------

Updated on 2026-02-01 at 18:13:39 +0000
