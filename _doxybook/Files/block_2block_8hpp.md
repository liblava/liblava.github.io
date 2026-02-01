---
title: liblava/block/block.hpp
summary: Command buffer model. 

---

# liblava/block/block.hpp

Command buffer model.  [More...](#detailed-description)

## Namespaces

| Name           |
| -------------- |
| **[lava](/_doxybook/Namespaces/namespacelava.md)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| struct | **[lava::command](/_doxybook/Classes/structlava_1_1command.md)** <br>Block command.  |
| struct | **[lava::block](/_doxybook/Classes/structlava_1_1block.md)** <br>Block of commands.  |

## Detailed Description

Command buffer model. 

**Author**: Lava Block OÜ and contributors 

**Copyright**: Copyright (c) 2018-present, MIT License 



## Source code

```cpp


#pragma once

#include "liblava/base/device.hpp"

namespace lava {

struct command : entity {
    using s_ptr = std::shared_ptr<command>;

    using c_ptr = command const*;

    using s_map = std::map<id, s_ptr>;

    using c_list = std::vector<c_ptr>;

    VkCommandBuffers buffers = {};

    using process_func = std::function<void(VkCommandBuffer)>;

    process_func on_process;

    bool active = true;

    static s_ptr make() {
        return std::make_shared<command>();
    }

    bool create(device::ptr device,
                index frame_count,
                VkCommandPools command_pools);

    void destroy(device::ptr device,
                 VkCommandPools command_pools);
};

struct block : entity {
    using ptr = block*;

    using s_ptr = std::shared_ptr<block>;

    using c_ptr = block const*;

    using s_map = std::map<id, s_ptr>;

    using c_list = std::vector<c_ptr>;

    static s_ptr make() {
        return std::make_shared<block>();
    }

    ~block() {
        destroy();
    }

    bool create(device::ptr device,
                index frame_count,
                index queue_family);

    void destroy();

    index get_frame_count() const {
        return to_index(m_cmd_pools.size());
    }

    id add_cmd(command::process_func func, bool active = true);

    id add_command(command::process_func func, bool active = true) {
        return add_cmd(func, active);
    }

    void remove_cmd(id::ref cmd_id);

    void remove_command(id::ref cmd_id) {
        remove_cmd(cmd_id);
    }

    bool process(index frame);

    index get_current_frame() const {
        return m_current_frame;
    }

    VkCommandBuffer get_command_buffer(id::ref cmd_id) const {
        return m_commands.at(cmd_id)->buffers.at(m_current_frame);
    }

    VkCommandBuffer get_command_buffer(id::ref cmd_id, index frame) const {
        return m_commands.at(cmd_id)->buffers.at(frame);
    }

    VkCommandBuffers collect_buffers() {
        VkCommandBuffers result;

        for (auto& cmd : m_cmd_order)
            if (cmd->active)
                result.push_back(cmd->buffers.at(m_current_frame));

        return result;
    }

    command::s_map const& get_commands() const {
        return m_commands;
    }

    command::c_list const& get_cmd_order() const {
        return m_cmd_order;
    }

    bool activated(id::ref cmd_id);

    bool set_active(id::ref cmd_id, bool active = true);

    device::ptr get_device() {
        return m_device;
    }

private:
    device::ptr m_device = nullptr;

    index m_current_frame = 0;

    VkCommandPools m_cmd_pools = {};

    command::s_map m_commands;

    command::c_list m_cmd_order;
};

} // namespace lava
```


-------------------------------

Updated on 2026-02-01 at 18:13:39 +0000
