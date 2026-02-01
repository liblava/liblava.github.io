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

#include "liblava/app/app.hpp"
#include "liblava/engine/producer.hpp"
#include "liblava/engine/props.hpp"

namespace lava {

constexpr name _props_ = "props";

struct engine : app {
    // Pointer to engine
    using ptr = engine*;

    using app::app;

    bool setup() override;

    lava::props props;

    lava::producer producer;

    using hud_menu_func = std::function<void()>;

    hud_menu_func on_menu;

    bool hud_active = false;

private:
    void handle_config();

    void hud_menu();

    id m_menu_layer;

#if LAVA_DEBUG
    id m_demo_layer;
#endif

    json_file::callback m_config_callback;
};

} // namespace lava
```


-------------------------------

Updated on 2026-02-01 at 18:13:39 +0000
