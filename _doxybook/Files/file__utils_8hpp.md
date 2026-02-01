---
title: liblava/file/file_utils.hpp
summary: File utilities. 

---

# liblava/file/file_utils.hpp

File utilities.  [More...](#detailed-description)

## Namespaces

| Name           |
| -------------- |
| **[lava](/_doxybook/Namespaces/namespacelava.md)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| struct | **[lava::file_data](/_doxybook/Classes/structlava_1_1file__data.md)** <br>File data.  |
| struct | **[lava::file_delete](/_doxybook/Classes/structlava_1_1file__delete.md)** <br>File delete guard.  |

## Detailed Description

File utilities. 

**Author**: Lava Block OÜ and contributors 

**Copyright**: Copyright (c) 2018-present, MIT License 



## Source code

```cpp


#pragma once

#include "liblava/core/data.hpp"

namespace lava {

bool read_file(std::vector<char>& out, string_ref filename);

bool write_file(string_ref filename,
                char const* data,
                size_t data_size);

bool extension(string_ref filename, string_ref extension);

bool extension(string_ref filename,
               string_list_ref extensions);

string get_filename_from(string_ref path,
                         bool with_extension = false);

bool remove_existing_path(string& target,
                          string_ref path);

bool load_file_data(string_ref filename,
                    data& target);

struct file_data : u_data {
    using ref = file_data const&;

    using u_data::u_data;

    explicit file_data(string_ref filename)
    : filename(filename) {
        load_file_data(filename, *this);
    }

    string filename;
};

struct file_delete : no_copy_no_move {
    explicit file_delete(string filename = "")
    : filename(filename) {}

    ~file_delete();

    string filename;

    bool active = true;
};

} // namespace lava
```


-------------------------------

Updated on 2026-02-01 at 18:13:39 +0000
