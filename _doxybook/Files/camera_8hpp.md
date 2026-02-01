---
title: liblava/app/camera.hpp
summary: First Person / Look At camera. 

---

# liblava/app/camera.hpp

First Person / Look At camera.  [More...](#detailed-description)

## Namespaces

| Name           |
| -------------- |
| **[lava](/_doxybook/Namespaces/namespacelava.md)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| struct | **[lava::camera](/_doxybook/Classes/structlava_1_1camera.md)** <br>First Person / Look At camera.  |

## Detailed Description

First Person / Look At camera. 

**Author**: Lava Block OÜ and contributors 

**Copyright**: Copyright (c) 2018-present, MIT License 



## Source code

```cpp


#pragma once

#include "liblava/frame/gamepad.hpp"
#include "liblava/frame/input.hpp"
#include "liblava/resource/buffer.hpp"

namespace lava {

struct camera : entity {
    using ptr = camera*;

    using s_ptr = std::shared_ptr<camera>;

    using s_map = std::map<id, s_ptr>;

    using s_list = std::vector<s_ptr>;

    enum class mode : index {
        first_person = 0,
        look_at,
    };

    bool create(device::ptr device);

    void destroy();

    void update_projection();

    void update_view(delta dt, mouse_position mouse_pos);

    void update_view(delta dt, gamepad::ref pad);

    mat4 get_view() const;

    mat4 get_projection() const;

    mat4 calc_view_projection() const;

    bool handle(key_event::ref event);

    bool handle(mouse_button_event::ref event,
                mouse_position mouse_pos);

    bool handle(scroll_event::ref event);

    bool valid() const {
        return m_data ? m_data->valid() : false;
    }

    VkDescriptorBufferInfo const* get_descriptor_info() const {
        return m_data ? m_data->get_descriptor_info() : nullptr;
    }

    void upload();

    void stop();

    void reset();

    void set_active(bool value = true) {
        m_active = value;
    }

    bool activated() const {
        return m_active;
    }

    bool moving() const {
        return m_move_up || m_move_down || m_move_left || m_move_right;
    }

    void set_movement_keys(keys_ref up, keys_ref down,
                           keys_ref left, keys_ref right) {
        m_up_keys = up;
        m_down_keys = down;
        m_left_keys = left;
        m_right_keys = right;
    }

    v3 position = v3(0.f);

    v3 rotation = v3(0.f);

    r32 rotation_speed = 20.f;

    r32 movement_speed = 1.f;

    r32 zoom_speed = 20.f;

    r32 fov = 60.f;

    r32 z_near = 0.1f;

    r32 z_far = 256.f;

    r32 aspect_ratio = 1.77f;

    mode mode = mode::first_person;

    bool lock_z = false;

    bool lock_rotation = false;

private:
    void move_first_person(delta dt);

    bool m_active = true;

    bool m_move_up = false;

    bool m_move_down = false;

    bool m_move_left = false;

    bool m_move_right = false;

    bool m_rotate = false;

    bool m_translate = false;

    r64 m_mouse_pos_x = 0.0;

    r64 m_mouse_pos_y = 0.0;

    r64 m_scroll_pos = 0.0;

    keys m_up_keys{key::w};

    keys m_down_keys{key::s};

    keys m_left_keys{key::a};

    keys m_right_keys{key::d};

    buffer::s_ptr m_data;

    size_t m_size = sizeof(mat4) * 2;

    mat4 m_projection = mat4(0.f);

    mat4 m_view = mat4(0.f);
};

} // namespace lava
```


-------------------------------

Updated on 2026-02-01 at 18:13:39 +0000
