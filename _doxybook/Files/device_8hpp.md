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

#include <liblava/base/device_table.hpp>
#include <liblava/base/queue.hpp>
#include <liblava/core/data.hpp>
#include <liblava/core/id.hpp>
#include <liblava/fwd.hpp>

namespace lava {

using device_p = device*;

using device_cp = device const*;

using physical_device_cp = physical_device const*;

struct device : device_table, entity {
    using ptr = std::shared_ptr<device>;

    using list = std::vector<ptr>;

    struct create_param {
        using ref = create_param const&;

        physical_device_cp physical_device = nullptr;

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

    static ptr make() {
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
        return graphics_queue_list;
    }

    queue::list const& graphics_queues() const {
        return get_graphics_queues();
    }

    queue::list const& get_compute_queues() const {
        return compute_queue_list;
    }

    queue::list const& compute_queues() const {
        return get_compute_queues();
    }

    queue::list const& get_transfer_queues() const {
        return transfer_queue_list;
    }

    queue::list const& transfer_queues() const {
        return get_transfer_queues();
    }

    queue::list const& get_queues() const {
        return queue_list;
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

    physical_device_cp get_physical_device() const {
        return physical_device;
    }

    VkPhysicalDevice get_vk_physical_device() const;

    VkPhysicalDeviceFeatures const& get_features() const;

    VkPhysicalDeviceProperties const& get_properties() const;

    bool surface_supported(VkSurfaceKHR surface) const;

    void set_allocator(allocator::ptr value) {
        mem_allocator = value;
    }

    allocator::ptr get_allocator() {
        return mem_allocator;
    }

    VmaAllocator alloc() const {
        return mem_allocator != nullptr
                   ? mem_allocator->get()
                   : nullptr;
    }

private:
    physical_device_cp physical_device = nullptr;

    queue::list graphics_queue_list;

    queue::list compute_queue_list;

    queue::list transfer_queue_list;

    queue::list queue_list;

    VkPhysicalDeviceFeatures features{};

    allocator::ptr mem_allocator;
};

VkShaderModule create_shader_module(device_p device,
                                    cdata::ref data);

using one_time_command_func = std::function<void(VkCommandBuffer)>;

bool one_time_submit_pool(device_p device,
                          VkCommandPool pool,
                          queue::ref queue,
                          one_time_command_func callback);

inline bool one_time_submit(device_p device,
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

Updated on 2022-11-30 at 01:16:04 +0000
