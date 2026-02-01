---
title: lava::run_time
summary: Run time. 

---

# lava::run_time



Run time. 


`#include <time.hpp>`

## Public Attributes

|                | Name           |
| -------------- | -------------- |
| [ms](/_doxybook/Namespaces/namespacelava.md#using-ms) | **[current](/_doxybook/Classes/structlava_1_1run__time.md#variable-current)** <br>Current milliseconds.  |
| [ms](/_doxybook/Namespaces/namespacelava.md#using-ms) | **[clock](/_doxybook/Classes/structlava_1_1run__time.md#variable-clock)** <br>Clock milliseconds.  |
| [ms](/_doxybook/Namespaces/namespacelava.md#using-ms) | **[system](/_doxybook/Classes/structlava_1_1run__time.md#variable-system)** <br>System milliseconds.  |
| [ms](/_doxybook/Namespaces/namespacelava.md#using-ms) | **[delta](/_doxybook/Classes/structlava_1_1run__time.md#variable-delta)** <br>Delta milliseconds.  |
| [ms](/_doxybook/Namespaces/namespacelava.md#using-ms) | **[fix_delta](/_doxybook/Classes/structlava_1_1run__time.md#variable-fix-delta)** <br>Fix delta milliseconds (0 = deactivated)  |
| [r32](/_doxybook/Namespaces/namespacelava.md#using-r32) | **[speed](/_doxybook/Classes/structlava_1_1run__time.md#variable-speed)** <br>Speed factor.  |
| bool | **[paused](/_doxybook/Classes/structlava_1_1run__time.md#variable-paused)** <br>Paused run time.  |

## Public Attributes Documentation

### variable current

```cpp
ms current {0};
```

Current milliseconds. 

### variable clock

```cpp
ms clock {16};
```

Clock milliseconds. 

### variable system

```cpp
ms system {0};
```

System milliseconds. 

### variable delta

```cpp
ms delta {0};
```

Delta milliseconds. 

### variable fix_delta

```cpp
ms fix_delta {0};
```

Fix delta milliseconds (0 = deactivated) 

### variable speed

```cpp
r32 speed = 1.f;
```

Speed factor. 

### variable paused

```cpp
bool paused = false;
```

Paused run time. 

-------------------------------

Updated on 2026-02-01 at 18:13:39 +0000