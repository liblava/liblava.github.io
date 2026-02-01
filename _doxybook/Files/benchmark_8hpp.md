---
title: liblava/app/benchmark.hpp
summary: Benchmark. 

---

# liblava/app/benchmark.hpp

Benchmark.  [More...](#detailed-description)

## Namespaces

| Name           |
| -------------- |
| **[lava](/_doxybook/Namespaces/namespacelava.md)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| struct | **[lava::benchmark_data](/_doxybook/Classes/structlava_1_1benchmark__data.md)** <br>Benchmark data.  |

## Detailed Description

Benchmark. 

**Author**: Lava Block OÜ and contributors 

**Copyright**: Copyright (c) 2018-present, MIT License 



## Source code

```cpp


#pragma once

#include "liblava/app/def.hpp"
#include "liblava/frame/frame.hpp"

namespace lava {

struct benchmark_data {
    ms time = ms{10000};

    ms offset = ms{5000};

    string file = _benchmark_json_;

    string path;

    bool exit = true;

    ui32 buffer_size = 100000;

    using list = std::vector<ui32>;

    list values;

    index current = 0;

    ms start_timestamp = ms{0};
};

bool parse_benchmark(cmd_line cmd_line, benchmark_data& data);

void benchmark(frame& app, benchmark_data& data);

bool write_frames_json(benchmark_data& data);

} // namespace lava
```


-------------------------------

Updated on 2026-02-01 at 18:13:39 +0000
