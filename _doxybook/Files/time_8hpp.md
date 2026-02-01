---
title: liblava/core/time.hpp
summary: Run time. 

---

# liblava/core/time.hpp

Run time.  [More...](#detailed-description)

## Namespaces

| Name           |
| -------------- |
| **[lava](/_doxybook/Namespaces/namespacelava.md)**  |
| **[std::chrono_literals](/_doxybook/Namespaces/namespacestd_1_1chrono__literals.md)** <br>Chrono literals.  |

## Classes

|                | Name           |
| -------------- | -------------- |
| struct | **[lava::timer](/_doxybook/Classes/structlava_1_1timer.md)** <br>Timer.  |
| struct | **[lava::run_time](/_doxybook/Classes/structlava_1_1run__time.md)** <br>Run time.  |

## Detailed Description

Run time. 

**Author**: Lava Block OÜ and contributors 

**Copyright**: Copyright (c) 2018-present, MIT License 



## Source code

```cpp


#pragma once

#include "liblava/core/types.hpp"
#include <chrono>
#include <iomanip>
#include <sstream>

namespace lava {

using namespace std::chrono_literals;

using seconds = std::chrono::seconds;

using milliseconds = std::chrono::milliseconds;

using ms = milliseconds;

using microseconds = std::chrono::microseconds;

using us = microseconds;

constexpr seconds const one_second = seconds(1);

constexpr ms const one_ms = ms(1);

constexpr us const one_us = us(1);

using clock = std::chrono::high_resolution_clock;

using time_point = clock::time_point;

using duration = clock::duration;

inline delta to_delta(milliseconds ms) {
    return ms.count() / 1000.f;
}

inline delta to_dt(milliseconds ms) {
    return to_delta(ms);
}

inline real to_sec(milliseconds ms) {
    return ms.count() / 1000.;
}

inline i32 to_sec_fix(milliseconds ms) {
    return to_i32(to_sec(ms));
}

inline ms to_ms(delta dt) {
    return ms(to_i32(dt * 1000.f));
}

inline ms to_ms(real sec) {
    return ms(to_i32(sec * 1000.));
}

struct timer {
    timer()
    : m_start_time(clock::now()) {}

    void reset() {
        m_start_time = clock::now();
    }

    ms elapsed() const {
        return std::chrono::duration_cast<ms>(clock::now()
                                              - m_start_time);
    }

private:
    time_point m_start_time;
};

struct run_time {
    ms current{0};

    ms clock{16};

    ms system{0};

    ms delta{0};

    ms fix_delta{0};

    r32 speed = 1.f;

    bool paused = false;
};

#ifdef _WIN32
    #pragma warning(push)
    #pragma warning(disable : 4996) //_CRT_SECURE_NO_WARNINGS
#endif

template <typename CLOCK_TYPE = std::chrono::system_clock>
inline string timestamp(const typename CLOCK_TYPE::time_point& time_point,
                        string_ref format = "%Y-%m-%d %H-%M-%S") {
    auto ms = std::chrono::duration_cast<milliseconds>(
                  time_point.time_since_epoch())
              % 1000;

    auto const t = CLOCK_TYPE::to_time_t(time_point);
    auto const tm = *std::localtime(std::addressof(t));

    std::ostringstream stm;
    stm << std::put_time(std::addressof(tm), str(format))
        << '.' << std::setfill('0') << std::setw(3) << ms.count();
    return stm.str();
}

inline string get_current_time() {
    auto now = std::chrono::system_clock::now();
    return timestamp(now);
}

#ifdef _WIN32
    #pragma warning(pop)
#endif

inline ms get_current_timestamp_ms() {
    return std::chrono::duration_cast<ms>(
        clock::now().time_since_epoch());
}

inline us get_current_timestamp_us() {
    return std::chrono::duration_cast<us>(
        clock::now().time_since_epoch());
}

inline ui64 get_current_timestamp() {
    return get_current_timestamp_ms().count();
}

} // namespace lava
```


-------------------------------

Updated on 2026-02-01 at 18:13:39 +0000
