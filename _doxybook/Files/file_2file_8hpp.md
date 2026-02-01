---
title: liblava/file/file.hpp
summary: File access. 

---

# liblava/file/file.hpp

File access.  [More...](#detailed-description)

## Namespaces

| Name           |
| -------------- |
| **[lava](/_doxybook/Namespaces/namespacelava.md)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| struct | **[lava::file](/_doxybook/Classes/structlava_1_1file.md)** <br>File.  |

## Detailed Description

File access. 

**Author**: Lava Block OÜ and contributors 

**Copyright**: Copyright (c) 2018-present, MIT License 



## Source code

```cpp


#pragma once

#include "liblava/core/data.hpp"
#include <fstream>

// fwd
struct PHYSFS_File;

namespace lava {

enum class file_type : index {
    none = 0,
    fs,
    f_stream
};

constexpr i64 const file_error_result = undef;

inline bool file_error(i64 result) {
    return result == file_error_result;
}

enum class file_mode : index {
    read = 0,
    write
};

struct file : no_copy_no_move {
    using ref = file const&;

    explicit file(string_ref path = "",
                  file_mode mode = file_mode::read);

    ~file();

    bool open(string_ref path,
              file_mode mode = file_mode::read);

    void close();

    bool opened() const;

    i64 get_size() const;

    i64 read(data::ptr data) {
        return read(data,
                    to_ui64(get_size()));
    }

    i64 read(data::ptr data, ui64 size);

    i64 write(data::c_ptr data, ui64 size);

    i64 seek(ui64 position);

    i64 tell() const;

    bool writable() const {
        return m_mode == file_mode::write;
    }

    file_type get_type() const {
        return m_type;
    }

    string_ref get_path() const {
        return m_path;
    }

private:
    file_type m_type = file_type::none;

    file_mode m_mode = file_mode::read;

    string m_path;

    PHYSFS_File* m_file = nullptr;

    mutable std::ifstream m_istream;

    mutable std::ofstream m_ostream;
};

} // namespace lava
```


-------------------------------

Updated on 2026-02-01 at 18:13:39 +0000
