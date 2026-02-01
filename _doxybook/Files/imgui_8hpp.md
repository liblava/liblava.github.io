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

#include "liblava/block/render_pipeline.hpp"
#include "liblava/file.hpp"
#include "liblava/frame/input.hpp"
#include "liblava/resource/texture.hpp"
#include "liblava/util/layer.hpp"

// fwd
struct GLFWwindow;
struct GLFWcursor;
struct ImDrawData;
struct ImGuiStyle;

namespace lava {

constexpr const r32 default_imgui_font_size = 18.f;

struct imgui {
    using ptr = imgui*;

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

        i32 flags = 0;
    };

    void setup(GLFWwindow* window, config config);

    void setup(GLFWwindow* win) {
        setup(win, config());
    }

    bool create(render_pipeline::s_ptr pipeline, index max_frames);

    bool create(device::ptr dev,
                index frames,
                VkPipelineCache pipeline_cache) {
        return create(render_pipeline::make(dev, pipeline_cache),
                      frames);
    }

    bool create(device::ptr dev,
                index frames,
                VkRenderPass pass,
                VkPipelineCache pipeline_cache = 0) {
        if (!create(dev, frames, pipeline_cache))
            return false;

        return m_pipeline->create(pass);
    }

    bool upload_fonts(texture::s_ptr texture);

    void destroy();

    bool ready() const {
        return m_initialized;
    }

    render_pipeline::s_ptr get_pipeline() {
        return m_pipeline;
    }

    using draw_func = std::function<void()>;

    draw_func on_draw;

    layer_list layers;

    bool capture_mouse() const;

    bool capture_keyboard() const;

    void set_active(bool value = true) {
        m_active = value;
    }

    bool activated() const {
        return m_active;
    }

    void toggle() {
        m_active = !m_active;
    }

    void set_ini_file(std::filesystem::path dir);

    std::filesystem::path get_ini_file() const {
        return std::filesystem::path(m_ini_file);
    }

    void convert_style_to_srgb();

    input_callback const& get_input_callback() const {
        return m_callback;
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

    device::ptr m_device = nullptr;

    // Initialized state
    bool m_initialized = false;

    render_pipeline::s_ptr m_pipeline;

    pipeline_layout::s_ptr m_layout;

    size_t m_buffer_memory_alignment = 256;

    index m_frame = 0;

    index m_max_frames = 4;

    buffer::s_list m_vertex_buffers;

    buffer::s_list m_index_buffers;

    descriptor::s_ptr m_descriptor;

    descriptor::pool::s_ptr m_descriptor_pool;

    VkDescriptorSet m_descriptor_set = VK_NULL_HANDLE;

    GLFWwindow* m_window = nullptr;

    bool m_mouse_just_pressed[5] = {false, false, false, false, false};

    r64 m_current_time = 0.0;

    std::vector<GLFWcursor*> m_mouse_cursors;

    string m_ini_file;

    bool m_active = true;

    input_callback m_callback;

    std::array<ui16, 3> m_icons_range;
};

void setup_imgui_font(imgui::config& config,
                      imgui::font::ref font);

void setup_imgui_font_icons(imgui::font& font,
                            string filename,
                            ui16 min, ui16 max);

void imgui_left_spacing(ui32 top = 1);

} // namespace lava
```


-------------------------------

Updated on 2026-02-01 at 18:13:39 +0000
