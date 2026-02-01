---
title: liblava/base/device.hpp
summary: Vulkan device. 

---

# liblava/base/device.hpp

Vulkan device.  [More...](#detailed-description)

## Namespaces

| Name           |
| -------------- |
| **[lava](/_doxybook/Namespaces/namespacelava.md)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| struct | **[lava::device](/_doxybook/Classes/structlava_1_1device.md)** <br>Vulkan device.  |
| struct | **[lava::device::create_param](/_doxybook/Classes/structlava_1_1device_1_1create__param.md)** <br>Device create parameters.  |

## Detailed Description

Vulkan device. 

**Author**: Lava Block OÜ and contributors 

**Copyright**: Copyright (c) 2018-present, MIT License 



## Source code

```cpp


#pragma once

#include "liblava/base/device_table.hpp"
#include "liblava/base/queue.hpp"
#include "liblava/core/data.hpp"
#include "liblava/core/id.hpp"
#include "liblava/fwd.hpp"

namespace lava {

struct device : device_table, entity {
    using ptr = device*;

    using c_ptr = device const*;

    using s_ptr = std::shared_ptr<device>;

    using s_list = std::vector<s_ptr>;

    using physical_device_c_ptr = physical_device const*;

    struct create_param {
        using ref = create_param const&;

        physical_device_c_ptr physical_device = nullptr;

        VmaAllocatorCreateFlags vma_flags = 0;

        names extensions;

        VkPhysicalDeviceFeatures features{};

        bool has_features_2 = false;

        void const* next = nullptr;

        queue_family_info::list queue_family_infos;

        void add_swapchain_extension() {
            extensions.push_back("VK_KHR_swapchain");
        }

        void add_portability_subset_extension() {
            extensions.push_back("VK_KHR_portability_subset");
        }

        void set_default_queues() {
            lava::set_default_queues(queue_family_infos);
        }

        void set_all_queues();

        bool add_queue(VkQueueFlags flags,
                       r32 priority = 1.f) {
            return add_queues(flags, 1, priority);
        }

        bool add_queues(VkQueueFlags flags,
                        ui32 count,
                        r32 priority = 1.f);

        bool add_dedicated_queues(r32 priority = 1.f);

        verify_queues_result verify_queues() const;
    };

    static s_ptr make() {
        return std::make_shared<device>();
    }

    ~device() {
        destroy();
    }

    bool create(create_param::ref param);

    void destroy();

    queue::ref get_graphics_queue(index index = 0) const {
        return get_graphics_queues().at(index);
    }

    queue::ref graphics_queue(index index = 0) const {
        return get_graphics_queue(index);
    }

    queue::ref get_compute_queue(index index = 0) const {
        return get_compute_queues().at(index);
    }

    queue::ref compute_queue(index index = 0) const {
        return get_compute_queue(index);
    }

    queue::ref get_transfer_queue(index index = 0) const {
        return get_transfer_queues().at(index);
    }

    queue::ref transfer_queue(index index = 0) const {
        return get_transfer_queue(index);
    }

    queue::list const& get_graphics_queues() const {
        return m_graphics_queue_list;
    }

    queue::list const& graphics_queues() const {
        return get_graphics_queues();
    }

    queue::list const& get_compute_queues() const {
        return m_compute_queue_list;
    }

    queue::list const& compute_queues() const {
        return get_compute_queues();
    }

    queue::list const& get_transfer_queues() const {
        return m_transfer_queue_list;
    }

    queue::list const& transfer_queues() const {
        return get_transfer_queues();
    }

    queue::list const& get_queues() const {
        return m_queue_list;
    }

    queue::list const& queues() const {
        return get_queues();
    }

    VkDevice get() const {
        return vk_device;
    }

    VolkDeviceTable const& call() const {
        return table;
    }

    bool wait_for_idle() const {
        return check(call().vkDeviceWaitIdle(vk_device));
    }

    physical_device_c_ptr get_physical_device() const {
        return m_physical_device;
    }

    VkPhysicalDevice get_vk_physical_device() const;

    VkPhysicalDeviceFeatures const& get_features() const;

    VkPhysicalDeviceProperties const& get_properties() const;

    bool surface_supported(VkSurfaceKHR surface) const;

    void set_allocator(allocator::s_ptr value) {
        m_mem_allocator = value;
    }

    allocator::s_ptr get_allocator() {
        return m_mem_allocator;
    }

    VmaAllocator alloc() const {
        return m_mem_allocator != nullptr
                   ? m_mem_allocator->get()
                   : nullptr;
    }

private:
    physical_device_c_ptr m_physical_device = nullptr;

    queue::list m_graphics_queue_list;

    queue::list m_compute_queue_list;

    queue::list m_transfer_queue_list;

    queue::list m_queue_list;

    VkPhysicalDeviceFeatures m_features{};

    allocator::s_ptr m_mem_allocator;
};

VkShaderModule create_shader_module(device::ptr device,
                                    c_data::ref data);

using one_time_command_func = std::function<void(VkCommandBuffer)>;

bool one_time_submit_pool(device::ptr device,
                          VkCommandPool pool,
                          queue::ref queue,
                          one_time_command_func callback);

inline bool one_time_submit(device::ptr device,
                            queue::ref queue,
                            one_time_command_func callback) {
    return one_time_submit_pool(device,
                                VK_NULL_HANDLE,
                                queue,
                                callback);
}

} // namespace lava
```


-------------------------------

Updated on 2026-02-01 at 18:13:39 +0000
