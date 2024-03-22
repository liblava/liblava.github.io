---
title: liblava/core/data.hpp
summary: Data wrapper. 

---

# liblava/core/data.hpp

Data wrapper.  [More...](#detailed-description)

## Namespaces

| Name           |
| -------------- |
| **[lava](/_doxybook/Namespaces/namespacelava.md)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| struct | **[lava::data_provider](/_doxybook/Classes/structlava_1_1data__provider.md)** <br>Data provider.  |
| struct | **[lava::data](/_doxybook/Classes/structlava_1_1data.md)** <br>Data wrapper.  |
| struct | **[lava::cdata](/_doxybook/Classes/structlava_1_1cdata.md)** <br>Const data wrapper.  |
| struct | **[lava::unique_data](/_doxybook/Classes/structlava_1_1unique__data.md)** <br>Unique data wrapper.  |

## Detailed Description

Data wrapper. 

**Author**: Lava Block OÜ and contributors 

**Copyright**: Copyright (c) 2018-present, MIT License 



## Source code

```cpp

#pragma once

#include <string.h>
#include "liblava/core/types.hpp"

namespace lava {

using data_ptr = char*;

using data_cptr = char const*;

struct data_provider {
    using alloc_func = std::function<data_ptr(size_t, size_t)>;

    alloc_func on_alloc;

    using free_func = std::function<void()>;

    free_func on_free;

    using realloc_func = std::function<data_ptr(data_ptr, size_t, size_t)>;

    realloc_func on_realloc;
};

inline data_ptr as_ptr(auto* value) {
    return (data_ptr) value;
}

inline data_cptr as_cptr(auto* value) {
    return (data_cptr) value;
}

inline auto align_up(auto value,
                     auto align) {
    return (value + align - 1) / align * align;
}

inline size_t align(size_t size,
                    size_t min = 0) {
    if (min == 0)
        return align_up(size, sizeof(void*));

    return align_up((size + min - 1) & ~(min - 1), sizeof(void*));
}

template<typename T>
inline size_t align(size_t min = 0) {
    return align(sizeof(T), min);
}

inline void* alloc_data(size_t size,
                        size_t alignment = sizeof(c8)) {
#if _WIN32
    return _aligned_malloc(size, alignment);
#else
    if (size % alignment == 0) {
        return aligned_alloc(alignment, size);
    } else {
        return aligned_alloc(alignment, ((size / alignment) + 1) * alignment);
    }
#endif
}

inline void free_data(void* data) {
#if _WIN32
    _aligned_free(data);
#else
    free(data);
#endif
}

inline void* realloc_data(void* data,
                          size_t size,
                          size_t alignment = sizeof(c8)) {
#if _WIN32
    return _aligned_realloc(data, size, alignment);
#else
    return realloc(data, align(size, alignment));
#endif
}

enum class data_mode : index {
    alloc = 0,
    no_alloc
};

struct data {
    using ref = data const&;

    data() = default;

    data(auto* ptr, size_t size)
    : ptr(as_ptr(ptr)), size(size) {}

    bool set(size_t length,
             data_mode mode = data_mode::alloc) {
        size = length;
        alignment = align<data_ptr>();

        if (mode == data_mode::alloc)
            return allocate();

        return true;
    }

    bool allocate() {
        ptr = as_ptr(alloc_data(size, alignment));
        return ptr != nullptr;
    }

    void free() {
        if (!ptr)
            return;

        free_data(ptr);
        ptr = nullptr;
    }

    data_ptr end() const {
        return ptr + size;
    }

    data_ptr ptr = nullptr;

    size_t size = 0;

    size_t alignment = 0;
};

struct cdata {
    using ref = cdata const&;

    cdata() = default;

    cdata(void const* ptr,
          size_t length)
    : ptr(as_ptr(ptr)), size(length) {}

    cdata(data::ref data)
    : cdata(data.ptr, data.size) {}

    data_cptr ptr = nullptr;

    size_t size = 0;
};

struct unique_data : data {
    using ref = unique_data const&;

    unique_data(size_t length = 0,
                data_mode mode = data_mode::alloc) {
        if (length)
            set(length, mode);
    }

    explicit unique_data(data::ref data) {
        ptr = data.ptr;
        size = data.size;
        alignment = data.alignment;
    }

    ~unique_data() {
        free();
    }
};

inline size_t next_pow_2(size_t x) {
    x--;
    x |= x >> 1;
    x |= x >> 2;
    x |= x >> 4;
    x |= x >> 8;
    x |= x >> 16;
    x++;
    return x;
}

} // namespace lava
```


-------------------------------

Updated on 2024-03-22 at 21:51:38 +0000
