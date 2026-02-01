---
title: liblava/frame/input.hpp
summary: Input handling. 

---

# liblava/frame/input.hpp

Input handling.  [More...](#detailed-description)

## Namespaces

| Name           |
| -------------- |
| **[lava](/_doxybook/Namespaces/namespacelava.md)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| struct | **[lava::key_event](/_doxybook/Classes/structlava_1_1key__event.md)** <br>Key event.  |
| struct | **[lava::scroll_offset](/_doxybook/Classes/structlava_1_1scroll__offset.md)** <br>Input scroll offset.  |
| struct | **[lava::scroll_event](/_doxybook/Classes/structlava_1_1scroll__event.md)** <br>Scroll event.  |
| struct | **[lava::mouse_position](/_doxybook/Classes/structlava_1_1mouse__position.md)** <br>Input mouse position.  |
| struct | **[lava::mouse_move_event](/_doxybook/Classes/structlava_1_1mouse__move__event.md)** <br>Mouse move event.  |
| struct | **[lava::mouse_button_event](/_doxybook/Classes/structlava_1_1mouse__button__event.md)** <br>Mouse button event.  |
| struct | **[lava::path_drop_event](/_doxybook/Classes/structlava_1_1path__drop__event.md)** <br>Path drop event.  |
| struct | **[lava::mouse_active_event](/_doxybook/Classes/structlava_1_1mouse__active__event.md)** <br>Mouse active event.  |
| struct | **[lava::input_callback](/_doxybook/Classes/structlava_1_1input__callback.md)** <br>Input callback.  |
| struct | **[lava::input_events](/_doxybook/Classes/structlava_1_1input__events.md)** <br>List of input events.  |
| struct | **[lava::input](/_doxybook/Classes/structlava_1_1input.md)** <br>Input handling.  |
| struct | **[lava::tooltip](/_doxybook/Classes/structlava_1_1tooltip.md)** <br>Tooltip.  |
| struct | **[lava::tooltip_list](/_doxybook/Classes/structlava_1_1tooltip__list.md)** <br>Tooltip list.  |

## Detailed Description

Input handling. 

**Author**: Lava Block OÜ and contributors 

**Copyright**: Copyright (c) 2018-present, MIT License 



## Source code

```cpp


#pragma once

#include "liblava/core/id.hpp"
#include "liblava/core/misc.hpp"

namespace lava {

enum class key : i32 {
    unknown = undef,

    /* printable keys */

    space = 32,
    apostrophe = 29, /* ' */
    comma = 44,      /* , */
    minus = 45,      /* - */
    period = 46,     /* . */
    slash = 47,      /* / */

    _0 = 48,
    _1,
    _2,
    _3,
    _4,
    _5,
    _6,
    _7,
    _8,
    _9,

    semicolon = 59, /* ; */
    equal = 61,     /* = */

    a = 65,
    b,
    c,
    d,
    e,
    f,
    g,
    h,
    i,
    j,
    k,
    l,
    m,
    n,
    o,
    p,
    q,
    r,
    s,
    t,
    u,
    v,
    w,
    x,
    y,
    z,

    left_bracket = 91,  /* [ */
    backslash = 92,     /* \ */
    right_bracket = 93, /* ] */
    grave_accent = 96,  /* ` */

    world_1 = 161, /* non-US #1 */
    world_2 = 162, /* non-US #2 */

    /* function keys */

    escape = 256,
    enter,
    tab,
    backspace,
    insert,
    del, /* delete */

    right,
    left,
    down,
    up,

    page_up,
    page_down,
    home,
    end,

    caps_lock = 280,
    scroll_lock,
    num_lock,
    print_screen,
    pause,

    f1 = 290,
    f2,
    f3,
    f4,
    f5,
    f6,
    f7,
    f8,
    f9,
    f10,
    f11,
    f12,
    f13,
    f14,
    f15,
    f16,
    f17,
    f18,
    f19,
    f20,
    f21,
    f22,
    f23,
    f24,
    f25,

    kp_0 = 320,
    kp_1,
    kp_2,
    kp_3,
    kp_4,
    kp_5,
    kp_6,
    kp_7,
    kp_8,
    kp_9,

    kp_decimal,
    kp_divide,
    kp_multiply,
    kp_subtract,
    kp_add,
    kp_enter,
    kp_equal,

    left_shift = 340,
    left_control,
    left_alt,
    left_super,

    right_shift,
    right_control,
    right_alt,
    right_super,

    menu,

    last = menu,
};

using key_ref = key const&;

using keys = std::vector<key>;

using keys_ref = keys const&;

string to_string(key k);

i32 get_scancode(key key);

enum class action : index {
    release = 0,
    press,
    repeat
};

using action_ref = action const&;

enum class mod : flag {
    none = 0 << 0,
    shift = 1 << 0,
    control = 1 << 1,
    alt = 1 << 2,
    super = 1 << 3,
    caps_lock = 1 << 4,
    num_lock = 1 << 5,
};

ENUM_FLAG_OPERATORS(mod)


inline bool check_mod(mod m, mod c) {
    return (m & c) != mod::none;
}

using mod_ref = mod const&;

string to_string(mod m);

struct key_event {
    using ref = key_event const&;

