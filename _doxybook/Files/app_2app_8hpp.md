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

## Detailed Description

Application with basic functionality. 

**Author**: Lava Block OÜ and contributors 

**Copyright**: Copyright (c) 2018-present, MIT License 



## Source code

```cpp

#pragma once

#include <liblava/app/benchmark.hpp>
#include <liblava/app/camera.hpp>
#include <liblava/app/config.hpp>
#include <liblava/app/forward_shading.hpp>
#include <liblava/block.hpp>
#include <liblava/frame.hpp>

namespace lava {

constexpr bool const draw_separator = true;

constexpr bool const draw_no_separator = false;

constexpr bool const draw_fps = true;

constexpr bool const draw_no_fps = false;

constexpr bool const draw_spacing = true;

constexpr bool const draw_no_spacing = false;

struct app : frame {
    explicit app(frame_env::ref env);

    explicit app(name name, argh::parser cmd_line = {});

    virtual bool setup();

    window_t window;

    input_t input;

    imgui_t imgui;

    imgui::config imgui_config;

    tooltip_list tooltips;

    device_p device = nullptr;

    camera_t camera;

    gamepad pad;

    staging_t staging;

    block_t block;

    renderer_t renderer;

    forward_shading shading;

    render_target::ptr target;

    run_time_t run_time;

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

    ui32 get_frame_counter() const {
        return frame_counter;
    }

    void draw_about(bool separator = draw_separator,
                    bool fps = draw_fps,
                    bool spacing = draw_spacing) const;

    app_config config;

    json_file config_file;

    using process_func = std::function<void(VkCommandBuffer, index)>;

    process_func on_process;

    id::ref block_cmd() const {
        return block_command;
    }

    using setup_func = std::function<bool()>;

    setup_func on_setup;

    string screenshot();

    void parse_config(argh::parser cmd_line);

private:
    void mount_resource();

    bool setup_file_system();

    bool setup_window();

    bool setup_device();

    bool setup_render();

    void setup_run();

    void handle_config();

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

    texture::ptr imgui_fonts;

    bool toggle_v_sync = false;

    ui32 frame_counter = 0;

    json_file::callback config_callback;

    id block_command;

    benchmark_data frames;
};

} // namespace lava
```


-------------------------------

Updated on 2022-11-30 at 01:16:04 +0000
