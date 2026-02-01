---
title: liblava/app/app.hpp
summary: Application with basic functionality. 

---

# liblava/app/app.hpp

Application with basic functionality.  [More...](#detailed-description)

## Namespaces

| Name           |
| -------------- |
| **[lava](/_doxybook/Namespaces/namespacelava.md)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| struct | **[lava::app](/_doxybook/Classes/structlava_1_1app.md)** <br>Application with basic functionality.  |
| struct | **[lava::app::about_info_setting](/_doxybook/Classes/structlava_1_1app_1_1about__info__setting.md)**  |

## Detailed Description

Application with basic functionality. 

**Author**: Lava Block OÜ and contributors 

**Copyright**: Copyright (c) 2018-present, MIT License 



## Source code

```cpp


#pragma once

#include "liblava/app/benchmark.hpp"
#include "liblava/app/camera.hpp"
#include "liblava/app/config.hpp"
#include "liblava/app/forward_shading.hpp"
#include "liblava/block.hpp"
#include "liblava/frame.hpp"

namespace lava {

struct app : frame {
    explicit app(frame_env::ref env);

    explicit app(name name, argh::parser cmd_line = {});

    virtual bool setup();

    bool headless = false;

    lava::window window;

    lava::input input;

    lava::imgui imgui;

    imgui::config imgui_config;

    tooltip_list tooltips;

    lava::device::ptr device = nullptr;

    lava::camera camera;

    gamepad pad;

    lava::staging staging;

    lava::block block;

    lava::renderer renderer;

    forward_shading shading;

    render_target::s_ptr target;

    file_system fs;

    VkPipelineCache pipeline_cache = nullptr;

    using update_func = std::function<bool(delta)>;

    update_func on_update;

    using create_func = std::function<bool()>;

    create_func on_create;

    using destroy_func = std::function<void()>;

    destroy_func on_destroy;

    bool v_sync() const {
        return config.v_sync;
    }

    bool triple_buffer() const {
        return config.triple_buffer;
    }

    ui32 fps_cap() const {
        return config.fps_cap;
    }

    ui32 get_frame_counter() const {
        return m_frame_counter;
    }

    string get_fps_info() const;

    struct about_info_setting {
        bool draw_separator = true;

        bool draw_fps = true;

        bool draw_spacing = true;

        static about_info_setting all() {
            return {};
        }
    };

    void draw_about(about_info_setting setting = about_info_setting::all()) const;

    app_config config;

    json_file config_file;

    using process_func = std::function<void(VkCommandBuffer, index)>;

    process_func on_process;

    id::ref block_cmd() const {
        return m_block_command;
    }

    using setup_func = std::function<bool()>;

    setup_func on_setup;

    string screenshot();

    void switch_config(string_ref config_name);

private:
    void mount_resource();

    bool setup_file_system();

    bool setup_window();

    bool setup_device();

    bool setup_render();

    void setup_run();

    void parse_cmd_line();

    bool load_config(string_ref config_name);

    void handle_input();

    void handle_keys();

    void handle_window();

    void update();

    void render();

    bool create_imgui();

    void destroy_imgui();

    bool create_target();

    void destroy_target();

    bool create_block();

    bool create_pipeline_cache();

    void destroy_pipeline_cache();

    texture::s_ptr m_imgui_fonts;

    bool m_toggle_v_sync = false;

    ui32 m_frame_counter = 0;

    us m_last_render_time{0};

    json_file::callback m_config_callback;

    id m_block_command;

    benchmark_data m_frames;
};

} // namespace lava
```


-------------------------------

Updated on 2026-02-01 at 18:13:39 +0000
