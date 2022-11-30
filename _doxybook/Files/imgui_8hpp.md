---
title: liblava/app/imgui.hpp
summary: ImGui integration. 

---

# liblava/app/imgui.hpp

ImGui integration.  [More...](#detailed-description)

## Namespaces

| Name           |
| -------------- |
| **[lava](/_doxybook/Namespaces/namespacelava.md)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| struct | **[lava::imgui](/_doxybook/Classes/structlava_1_1imgui.md)** <br>ImGui integration.  |
| struct | **[lava::imgui::icon_font](/_doxybook/Classes/structlava_1_1imgui_1_1icon__font.md)** <br>ImGui icon font settings.  |
| struct | **[lava::imgui::font](/_doxybook/Classes/structlava_1_1imgui_1_1font.md)** <br>ImGui font settings.  |
| struct | **[lava::imgui::config](/_doxybook/Classes/structlava_1_1imgui_1_1config.md)** <br>ImGui configuration.  |

## Detailed Description

ImGui integration. 

**Author**: Lava Block OÜ and contributors 

**Copyright**: Copyright (c) 2018-present, MIT License 



## Source code

```cpp

#pragma once

#include <liblava/block/render_pipeline.hpp>
#include <liblava/file.hpp>
#include <liblava/frame/input.hpp>
#include <liblava/resource/texture.hpp>

// fwd
struct GLFWwindow;
struct GLFWcursor;
struct ImDrawData;
struct ImGuiStyle;

namespace lava {

constexpr const r32 default_imgui_font_size = 18.f;

struct imgui {
    explicit imgui() = default;

    explicit imgui(GLFWwindow* window) {
        setup(window);
    }

    ~imgui() {
        destroy();
    }

    struct icon_font {
        data font_data;

        ui16 range_begin = 0;

        ui16 range_end = 0;

        r32 size = default_imgui_font_size;
    };

    struct font {
        using ref = font const&;

        string file;

        r32 size = 21.f;

        string icon_file;

        r32 icon_size = 21.f;

        ui16 icon_range_begin = 0;

        ui16 icon_range_end = 0;
    };

    struct config {
        data font_data;

        r32 font_size = default_imgui_font_size;

        std::shared_ptr<ImGuiStyle> style;

        icon_font icon;

        std::filesystem::path ini_file_dir;
    };

    void setup(GLFWwindow* window, config config);

    void setup(GLFWwindow* window) {
        setup(window, config());
    }

    bool create(render_pipeline::ptr pipeline, index max_frames);

    bool create(device_p device,
                index max_frames,
                VkPipelineCache pipeline_cache) {
        return create(render_pipeline::make(device, pipeline_cache),
                      max_frames);
    }

    bool create(device_p device,
                index max_frames,
                VkRenderPass pass,
                VkPipelineCache pipeline_cache = 0) {
        if (!create(device, max_frames, pipeline_cache))
            return false;

        return pipeline->create(pass);
    }

    bool upload_fonts(texture::ptr texture);

    void destroy();

    bool ready() const {
        return initialized;
    }

    render_pipeline::ptr get_pipeline() {
        return pipeline;
    }

    using draw_func = std::function<void()>;

    draw_func on_draw;

    bool capture_mouse() const;

    bool capture_keyboard() const;

    void set_active(bool value = true) {
        active = value;
    }

    bool activated() const {
        return active;
    }

    void toggle() {
        active = !active;
    }

    void set_ini_file(std::filesystem::path dir);

    std::filesystem::path get_ini_file() const {
        return std::filesystem::path(ini_file);
    }

    void convert_style_to_srgb();

    input_callback const& get_input_callback() const {
        return callback;
    }

private:
    void handle_key_event(i32 key, i32 scancode, i32 action, i32 mods);

    void handle_mouse_button_event(i32 button, i32 action, i32 mods);

    void handle_scroll_event(r64 x_offset, r64 y_offset);

    void prepare_draw_lists(ImDrawData* draw_data);

    void render_draw_lists(VkCommandBuffer cmd_buf);

    void invalidate_device_objects();

    void update_mouse_pos_and_buttons();

    void update_mouse_cursor();

    void new_frame();

    void render(VkCommandBuffer cmd_buf);

    device_p device = nullptr;

    // Initialized state
    bool initialized = false;

    render_pipeline::ptr pipeline;

    pipeline_layout::ptr layout;

    size_t buffer_memory_alignment = 256;

    index frame = 0;

    index max_frames = 4;

    buffer::list vertex_buffers;

    buffer::list index_buffers;

    descriptor_ptr descriptor;

    descriptor::pool::ptr descriptor_pool;

    VkDescriptorSet descriptor_set = VK_NULL_HANDLE;

    GLFWwindow* window = nullptr;

    bool mouse_just_pressed[5] = { false, false, false, false, false };

    r64 current_time = 0.0;

    std::vector<GLFWcursor*> mouse_cursors;

    string ini_file;

    bool active = true;

    input_callback callback;

    std::array<ui16, 3> icons_range;
};

using imgui_t = imgui;

void setup_imgui_font(imgui::config& config,
                      imgui::font::ref font);

void setup_imgui_font_icons(imgui::font& font,
                            string filename,
                            ui16 min, ui16 max);

void imgui_left_spacing(ui32 top = 1);

} // namespace lava
```


-------------------------------

Updated on 2022-11-30 at 01:16:04 +0000
