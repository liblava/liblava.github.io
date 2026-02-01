---
title: lava::log::config
summary: Log configuration. 

---

# lava::log::config



Log configuration. 


`#include <log.hpp>`

## Public Attributes

|                | Name           |
| -------------- | -------------- |
| [name](/_doxybook/Namespaces/namespacelava.md#using-name) | **[logger](/_doxybook/Classes/structlava_1_1log_1_1config.md#variable-logger)** <br>Logger name.  |
| [name](/_doxybook/Namespaces/namespacelava.md#using-name) | **[file](/_doxybook/Classes/structlava_1_1log_1_1config.md#variable-file)** <br>Log file.  |
| [i32](/_doxybook/Namespaces/namespacelava.md#using-i32) | **[level](/_doxybook/Classes/structlava_1_1log_1_1config.md#variable-level)** <br>Log level.  |
| bool | **[debug](/_doxybook/Classes/structlava_1_1log_1_1config.md#variable-debug)** <br>Log to console, else file.  |

## Public Attributes Documentation

### variable logger

```cpp
name logger = _lava_;
```

Logger name. 

### variable file

```cpp
name file = "lava.log";
```

Log file. 

### variable level

```cpp
i32 level = undef;
```

Log level. 

### variable debug

```cpp
bool debug = false;
```

Log to console, else file. 

-------------------------------

Updated on 2026-02-01 at 18:13:39 +0000