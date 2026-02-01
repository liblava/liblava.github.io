---
title: liblava/block/descriptor.hpp
summary: Descriptor definition. 

---

# liblava/block/descriptor.hpp

Descriptor definition.  [More...](#detailed-description)

## Namespaces

| Name           |
| -------------- |
| **[lava](/_doxybook/Namespaces/namespacelava.md)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| struct | **[lava::descriptor](/_doxybook/Classes/structlava_1_1descriptor.md)** <br>Descriptor.  |
| struct | **[lava::descriptor::binding](/_doxybook/Classes/structlava_1_1descriptor_1_1binding.md)** <br>Descriptor binding.  |
| struct | **[lava::descriptor::pool](/_doxybook/Classes/structlava_1_1descriptor_1_1pool.md)** <br>Descriptor pool.  |

## Detailed Description

Descriptor definition. 

**Author**: Lava Block OÜ and contributors 

**Copyright**: Copyright (c) 2018-present, MIT License 



## Source code

```cpp


#pragma once

#include "liblava/base/device.hpp"

namespace lava {

struct descriptor : entity {
    struct binding {
        using s_ptr = std::shared_ptr<binding>;

        using s_list = std::vector<s_ptr>;

        static s_ptr make(index index) {
            auto result = std::make_shared<binding>();
            result->set(index);
            result->set_count(1);
            return result;
        }

        explicit binding();

        VkDescriptorSetLayoutBinding const& get() const {
            return m_vk_binding;
        }

        void set(index index) {
            m_vk_binding.binding = index;
        }

        void set_type(VkDescriptorType descriptor_type) {
            m_vk_binding.descriptorType = descriptor_type;
        }

        void set_count(ui32 descriptor_count) {
            m_vk_binding.descriptorCount = descriptor_count;
        }

        void set_stage_flags(VkShaderStageFlags stage_flags) {
            m_vk_binding.stageFlags = stage_flags;
        }

        void set_samplers(VkSampler const* immutable_samplers) {
            m_vk_binding.pImmutableSamplers = immutable_samplers;
        }

    private:
        VkDescriptorSetLayoutBinding m_vk_binding;
    };

    struct pool : entity {
        using s_ptr = std::shared_ptr<pool>;

        using s_list = std::vector<s_ptr>;

        static s_ptr make() {
            return std::make_shared<descriptor::pool>();
        }

        bool create(device::ptr device,
                    VkDescriptorPoolSizesRef sizes,
                    ui32 max = 1,
                    VkDescriptorPoolCreateFlags flags =
                        VK_DESCRIPTOR_POOL_CREATE_FREE_DESCRIPTOR_SET_BIT);

        void destroy();

        VkDescriptorPool get() const {
            return m_vk_pool;
        }

        device::ptr get_device() {
            return m_device;
        }

        VkDescriptorPoolSizes const& get_sizes() const {
            return m_sizes;
        }

        ui32 get_max() const {
            return m_max;
        }

    private:
        device::ptr m_device = nullptr;

        VkDescriptorPool m_vk_pool = VK_NULL_HANDLE;

        VkDescriptorPoolSizes m_sizes;

        ui32 m_max = 0;
    };

    using s_ptr = std::shared_ptr<descriptor>;

    using s_list = std::vector<s_ptr>;

    static s_ptr make() {
        return std::make_shared<descriptor>();
    }

    void add_binding(index binding,
                     VkDescriptorType descriptor_type,
                     VkShaderStageFlags stage_flags);

    void clear_bindings() {
        m_bindings.clear();
    }

    void add(binding::s_ptr const& binding) {
        m_bindings.push_back(binding);
    }

    bool create(device::ptr device);

    void destroy();

    ui32 get_binding_count() const {
        return to_ui32(m_bindings.size());
    }

    binding::s_list const& get_bindings() {
        return m_bindings;
    }

    VkDescriptorSetLayout get() const {
        return m_layout;
    }

    device::ptr get_device() {
        return m_device;
    }

    VkDescriptorSet allocate_set(VkDescriptorPool pool);

    VkDescriptorSet allocate(VkDescriptorPool pool) {
        return allocate_set(pool);
    }

    bool deallocate_set(VkDescriptorSet& descriptor_set,
                        VkDescriptorPool pool);

    bool deallocate(VkDescriptorSet& descriptor_set,
                    VkDescriptorPool pool) {
        return deallocate_set(descriptor_set, pool);
    }

    VkDescriptorSets allocate_sets(ui32 size,
                                   VkDescriptorPool pool);

    VkDescriptorSets allocate(ui32 size,
                              VkDescriptorPool pool) {
        return allocate_sets(size, pool);
    }

    bool deallocate_sets(VkDescriptorSets& descriptor_sets,
                         VkDescriptorPool pool);

    bool deallocate(VkDescriptorSets& descriptor_sets,
                    VkDescriptorPool pool) {
        return deallocate_sets(descriptor_sets, pool);
    }

private:
    device::ptr m_device = nullptr;

    VkDescriptorSetLayout m_layout = VK_NULL_HANDLE;

    binding::s_list m_bindings;
};

} // namespace lava
```


-------------------------------

Updated on 2026-02-01 at 18:13:39 +0000
