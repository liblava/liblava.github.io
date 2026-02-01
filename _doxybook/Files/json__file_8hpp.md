---
title: liblava/file/json_file.hpp
summary: Json file. 

---

# liblava/file/json_file.hpp

Json file.  [More...](#detailed-description)

## Namespaces

| Name           |
| -------------- |
| **[lava](/_doxybook/Namespaces/namespacelava.md)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| struct | **[lava::json_file](/_doxybook/Classes/structlava_1_1json__file.md)** <br>Json file.  |
| struct | **[lava::json_file::callback](/_doxybook/Classes/structlava_1_1json__file_1_1callback.md)** <br>Json file callback.  |

## Detailed Description

Json file. 

**Author**: Lava Block OÜ and contributors 

**Copyright**: Copyright (c) 2018-present, MIT License 



## Source code

```cpp


#pragma once

#include "liblava/file/json.hpp"

namespace lava {

struct json_file {
    explicit json_file(string_ref path = "config.json");

    struct callback {
        using list = std::vector<callback*>;

        using load_func = std::function<void(json_ref)>;

        load_func on_load;

        using save_func = std::function<json()>;

        save_func on_save;
    };

    void add(callback* callback);

    void remove(callback* callback);

    void clear() {
        m_callbacks.clear();
    }

    void set(string_ref value) {
        m_path = value;
    }

    string_ref get() const {
        return m_path;
    }

    bool load();

    bool save();

private:
    string m_path;

    callback::list m_callbacks;
};

} // namespace lava
```


-------------------------------

Updated on 2026-02-01 at 18:13:39 +0000
