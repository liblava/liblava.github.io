---
title: lava::benchmark_data
summary: Benchmark data. 

---

# lava::benchmark_data



Benchmark data. 


`#include <benchmark.hpp>`

## Public Types

|                | Name           |
| -------------- | -------------- |
| using std::vector< [ui32](/_doxybook/Namespaces/namespacelava.md#using-ui32) > | **[list](/_doxybook/Classes/structlava_1_1benchmark__data.md#using-list)** <br>List of frame times.  |

## Public Attributes

|                | Name           |
| -------------- | -------------- |
| [ms](/_doxybook/Namespaces/namespacelava.md#using-ms) | **[time](/_doxybook/Classes/structlava_1_1benchmark__data.md#variable-time)** <br>Benchmark duration.  |
| [ms](/_doxybook/Namespaces/namespacelava.md#using-ms) | **[offset](/_doxybook/Classes/structlava_1_1benchmark__data.md#variable-offset)** <br>Warm up time.  |
| [string](/_doxybook/Namespaces/namespacelava.md#using-string) | **[file](/_doxybook/Classes/structlava_1_1benchmark__data.md#variable-file)** <br>Output file.  |
| [string](/_doxybook/Namespaces/namespacelava.md#using-string) | **[path](/_doxybook/Classes/structlava_1_1benchmark__data.md#variable-path)** <br>Output path (empty: pref_dir)  |
| bool | **[exit](/_doxybook/Classes/structlava_1_1benchmark__data.md#variable-exit)** <br>Close app after benchmark.  |
| [ui32](/_doxybook/Namespaces/namespacelava.md#using-ui32) | **[buffer_size](/_doxybook/Classes/structlava_1_1benchmark__data.md#variable-buffer-size)** <br>Pre-allocated buffer size for results.  |
| [list](/_doxybook/Classes/structlava_1_1benchmark__data.md#using-list) | **[values](/_doxybook/Classes/structlava_1_1benchmark__data.md#variable-values)** <br>Benchmark results.  |
| [index](/_doxybook/Namespaces/namespacelava.md#using-index) | **[current](/_doxybook/Classes/structlava_1_1benchmark__data.md#variable-current)** <br>Current frame index.  |
| [ms](/_doxybook/Namespaces/namespacelava.md#using-ms) | **[start_timestamp](/_doxybook/Classes/structlava_1_1benchmark__data.md#variable-start-timestamp)** <br>Benchmark start timestamp.  |

## Public Types Documentation

### using list

```cpp
using lava::benchmark_data::list =  std::vector<ui32>;
```

List of frame times. 

## Public Attributes Documentation

### variable time

```cpp
ms time = ms{10000};
```

Benchmark duration. 

### variable offset

```cpp
ms offset = ms{5000};
```

Warm up time. 

### variable file

```cpp
string file = _benchmark_json_;
```

Output file. 

### variable path

```cpp
string path;
```

Output path (empty: pref_dir) 

### variable exit

```cpp
bool exit = true;
```

Close app after benchmark. 

### variable buffer_size

```cpp
ui32 buffer_size = 100000;
```

Pre-allocated buffer size for results. 

### variable values

```cpp
list values;
```

Benchmark results. 

### variable current

```cpp
index current = 0;
```

Current frame index. 

### variable start_timestamp

```cpp
ms start_timestamp = ms{0};
```

Benchmark start timestamp. 

-------------------------------

Updated on 2026-02-01 at 18:13:39 +0000