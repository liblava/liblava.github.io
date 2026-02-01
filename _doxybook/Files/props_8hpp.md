---
title: liblava/engine/props.hpp
summary: Props. 

---

# liblava/engine/props.hpp

Props.  [More...](#detailed-description)

## Namespaces

| Name           |
| -------------- |
| **[lava](/_doxybook/Namespaces/namespacelava.md)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| struct | **[lava::props](/_doxybook/Classes/structlava_1_1props.md)** <br>Props.  |
| struct | **[lava::props::item](/_doxybook/Classes/structlava_1_1props_1_1item.md)** <br>Prop item.  |

## Detailed Description

Props. 

**Author**: Lava Block OÜ and contributors 

**Copyright**: Copyright (c) 2018-present, MIT License 



## Source code

```cpp


#pragma once

#include "liblava/file/file_utils.hpp"
#include "liblava/file/json.hpp"
#include "liblava/frame/argh.hpp"
#include "liblava/fwd.hpp"

namespace lava {

struct props : configurable {
    engine* app = nullptr;

    struct item {
        using map = std::map<string, item>;

        item(string_ref filename)
        : filename(filename) {}

        string filename;

        file_data data;
    };

    void add(string_ref name,
             string_ref filename);

    void remove(string_ref name);

    bool install(string_ref name,
                 string_ref filename);

    c_data operator()(string_ref name);

    string_ref get_filename(string_ref name) const {
        return m_map.at(name).filename;
    }

    void set_filename(string_ref name,
                      string_ref filename) {
        m_map.at(name).filename = filename;
    }

    bool exists(string_ref name) const {
        return m_map.count(name);
    }

    bool empty(string_ref name) const {
        return m_map.at(name).data.addr == nullptr;
    }

    bool load(string_ref name);

    void unload(string_ref name) {
        m_map.at(name).data = {};
    }

    bool load_all();

    void unload_all() {
        for (auto& [name, prop] : m_map)
            prop.data = {};
    }

    bool check();

    void parse(cmd_line cmd_line);

    void clear() {
        m_map.clear();
    }

    item::map const& get_all() const {
        return m_map;
    }

    void set_json(json_ref j) override;

    json get_json() const override;

private:
    item::map m_map;
};

} // namespace lava
```


-------------------------------

Updated on 2026-02-01 at 18:13:39 +0000