    using func = std::function<bool(ref)>;

    using listeners = std::map<id, func>;

    using list = std::vector<key_event>;

    id sender;

    lava::key key;

    lava::action action;

    lava::mod mod;

    i32 scancode = 0;

    bool pressed(key_ref k) const {
        return (action == action::press) && (key == k);
    }

    bool released(key_ref k) const {
        return (action == action::release) && (key == k);
    }

    bool repeated(key_ref k) const {
        return (action == action::repeat) && (key == k);
    }

    bool active() const {
        return (action == action::press) || (action == action::repeat);
    }

    bool pressed(key_ref k, mod_ref m) const {
        return pressed(k) && (mod == m);
    }
};

struct scroll_offset {
    r64 x = 0.0;

    r64 y = 0.0;
};

struct scroll_event {
    using ref = scroll_event const&;

    using func = std::function<bool(ref)>;

    using listeners = std::map<id, func>;

    using list = std::vector<scroll_event>;

    id sender;

    scroll_offset offset;
};

struct mouse_position {
    r64 x = 0.0;

    r64 y = 0.0;
};

using mouse_position_ref = mouse_position const&;

struct mouse_move_event {
    using ref = mouse_move_event const&;

    using func = std::function<bool(ref)>;

    using listeners = std::map<id, func>;

    using list = std::vector<mouse_move_event>;

    id sender;

    mouse_position position;
};

enum class mouse_button : index {
    _1 = 0,
    _2,
    _3,
    _4,
    _5,
    _6,
    _7,
    _8,

    last = _8,

    left = _1,
    right = _2,
    middle = _3,
};

using mouse_button_ref = mouse_button const&;

struct mouse_button_event {
    using ref = mouse_button_event const&;

    using func = std::function<bool(ref)>;

    using listeners = std::map<id, func>;

    using list = std::vector<mouse_button_event>;

    id sender;

    mouse_button button;

    lava::action action;

    lava::mod mod;

    bool pressed(mouse_button_ref b) const {
        return action == action::press && button == b;
    }

    bool released(mouse_button_ref b) const {
        return action == action::release && button == b;
    }
};

struct path_drop_event {
    using ref = path_drop_event const&;

    using func = std::function<bool(ref)>;

    using listeners = std::map<id, func>;

    using list = std::vector<path_drop_event>;

    id sender;

    string_list files;
};

struct mouse_active_event {
    using ref = mouse_active_event const&;

    using func = std::function<bool(ref)>;

    using listeners = std::map<id, func>;

    using list = std::vector<mouse_active_event>;

    id sender;

    bool active = false;
};

struct input_callback {
    using cptr = input_callback const*;

    using list = std::vector<input_callback*>;

    using clist = std::vector<cptr>;

    template <typename T>
    using func = std::function<bool(typename T::ref)>;

    key_event::func on_key_event;

    scroll_event::func on_scroll_event;

    mouse_move_event::func on_mouse_move_event;

    mouse_button_event::func on_mouse_button_event;

    mouse_active_event::func on_mouse_active_event;

    path_drop_event::func on_path_drop_event;
};

template <typename T>
struct input_events : T::list {
    void add(typename T::ref event) {
        this->push_back(event);
    }

    id_listeners<T> listeners;
};

using input_key_events = input_events<key_event>;

using input_scroll_events = input_events<scroll_event>;

using input_mouse_move_events = input_events<mouse_move_event>;

using input_mouse_button_events = input_events<mouse_button_event>;

using input_mouse_active_events = input_events<mouse_active_event>;

using input_path_drop_events = input_events<path_drop_event>;

constexpr bool const input_ignore = false;

constexpr bool const input_done = true;

struct input {
    using ptr = input*;

    input_key_events key;

    input_scroll_events scroll;

    input_mouse_move_events mouse_move;

    input_mouse_button_events mouse_button;

    input_mouse_active_events mouse_active;

    input_path_drop_events path_drop;

    void handle_events();

    void add(input_callback::cptr callback) {
        m_callbacks.push_back(callback);
    }

    void remove(input_callback::cptr callback) {
        lava::remove(m_callbacks, callback);
    }

    mouse_position_ref get_mouse_position() const {
        return m_current_position;
    }

    void set_mouse_position(mouse_position_ref position) {
        m_current_position = position;
    }

private:
    void handle_mouse_events();

    mouse_position m_current_position;

    input_callback::clist m_callbacks;
};

struct tooltip {
    tooltip(string_ref name,
            key key,
            mod mod)
    : name(name), key(key), mod(mod) {
    }

    using list = std::vector<tooltip>;

    string name;

    lava::key key;

    lava::mod mod;
};

struct tooltip_list {
    void add(string_ref name,
             key key,
             mod mod = mod::none) {
        m_tooltips.emplace_back(name, key, mod);
    }

    void clear() {
        m_tooltips.clear();
    }

    tooltip::list const& get_list() const {
        return m_tooltips;
    }

    void set(tooltip::list const& list) {
        m_tooltips = list;
    }

    string format_string() const;

private:
    tooltip::list m_tooltips;
};

} // namespace lava
```


-------------------------------

Updated on 2026-02-01 at 18:13:39 +0000
