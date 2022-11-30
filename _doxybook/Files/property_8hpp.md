---
title: liblava/engine/property.hpp
summary: Props master. 

---

# liblava/engine/property.hpp

Props master.  [More...](#detailed-description)

## Namespaces

| Name           |
| -------------- |
| **[lava](/_doxybook/Namespaces/namespacelava.md)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| struct | **[lava::property](/_doxybook/Classes/structlava_1_1property.md)** <br>Props master.  |
| struct | **[lava::property::prop](/_doxybook/Classes/structlava_1_1property_1_1prop.md)** <br>Prop.  |

## Detailed Description

Props master. 

**Author**: Lava Block OÜ and contributors 

**Copyright**: Copyright (c) 2018-present, MIT License 



## Source code

```cpp

#pragma once

#include <liblava/file/file_utils.hpp>
#include <liblava/file/json.hpp>
#include <liblava/frame/argh.hpp>
#include <liblava/fwd.hpp>

namespace lava {

struct property : configurable {
    engine* context = nullptr;

    struct prop {
        using map = std::map<string, prop>;

        prop(string_ref filename)
        : filename(filename) {}

        string filename;

        file_data data;
    };

    void add(string_ref name,
             string_ref filename);

    cdata operator()(string_ref name);

    string_ref get_filename(string_ref name) const {
        return map.at(name).filename;
    }

    void set_filename(string_ref name,
                      string_ref filename) {
        map.at(name).filename = filename;
    }

    bool exists(string_ref name) const {
        return map.count(name);
    }

    bool empty(string_ref name) const {
        return map.at(name).data.ptr == nullptr;
    }

    bool load(string_ref name);

    void unload(string_ref name) {
        map.at(name).data = {};
    }

    bool load_all();

    void unload_all() {
        for (auto& [name, prop] : map)
            prop.data = {};
    }

    bool check();

    void parse(cmd_line cmd_line);

    void clear() {
        map.clear();
    }

    prop::map const& get_all() const {
        return map;
    }

    void set_config(json_ref j) override;

    json get_config() const override;

private:
    prop::map map;
};

} // namespace lava
```


-------------------------------

Updated on 2022-11-30 at 01:16:04 +0000
