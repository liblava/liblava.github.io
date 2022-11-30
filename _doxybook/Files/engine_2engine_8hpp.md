---
title: liblava/engine/engine.hpp
summary: Engine. 

---

# liblava/engine/engine.hpp

Engine.  [More...](#detailed-description)

## Namespaces

| Name           |
| -------------- |
| **[lava](/_doxybook/Namespaces/namespacelava.md)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| struct | **[lava::engine](/_doxybook/Classes/structlava_1_1engine.md)** <br>Engine.  |

## Detailed Description

Engine. 

**Author**: Lava Block OÜ and contributors 

**Copyright**: Copyright (c) 2018-present, MIT License 



## Source code

```cpp

#pragma once

#include <liblava/app/app.hpp>
#include <liblava/engine/producer.hpp>
#include <liblava/engine/property.hpp>

namespace lava {

constexpr name _props_ = "props";

struct engine : app {
    using app::app;

    bool setup() override;

    property props;

    producer_t producer;

private:
    void handle_config();

    json_file::callback config_callback;
};

} // namespace lava
```


-------------------------------

Updated on 2022-11-30 at 01:16:04 +0000
