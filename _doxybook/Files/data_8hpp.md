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
| struct | **[lava::data](/_doxybook/Classes/structlava_1_1data.md)** <br>Data wrapper.  |
| struct | **[lava::data_provider](/_doxybook/Classes/structlava_1_1data__provider.md)** <br>Data provider.  |
| struct | **[lava::c_data](/_doxybook/Classes/structlava_1_1c__data.md)** <br>Const data wrapper.  |
| struct | **[lava::u_data](/_doxybook/Classes/structlava_1_1u__data.md)** <br>Unique data wrapper.  |

## Detailed Description

Data wrapper. 

**Author**: Lava Block OÜ and contributors 

**Copyright**: Copyright (c) 2018-present, MIT License 



## Source code

```cpp


#pragma once

#include "liblava/core/types.hpp"
#include <string.h>

namespace lava {

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

template <typename T>
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

struct data {
    using ref = data const&;

    using ptr = char*;

    using c_ptr = char const*;

    static inline ptr as_ptr(auto* value) {
        return (ptr)value;
    }

    static inline c_ptr as_c_ptr(auto* value) {
        return (c_ptr)value;
    }

    enum class mode : index {
        alloc = 0,
        no_alloc
    };

    data() = default;

    data(auto* addr, size_t size)
    : addr(as_ptr(addr)), size(size) {}

    bool set(size_t length,
             mode mode = mode::alloc) {
        size = length;
        alignment = align<data::ptr>();

        if (mode == mode::alloc)
            return allocate();

        return true;
    }

    bool allocate() {
        addr = as_ptr(alloc_data(size, alignment));
        return addr != nullptr;
    }

    void deallocate() {
        if (!addr)
            return;

        free_data(addr);
        addr = nullptr;
    }

    ptr end() const {
        return addr + size;
    }

    ptr addr = nullptr;

    size_t size = 0;

    size_t alignment = 0;
};

struct data_provider {
    using alloc_func = std::function<data::ptr(size_t, size_t)>;

    alloc_func on_alloc;

    using free_func = std::function<void()>;

    free_func on_free;

    using realloc_func = std::function<data::ptr(data::ptr, size_t, size_t)>;

    realloc_func on_realloc;
};

struct c_data {
    using ref = c_data const&;

    c_data() = default;

    c_data(void const* addr,
           size_t length)
    : addr(data::as_ptr(addr)), size(length) {}

    c_data(data::ref data)
    : c_data(data.addr, data.size) {}

    data::c_ptr addr = nullptr;

    size_t size = 0;
};

struct u_data : data {
    using ref = u_data const&;

    u_data(size_t length = 0,
           data::mode mode = data::mode::alloc) {
        if (length)
            set(length, mode);
    }

    explicit u_data(data::ref data) {
        addr = data.addr;
        size = data.size;
        alignment = data.alignment;
    }

    ~u_data() {
        deallocate();
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

Updated on 2026-02-01 at 18:13:39 +0000
