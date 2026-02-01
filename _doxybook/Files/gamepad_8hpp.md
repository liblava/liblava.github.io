---
title: liblava/frame/gamepad.hpp
summary: Gamepad manager. 

---

# liblava/frame/gamepad.hpp

Gamepad manager.  [More...](#detailed-description)

## Namespaces

| Name           |
| -------------- |
| **[lava](/_doxybook/Namespaces/namespacelava.md)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| struct | **[lava::gamepad](/_doxybook/Classes/structlava_1_1gamepad.md)** <br>Gamepad.  |
| struct | **[lava::gamepad_manager](/_doxybook/Classes/structlava_1_1gamepad__manager.md)** <br>Gamepad manager.  |

## Detailed Description

Gamepad manager. 

**Author**: Lava Block OÜ and contributors 

**Copyright**: Copyright (c) 2018-present, MIT License 



## Source code

```cpp


#pragma once

#include "liblava/core/id.hpp"

namespace lava {

enum class gamepad_id : index {
    _1 = 0,
    _2,
    _3,
    _4,
    _5,
    _6,
    _7,
    _8,
    _9,
    _10,
    _11,
    _12,
    _13,
    _14,
    _15,
    _16,

    last = _16,
};

using gamepad_id_ref = gamepad_id const&;

enum class gamepad_button : index {
    a = 0,
    b,
    x,
    y,

    left_bumper,
    right_bumper,

    back,
    start,
    guide,

    left_thumb,
    right_thumb,

    dpad_up,
    dpad_right,
    dpad_down,
    dpad_left,

    last = dpad_left,

    cross = a,
    circle = b,
    square = x,
    triangle = y,
};

using gamepad_button_ref = gamepad_button const&;

enum class gamepad_axis : index {
    left_x = 0,
    left_y,

    right_x,
    right_y,

    left_trigger,
    right_trigger,

    last = right_trigger,
};

using gamepad_axis_ref = gamepad_axis const&;

struct gamepad {
    using list = std::vector<gamepad>;

    using ref = gamepad const&;

    explicit gamepad(gamepad_id_ref pad_id = gamepad_id::_1);

    bool ready() const;

    bool update();

    bool pressed(gamepad_button_ref button) const {
        return m_state.buttons[to_ui32(button)];
    }

    r32 value(gamepad_axis_ref axis) const {
        return m_state.axes[to_ui32(axis)];
    }

    gamepad_id_ref get_pad_id() const {
        return m_pad_id;
    }

    ui32 get_id() const {
        return to_ui32(get_pad_id());
    }

    name get_name() const;

private:
    gamepad_id m_pad_id;

    struct state {
        uchar buttons[15];

        r32 axes[6];
    };

    gamepad::state m_state;
};

gamepad::list gamepads();

struct gamepad_manager {
    using listener_func = std::function<bool(gamepad, bool)>;

    static gamepad_manager& singleton() {
        static gamepad_manager manager;
        return manager;
    }

    id add(listener_func listener);

    void remove(id::ref func_id);

private:
    explicit gamepad_manager();

    using listener_map = std::map<id, listener_func>;

    listener_map m_map;
};

} // namespace lava
```


-------------------------------

Updated on 2026-02-01 at 18:13:39 +0000
