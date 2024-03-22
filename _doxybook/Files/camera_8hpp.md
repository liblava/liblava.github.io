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

enum class camera_mode : index {
    first_person = 0,
    look_at,
};

struct camera : entity {
    using ptr = std::shared_ptr<camera>;

    using map = std::map<id, ptr>;

    using list = std::vector<ptr>;

    bool create(device_p device);

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
        return data ? data->valid() : false;
    }

    VkDescriptorBufferInfo const* get_descriptor_info() const {
        return data ? data->get_descriptor_info() : nullptr;
    }

    void upload();

    void stop();

    void reset();

    void set_active(bool value = true) {
        active = value;
    }

    bool activated() const {
        return active;
    }

    bool moving() const {
        return move_up || move_down || move_left || move_right;
    }

    void set_movement_keys(keys_ref up, keys_ref down,
                           keys_ref left, keys_ref right) {
        up_keys = up;
        down_keys = down;
        left_keys = left;
        right_keys = right;
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

    camera_mode mode = camera_mode::first_person;

    bool lock_z = false;

    bool lock_rotation = false;

private:
    void move_first_person(delta dt);

    bool active = true;

    bool move_up = false;

    bool move_down = false;

    bool move_left = false;

    bool move_right = false;

    bool rotate = false;

    bool translate = false;

    r64 mouse_pos_x = 0.0;

    r64 mouse_pos_y = 0.0;

    r64 scroll_pos = 0.0;

    keys up_keys{ key::w };

    keys down_keys{ key::s };

    keys left_keys{ key::a };

    keys right_keys{ key::d };

    buffer::ptr data;

    size_t size = sizeof(mat4) * 2;

    mat4 projection = mat4(0.f);

    mat4 view = mat4(0.f);
};

using camera_t = camera;

} // namespace lava
```


-------------------------------

Updated on 2024-03-22 at 21:51:38 +0000
