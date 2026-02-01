---
title: liblava/app/config.hpp
summary: Application configuration. 

---

# liblava/app/config.hpp

Application configuration.  [More...](#detailed-description)

## Namespaces

| Name           |
| -------------- |
| **[lava](/_doxybook/Namespaces/namespacelava.md)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| struct | **[lava::app_config](/_doxybook/Classes/structlava_1_1app__config.md)** <br>Application configuration.  |

## Detailed Description

Application configuration. 

**Author**: Lava Block OÜ and contributors 

**Copyright**: Copyright (c) 2018-present, MIT License 



## Source code

```cpp


#pragma once

#include "liblava/app/imgui.hpp"
#include "liblava/frame/window.hpp"
#include "liblava/fwd.hpp"
#include "liblava/resource/format.hpp"

namespace lava {

struct app_config : configurable {
    app* context = nullptr;

    name org = _liblava_;

    name ext = "zip";

    bool save_window = true;

    bool handle_key_events = true;

    bool v_sync = false;

    bool triple_buffer = true;

    ui32 fps_cap = 0;

    surface_format_request surface;

    index physical_device = 0;

    imgui::font imgui_font;

    string name_id = _default_;

    void set_json(json_ref j) override;

    json get_json() const override;

    void update_window_state();

    window::state::optional window_state;
};

void set_window_icon(window& window, string_ref icon_file = "icon.png");

} // namespace lava
```


-------------------------------

Updated on 2026-02-01 at 18:13:39 +0000
