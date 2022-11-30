---
title: liblava/frame/argh.hpp
summary: Json. 

---

# liblava/frame/argh.hpp

Json.  [More...](#detailed-description)

## Namespaces

| Name           |
| -------------- |
| **[lava](/_doxybook/Namespaces/namespacelava.md)**  |

## Detailed Description

Json. 

**Author**: Lava Block OÜ and contributors 

**Copyright**: Copyright (c) 2018-present, MIT License 

Command line arguments.




## Source code

```cpp

#pragma once

#include <argh.h>
#include <liblava/util/log.hpp>

namespace lava {

using cmd_line = argh::parser const&;

inline void log_command_line(cmd_line cmd_line) {
    if (!cmd_line.pos_args().empty()) {
        for (auto const& pos_arg : cmd_line.pos_args())
            log()->info("cmd {}", pos_arg);
    }

    if (!cmd_line.flags().empty()) {
        for (auto const& flag : cmd_line.flags())
            log()->info("cmd flag: {}", flag);
    }

    if (!cmd_line.params().empty()) {
        for (auto const& [key, value] : cmd_line.params())
            log()->info("cmd param: {} = {}", key, value);
    }
}

} // namespace lava
```


-------------------------------

Updated on 2022-11-30 at 01:16:04 +0000
