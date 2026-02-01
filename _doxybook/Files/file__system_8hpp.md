---
title: liblava/file/file_system.hpp
summary: File system. 

---

# liblava/file/file_system.hpp

File system.  [More...](#detailed-description)

## Namespaces

| Name           |
| -------------- |
| **[lava](/_doxybook/Namespaces/namespacelava.md)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| struct | **[lava::file_system](/_doxybook/Classes/structlava_1_1file__system.md)** <br>File system.  |

## Detailed Description

File system. 

**Author**: Lava Block OÜ and contributors 

**Copyright**: Copyright (c) 2018-present, MIT License 



## Source code

```cpp


#pragma once

#include "liblava/core/version.hpp"
#include <filesystem>

namespace lava {

struct file_system : no_copy_no_move {
    sem_version get_version();

    string get_base_dir();

    string get_full_base_dir(string_ref path);

    string get_pref_dir();

    string get_res_dir();

    bool mount(string_ref path);

    bool mount_base(string_ref base_dir_path);

    bool exists(string_ref file);

    string get_real_dir(string_ref file);

    string_list enumerate_files(string_ref path);

    bool initialize(string_ref argv_0,
                    string_ref org,
                    string_ref app,
                    string_ref ext);

    void terminate();

    string_list mount_res();

    bool create_folder(string_ref name = "data");

    void clean_pref_dir();

    string_ref get_org() const {
        return m_org;
    }

    string_ref get_app() const {
        return m_app;
    }

    string_ref get_ext() const {
        return m_ext;
    }

    bool ready() const {
        return m_initialized;
    }

private:
    bool m_initialized = false;

    string m_org;

    string m_app;

    string m_ext;

    string m_res_path;
};

} // namespace lava
```


-------------------------------

Updated on 2026-02-01 at 18:13:39 +0000
