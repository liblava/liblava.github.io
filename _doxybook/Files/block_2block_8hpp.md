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

#include <liblava/base/device.hpp>

namespace lava {

struct command : entity {
    using ptr = std::shared_ptr<command>;

    using cptr = command const*;

    using map = std::map<id, ptr>;

    using clist = std::vector<cptr>;

    VkCommandBuffers buffers = {};

    using process_func = std::function<void(VkCommandBuffer)>;

    process_func on_process;

    bool active = true;

    static ptr make() {
        return std::make_shared<command>();
    }

    bool create(device_p device,
                index frame_count,
                VkCommandPools command_pools);

    void destroy(device_p device,
                 VkCommandPools command_pools);
};

struct block : entity {
    using ptr = std::shared_ptr<block>;

    using cptr = command const*;

    using map = std::map<id, ptr>;

    using clist = std::vector<cptr>;

    static ptr make() {
        return std::make_shared<block>();
    }

    ~block() {
        destroy();
    }

    bool create(device_p device,
                index frame_count,
                index queue_family);

    void destroy();

    index get_frame_count() const {
        return to_index(cmd_pools.size());
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
        return current_frame;
    }

    VkCommandBuffer get_command_buffer(id::ref cmd_id) const {
        return commands.at(cmd_id)->buffers.at(current_frame);
    }

    VkCommandBuffer get_command_buffer(id::ref cmd_id, index frame) const {
        return commands.at(cmd_id)->buffers.at(frame);
    }

    VkCommandBuffers get_buffers() {
        VkCommandBuffers result;

        for (auto& cmd : cmd_order)
            if (cmd->active)
                result.push_back(cmd->buffers.at(current_frame));

        return result;
    }

    command::map const& get_commands() const {
        return commands;
    }

    command::clist const& get_cmd_order() const {
        return cmd_order;
    }

    bool activated(id::ref cmd_id);

    bool set_active(id::ref cmd_id, bool active = true);

    device_p get_device() {
        return device;
    }

private:
    device_p device = nullptr;

    index current_frame = 0;

    VkCommandPools cmd_pools = {};

    command::map commands;

    command::clist cmd_order;
};

using block_t = block;

} // namespace lava
```


-------------------------------

Updated on 2022-11-30 at 01:16:04 +0000
