---
title: liblava/base/platform.hpp
summary: Stage platform. 

---

# liblava/base/platform.hpp

Stage platform.  [More...](#detailed-description)

## Namespaces

| Name           |
| -------------- |
| **[lava](/_doxybook/Namespaces/namespacelava.md)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| struct | **[lava::platform](/_doxybook/Classes/structlava_1_1platform.md)** <br>Stage platform.  |

## Detailed Description

Stage platform. 

**Author**: Lava Block OÜ and contributors 

**Copyright**: Copyright (c) 2018-present, MIT License 



## Source code

```cpp


#pragma once

#include "liblava/base/device.hpp"

namespace lava {

struct platform {
    using ptr = platform*;

    device::s_ptr create(index physical_device = 0);

    device::s_ptr create(device::create_param::ref param);

    device::ptr create_device(index physical_device = 0);

    device::s_list const& get_devices() const {
        return m_devices;
    }

    void wait_idle();

    bool remove(id::ref device_id);

    void clear();

    using create_param_func = std::function<void(device::create_param&)>;

    create_param_func on_create_param;

private:
    device::s_list m_devices;
};

} // namespace lava
```


-------------------------------

Updated on 2026-02-01 at 18:13:39 +0000
