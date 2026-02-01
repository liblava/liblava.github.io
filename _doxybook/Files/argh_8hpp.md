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

#include "argh.h"
#include "liblava/core/types.hpp"

namespace lava {

using cmd_line = argh::parser const&;

void log_command_line(cmd_line cmd_line);

string get_cmd(cmd_line cmd_line,
               std::initializer_list<name const> names);

} // namespace lava
```


-------------------------------

Updated on 2026-02-01 at 18:13:39 +0000
