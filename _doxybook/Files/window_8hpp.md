---
title: liblava/frame/window.hpp
summary: Window. 

---

# liblava/frame/window.hpp

Window.  [More...](#detailed-description)

## Namespaces

| Name           |
| -------------- |
| **[lava](/_doxybook/Namespaces/namespacelava.md)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| struct | **[lava::window](/_doxybook/Classes/structlava_1_1window.md)** <br>Window.  |
| struct | **[lava::window::state](/_doxybook/Classes/structlava_1_1window_1_1state.md)** <br>Window state.  |

## Defines

|                | Name           |
| -------------- | -------------- |
|  | **[VK_NO_PROTOTYPES](/_doxybook/Files/window_8hpp.md#define-vk-no-prototypes)**  |

## Detailed Description

Window. 

**Author**: Lava Block OÜ and contributors 

**Copyright**: Copyright (c) 2018-present, MIT License 



## Macros Documentation

### define VK_NO_PROTOTYPES

```cpp
#define VK_NO_PROTOTYPES 
```


## Source code

```cpp


#pragma once

#include "liblava/core/data.hpp"
#include "liblava/frame/input.hpp"
#include "liblava/util/math.hpp"

#define VK_NO_PROTOTYPES
#include "vulkan/vulkan.h"
#include <optional>

struct GLFWwindow;

namespace lava {

struct window : entity {
    struct state {
        using ref = state const&;

        using optional = std::optional<window::state>;

        explicit state() {}

        i32 x = 0;

        i32 y = 0;

        ui32 width = 0;

        ui32 height = 0;

        bool fullscreen = false;

        bool floating = false;

        bool resizable = true;

        bool decorated = true;

        bool maximized = false;

        index monitor = 0;
    };

    using ptr = window*;

    using s_ptr = std::shared_ptr<window>;

    using event = std::function<void(s_ptr)>;

    using s_map = std::map<id, s_ptr>;

    using ref = window const&;

    window() = default;

    explicit window(name title)
    : m_title(title) {}

    bool create(state::optional state = {});

    void destroy();

    state get_state() const;

    void set_state(state& s);

    void set_title(string_ref text);

    string_ref get_title() const {
        return m_title;
    }

    void set_save_name(string_ref save) {
        m_save_name = save;
    }

    string_ref get_save_name() const {
        return m_save_name;
    }

    void set_position(i32 x, i32 y);

    void get_position(i32& x, i32& y) const;

    void set_size(ui32 width, ui32 height);

    void get_size(ui32& width, ui32& height) const;

    void get_framebuffer_size(ui32& width, ui32& height) const;

    uv2 get_size() const;

    uv2 get_framebuffer_size() const;

    void set_mouse_position(r64 x, r64 y);

    void get_mouse_position(r64& x, r64& y) const;

    v2 get_content_scale() const;

    mouse_position get_mouse_position() const;

    void hide_mouse_cursor();

    void show_mouse_cursor();

    r32 get_aspect_ratio() const;

    void show();

    void hide();

    bool visible() const;

    void iconify();

    bool iconified() const;

    void restore();

    void maximize();

    bool maximized() const;

    void focus();

    bool focused() const;

    void set_fullscreen(bool active) {
        if (m_fullscreen_active != active)
            m_switch_mode_request_active = true;
    }

    bool fullscreen() const {
        return m_fullscreen_active;
    }

    bool hovered() const;

    bool resizable() const;

    void set_resizable(bool value);

    bool decorated() const;

    void set_decorated(bool value);

    bool floating() const;

    void set_floating(bool value);

    bool close_request() const;

    bool switch_mode_request() const {
        return m_switch_mode_request_active;
    }

    bool switch_mode(state::optional state = {});

    GLFWwindow* get() const {
        return m_handle;
    }

    bool resize_request() const {
        return m_resize_request_active;
    }

    bool handle_resize() {
        if (on_resize)
            if (!on_resize(m_framebuffer_width,
                           m_framebuffer_height))
                return false;

        m_resize_request_active = false;
        return true;
    }

    void update_state() {
        get_position(m_pos_x, m_pos_y);
        get_size(m_width, m_height);
    }

    using resize_func = std::function<bool(ui32, ui32)>;

    resize_func on_resize;

    void assign(input::ptr callback) {
        m_input = callback;
    }

    void show_save_title(bool value = true) {
        m_save_title_active = value;
    }

    bool save_title() const {
        return m_save_title_active;
    }

    void update_title() {
        set_title(m_title);
    }

    VkSurfaceKHR create_surface();

    void set_icon(data::c_ptr data, uv2 size);

    index detect_monitor() const;

    void center();

private:
    void handle_message();

    void handle_mouse_message();

    GLFWwindow* m_handle = nullptr;

    input::ptr m_input = nullptr;

    string m_title = _lava_;

    string m_save_name = _default_;

    bool m_fullscreen_active = false;

    bool m_save_title_active = false;

    bool m_switch_mode_request_active = false;

    bool m_resize_request_active = false;

    ui32 m_framebuffer_width = 0;

    ui32 m_framebuffer_height = 0;

    i32 m_pos_x = 0;

    i32 m_pos_y = 0;

    ui32 m_width = 0;

    ui32 m_height = 0;
};

VkSurfaceKHR create_surface(GLFWwindow* window);

window* get_window(GLFWwindow* handle);

} // namespace lava
```


-------------------------------

Updated on 2026-02-01 at 18:13:39 +0000
