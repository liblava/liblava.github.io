---
title: liblava/core/misc.hpp
summary: Miscellaneous helpers. 

---

# liblava/core/misc.hpp

Miscellaneous helpers.  [More...](#detailed-description)

## Namespaces

| Name           |
| -------------- |
| **[lava](/_doxybook/Namespaces/namespacelava.md)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| struct | **[lava::reversion_wrapper](/_doxybook/Classes/structlava_1_1reversion__wrapper.md)** <br>Reversion Wrapper.  |

## Detailed Description

Miscellaneous helpers. 

**Author**: Lava Block OÜ and contributors 

**Copyright**: Copyright (c) 2018-present, MIT License 



## Source code

```cpp


#pragma once

#include "liblava/core/types.hpp"
#include <algorithm>
#include <cstring>
#include <utility>

namespace lava {

inline bool exists(names_ref list, name item) {
    auto itr = std::find_if(list.begin(), list.end(),
                            [&](name entry) { return strcmp(entry, item) == 0; });
    return itr != list.end();
}

template <typename T>
inline void remove(std::vector<T>& list, T item) {
    list.erase(std::remove(list.begin(), list.end(), item), list.end());
}

template <typename T>
inline bool contains(std::vector<T>& list, T item) {
    return std::find(list.begin(), list.end(), item) != list.end();
}

template <typename T>
inline void append(std::vector<T>& list, std::vector<T>& items) {
    list.insert(list.end(), items.begin(), items.end());
}

inline void trim_start(string& s) {
    s.erase(s.begin(), std::find_if(s.begin(), s.end(), [](uchar ch) {
                return !std::isspace(ch);
            }));
}

inline void trim_end(string& s) {
    s.erase(std::find_if(s.rbegin(), s.rend(), [](uchar ch) {
                return !std::isspace(ch);
            }).base(),
            s.end());
}

inline void trim(string& s) {
    trim_start(s);
    trim_end(s);
}

inline string trim_start_copy(string s) {
    trim_start(s);
    return s;
}

inline string trim_end_copy(string s) {
    trim_end(s);
    return s;
}

inline string trim_copy(string s) {
    trim(s);
    return s;
}

inline string& remove_chars(string& s, string_ref chars) {
    s.erase(std::remove_if(s.begin(), s.end(), [&chars](name_ref c) {
                return chars.find(c) != string::npos;
            }),
            s.end());
    return s;
}

constexpr name g_punctuation_marks_ = "\"\'";

inline string& remove_punctuation_marks(string& s) {
    return remove_chars(s, g_punctuation_marks_);
}

inline string remove_chars_copy(string s, string_ref chars) {
    return remove_chars(s, chars);
}

inline string& remove_nondigit(string& s) {
    s.erase(std::remove_if(s.begin(), s.end(), [](name_ref c) {
                return !isdigit(c);
            }),
            s.end());
    return s;
}

inline string remove_nondigit_copy(string s) {
    return remove_nondigit(s);
}

inline string& remove_chars_if_not(string& s, string_ref allowed) {
    s.erase(std::remove_if(s.begin(), s.end(), [&allowed](name_ref c) {
                return allowed.find(c) == string::npos;
            }),
            s.end());
    return s;
}

inline string remove_chars_if_not_copy(string s, string_ref allowed) {
    return remove_chars_if_not(s, allowed);
}

template <typename T>
struct reversion_wrapper {
    T& iterable;
};

template <typename T>
inline auto begin(reversion_wrapper<T> w) {
    return std::rbegin(w.iterable);
}

template <typename T>
inline auto end(reversion_wrapper<T> w) {
    return std::rend(w.iterable);
}

template <typename T>
inline reversion_wrapper<T> reverse(T&& iterable) {
    return {iterable};
}

} // namespace lava
```


-------------------------------

Updated on 2026-02-01 at 18:13:39 +0000
