---
title: liblava/util/layer.hpp
summary: Layering. 

---

# liblava/util/layer.hpp

Layering.  [More...](#detailed-description)

## Namespaces

| Name           |
| -------------- |
| **[lava](/_doxybook/Namespaces/namespacelava.md)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| struct | **[lava::layer](/_doxybook/Classes/structlava_1_1layer.md)** <br>Layer.  |
| struct | **[lava::layer_list](/_doxybook/Classes/structlava_1_1layer__list.md)** <br>Layer list.  |

## Detailed Description

Layering. 

**Author**: Lava Block OÜ and contributors 

**Copyright**: Copyright (c) 2018-present, MIT License 



## Source code

```cpp


#pragma once

#include "liblava/core/id.hpp"
#include "liblava/core/misc.hpp"

namespace lava {

struct layer : entity {
    using s_ptr = std::shared_ptr<layer>;

    using map = std::map<id, s_ptr>;

    using list = std::vector<s_ptr>;

    using func = std::function<void()>;

    static s_ptr make(string_ref name) {
        return std::make_shared<layer>(name);
    }

    layer(string_ref name)
    : name(name) {}

    func on_func;

    bool active = true;

    string name;
};

struct layer_list {
    using ptr = layer_list*;

    id add(string_ref name,
           layer::func func,
           bool active = true) {
        auto layer = layer::make(name);

        layer->on_func = func;
        layer->active = active;

        m_layers.push_back(layer);

        return layer->get_id();
    }

    void add(layer::s_ptr layer) {
        m_layers.push_back(layer);
    }

    id add_inactive(string_ref name,
                    layer::func func) {
        return add(name, func, false);
    }

    layer::s_ptr get(id::ref layer_id) {
        for (auto const& layer : m_layers)
            if (layer->get_id() == layer_id)
                return layer;

        return nullptr;
    }

    bool remove(id::ref layer_id) {
        for (auto const& layer : m_layers) {
            if (layer->get_id() == layer_id) {
                lava::remove(m_layers, layer);
                return true;
            }
        }

        return false;
    }

    layer::list const& get_all() const {
        return m_layers;
    }

    void clear() {
        m_layers.clear();
    }

private:
    layer::list m_layers;
};

} // namespace lava
```


-------------------------------

Updated on 2026-02-01 at 18:13:39 +0000
