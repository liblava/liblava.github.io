---
title: liblava/core/types.hpp
summary: Basic types. 

---

# liblava/core/types.hpp

Basic types.  [More...](#detailed-description)

## Namespaces

| Name           |
| -------------- |
| **[lava](/_doxybook/Namespaces/namespacelava.md)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| struct | **[lava::no_copy_no_move](/_doxybook/Classes/structlava_1_1no__copy__no__move.md)** <br>No copy and no move object.  |
| struct | **[lava::interface](/_doxybook/Classes/structlava_1_1interface.md)** <br>Interface.  |
| struct | **[lava::pair_hash](/_doxybook/Classes/structlava_1_1pair__hash.md)** <br>Pair hash.  |

## Defines

|                | Name           |
| -------------- | -------------- |
|  | **[ENUM_FLAG_OPERATORS](/_doxybook/Files/types_8hpp.md#define-enum-flag-operators)**(T) <br>Enum flag operators.  |

## Detailed Description

Basic types. 

**Author**: Lava Block OÜ and contributors 

**Copyright**: Copyright (c) 2018-present, MIT License 



## Macros Documentation

### define ENUM_FLAG_OPERATORS

```cpp
#define ENUM_FLAG_OPERATORS(
    T
)
    inline T operator~(T a) { \
        return static_cast<T>(~static_cast<std::underlying_type<T>::type>(a)); \
    } \
    inline T operator|(T a, T b) { \
        return static_cast<T>(static_cast<std::underlying_type<T>::type>(a) | static_cast<std::underlying_type<T>::type>(b)); \
    } \
    inline T operator&(T a, T b) { \
        return static_cast<T>(static_cast<std::underlying_type<T>::type>(a) & static_cast<std::underlying_type<T>::type>(b)); \
    } \
    inline T operator^(T a, T b) { \
        return static_cast<T>(static_cast<std::underlying_type<T>::type>(a) ^ static_cast<std::underlying_type<T>::type>(b)); \
    } \
    inline T& operator|=(T& a, T b) { \
        return reinterpret_cast<T&>(reinterpret_cast<std::underlying_type<T>::type&>(a) |= static_cast<std::underlying_type<T>::type>(b)); \
    } \
    inline T& operator&=(T& a, T b) { \
        return reinterpret_cast<T&>(reinterpret_cast<std::underlying_type<T>::type&>(a) &= static_cast<std::underlying_type<T>::type>(b)); \
    } \
    inline T& operator^=(T& a, T b) { \
        return reinterpret_cast<T&>(reinterpret_cast<std::underlying_type<T>::type&>(a) ^= static_cast<std::underlying_type<T>::type>(b)); \
    }
```

Enum flag operators. 

## Source code

```cpp


#pragma once

#include "liblava/core/def.hpp"
#include <cstdint>
#include <functional>
#include <map>
#include <string>
#include <string_view>
#include <vector>

namespace lava {

using int8 = std::int8_t;

using i8 = int8;

using uint8 = std::uint8_t;

using ui8 = uint8;

using int16 = std::int16_t;

using i16 = int16;

using uint16 = std::uint16_t;

using ui16 = uint16;

using int32 = std::int32_t;

using i32 = int32;

using uint32 = std::uint32_t;

using ui32 = uint32;

using int64 = std::int64_t;

using i64 = int64;

using uint64 = std::uint64_t;

using ui64 = uint64;

using char8 = std::int_fast8_t;

using c8 = char8;

using uchar8 = std::uint_fast8_t;

using uc8 = uchar8;

using char16 = int16;

using c16 = char16;

using uchar16 = uint16;

using uc16 = uchar16;

using char32 = int32;

using c32 = char32;

using uchar32 = uint32;

using uc32 = uchar32;

using size_t = std::size_t;

using uchar = unsigned char;

using r32 = float;

using r64 = double;

using real = r64;

using delta = r32;

using void_ptr = void*;

using void_c_ptr = void const*;

constexpr i32 const undef = -1;

using flag = ui32;

using index = ui32;

constexpr index const no_index = 0xffffffff;

using index_list = std::vector<index>;

using index_map = std::map<index, index>;

using string = std::string;

using string_ref = string const&;

using string_list = std::vector<string>;

using string_list_ref = string_list const&;

using string_view = std::string_view;

using string_map = std::map<string, string>;

using string_map_ref = string_map const&;

using name = char const*;

using name_ref = char const&;

using names = std::vector<name>;

using names_ref = names const&;

constexpr name _lava_ = "lava";

constexpr name _liblava_ = "liblava";

constexpr name _default_ = "default";

inline name str(string_ref value) {
    return value.c_str();
}

inline r32 to_r32(auto value) {
    return static_cast<r32>(value);
}

inline r64 to_r64(auto value) {
    return static_cast<r64>(value);
}

inline i32 to_i32(auto value) {
    return static_cast<i32>(value);
}

inline i64 to_i64(auto value) {
    return static_cast<i64>(value);
}

inline ui32 to_ui32(auto value) {
    return static_cast<ui32>(value);
}

inline ui64 to_ui64(auto value) {
    return static_cast<ui64>(value);
}

inline size_t to_size_t(auto value) {
    return static_cast<size_t>(value);
}

inline index to_index(auto value) {
    return static_cast<index>(value);
}

inline char const* to_char(auto value) {
    return (char const*)value;
}

struct no_copy_no_move {
    no_copy_no_move() = default;

    no_copy_no_move(no_copy_no_move const&) = delete;

    void operator=(no_copy_no_move const&) = delete;
};

struct interface {
    virtual ~interface() = default;
};

template <typename T>
inline void hash_combine(size_t& seed,
                         T const& val) {
    seed ^= std::hash<T>()(val) + 0x9e3779b9
            + (seed << 6) + (seed >> 2);
}

template <typename T>
inline void hash_value(size_t& seed,
                       T const& val) {
    hash_combine(seed, val);
}

template <typename T, typename... Types>
inline void hash_value(size_t& seed,
                       T const& val,
                       Types const&... args) {
    hash_combine(seed, val);
    hash_value(seed, args...);
}

template <typename... Types>
inline size_t hash_value(Types const&... args) {
    size_t seed = 0;
    hash_value(seed, args...);
    return seed;
}

struct pair_hash {
    template <class T1, class T2>
    size_t operator()(std::pair<T1, T2> const& p) const {
        return hash_value(p.first, p.second);
    }
};

#define ENUM_FLAG_OPERATORS(T) \
    inline T operator~(T a) { \
        return static_cast<T>(~static_cast<std::underlying_type<T>::type>(a)); \
    } \
    inline T operator|(T a, T b) { \
        return static_cast<T>(static_cast<std::underlying_type<T>::type>(a) | static_cast<std::underlying_type<T>::type>(b)); \
    } \
    inline T operator&(T a, T b) { \
        return static_cast<T>(static_cast<std::underlying_type<T>::type>(a) & static_cast<std::underlying_type<T>::type>(b)); \
    } \
    inline T operator^(T a, T b) { \
        return static_cast<T>(static_cast<std::underlying_type<T>::type>(a) ^ static_cast<std::underlying_type<T>::type>(b)); \
    } \
    inline T& operator|=(T& a, T b) { \
        return reinterpret_cast<T&>(reinterpret_cast<std::underlying_type<T>::type&>(a) |= static_cast<std::underlying_type<T>::type>(b)); \
    } \
    inline T& operator&=(T& a, T b) { \
        return reinterpret_cast<T&>(reinterpret_cast<std::underlying_type<T>::type&>(a) &= static_cast<std::underlying_type<T>::type>(b)); \
    } \
    inline T& operator^=(T& a, T b) { \
        return reinterpret_cast<T&>(reinterpret_cast<std::underlying_type<T>::type&>(a) ^= static_cast<std::underlying_type<T>::type>(b)); \
    }

} // namespace lava
```


-------------------------------

Updated on 2026-02-01 at 18:13:39 +0000
