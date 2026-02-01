---
title: liblava/util/random.hpp
summary: Random generator. 

---

# liblava/util/random.hpp

Random generator.  [More...](#detailed-description)

## Namespaces

| Name           |
| -------------- |
| **[lava](/_doxybook/Namespaces/namespacelava.md)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| struct | **[lava::random_generator](/_doxybook/Classes/structlava_1_1random__generator.md)** <br>Random generator.  |
| struct | **[lava::pseudorandom_generator](/_doxybook/Classes/structlava_1_1pseudorandom__generator.md)** <br>Pseudorandom generator.  |

## Detailed Description

Random generator. 

**Author**: Lava Block OÜ and contributors 

**Copyright**: Copyright (c) 2018-present, MIT License 



## Source code

```cpp


#pragma once

#include "liblava/core/types.hpp"
#include <random>

namespace lava {

struct random_generator {
    random_generator() {
        std::random_device rd;
        m_engine = std::mt19937(rd());
    }

    i32 get(i32 low, i32 high) {
        std::uniform_int_distribution<i32> dist(low, high);
        return dist(m_engine);
    }

    template <typename T = real>
    T get(T low, T high) {
        std::uniform_real_distribution<T> dist(low, high);
        return dist(m_engine);
    }

private:
    std::mt19937 m_engine;
};

inline auto random(auto low, auto high) {
    return random_generator().get(low, high);
}

inline auto random(auto high) {
    return random_generator().get({}, high);
}

struct pseudorandom_generator {
    explicit pseudorandom_generator(ui32 seed)
    : m_seed(seed) {}

    void set_seed(ui32 value) {
        m_seed = value;
    }

    ui32 get() {
        return generate_fast() ^ (generate_fast() >> 7);
    }

private:
    ui32 m_seed = 0;

    ui32 generate_fast() {
        return m_seed = (m_seed * 196314165 + 907633515);
    }
};

} // namespace lava
```


-------------------------------

Updated on 2026-02-01 at 18:13:39 +0000
