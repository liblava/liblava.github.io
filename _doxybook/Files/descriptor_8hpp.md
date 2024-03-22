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
        using ptr = std::shared_ptr<binding>;

        using list = std::vector<ptr>;

        static ptr make(index index) {
            auto result = std::make_shared<binding>();
            result->set(index);
            result->set_count(1);
            return result;
        }

        explicit binding();

        VkDescriptorSetLayoutBinding const& get() const {
            return vk_binding;
        }

        void set(index index) {
            vk_binding.binding = index;
        }

        void set_type(VkDescriptorType descriptor_type) {
            vk_binding.descriptorType = descriptor_type;
        }

        void set_count(ui32 descriptor_count) {
            vk_binding.descriptorCount = descriptor_count;
        }

        void set_stage_flags(VkShaderStageFlags stage_flags) {
            vk_binding.stageFlags = stage_flags;
        }

        void set_samplers(VkSampler const* immutable_samplers) {
            vk_binding.pImmutableSamplers = immutable_samplers;
        }

    private:
        VkDescriptorSetLayoutBinding vk_binding;
    };

    struct pool : entity {
        using ptr = std::shared_ptr<pool>;

        using list = std::vector<ptr>;

        static ptr make() {
            return std::make_shared<descriptor::pool>();
        }

        bool create(device_p device,
                    VkDescriptorPoolSizesRef sizes,
                    ui32 max = 1,
                    VkDescriptorPoolCreateFlags flags =
                        VK_DESCRIPTOR_POOL_CREATE_FREE_DESCRIPTOR_SET_BIT);

        void destroy();

        VkDescriptorPool get() const {
            return vk_pool;
        }

        device_p get_device() {
            return device;
        }

        VkDescriptorPoolSizes const& get_sizes() const {
            return sizes;
        }

        ui32 get_max() const {
            return max;
        }

    private:
        device_p device = nullptr;

        VkDescriptorPool vk_pool = VK_NULL_HANDLE;

        VkDescriptorPoolSizes sizes;

        ui32 max = 0;
    };

    using ptr = std::shared_ptr<descriptor>;

    using list = std::vector<ptr>;

    static ptr make() {
        return std::make_shared<descriptor>();
    }

    void add_binding(index binding,
                     VkDescriptorType descriptor_type,
                     VkShaderStageFlags stage_flags);

    void clear_bindings() {
        bindings.clear();
    }

    void add(binding::ptr const& binding) {
        bindings.push_back(binding);
    }

    bool create(device_p device);

    void destroy();

    ui32 get_binding_count() const {
        return to_ui32(bindings.size());
    }

    binding::list const& get_bindings() {
        return bindings;
    }

    VkDescriptorSetLayout get() const {
        return layout;
    }

    device_p get_device() {
        return device;
    }

    VkDescriptorSet allocate_set(VkDescriptorPool pool);

    VkDescriptorSet allocate(VkDescriptorPool pool) {
        return allocate_set(pool);
    }

    bool free_set(VkDescriptorSet& descriptor_set,
                  VkDescriptorPool pool);

    bool free(VkDescriptorSet& descriptor_set,
              VkDescriptorPool pool) {
        return free_set(descriptor_set, pool);
    }

    VkDescriptorSets allocate_sets(ui32 size,
                                   VkDescriptorPool pool);

    VkDescriptorSets allocate(ui32 size,
                              VkDescriptorPool pool) {
        return allocate_sets(size, pool);
    }

    bool free_sets(VkDescriptorSets& descriptor_sets,
                   VkDescriptorPool pool);

    bool free(VkDescriptorSets& descriptor_sets,
              VkDescriptorPool pool) {
        return free_sets(descriptor_sets, pool);
    }

private:
    device_p device = nullptr;

    VkDescriptorSetLayout layout = VK_NULL_HANDLE;

    binding::list bindings;
};

using descriptor_ptr = descriptor::ptr;

} // namespace lava
```


-------------------------------

Updated on 2024-03-22 at 21:51:38 +0000
