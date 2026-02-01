---
title: lava::global_logger
summary: Global logger. 

---

# lava::global_logger



Global logger. 


`#include <log.hpp>`

## Public Functions

|                | Name           |
| -------------- | -------------- |
| [global_logger](/_doxybook/Classes/structlava_1_1global__logger.md) & | **[singleton](/_doxybook/Classes/structlava_1_1global__logger.md#function-singleton)**()<br>Get global logger singleton.  |
| [s_logger](/_doxybook/Namespaces/namespacelava.md#using-s-logger) | **[get](/_doxybook/Classes/structlava_1_1global__logger.md#function-get)**()<br>Get logger.  |
| void | **[set](/_doxybook/Classes/structlava_1_1global__logger.md#function-set)**([lava::s_logger](/_doxybook/Namespaces/namespacelava.md#using-s-logger) l)<br>Set logger.  |
| void | **[reset](/_doxybook/Classes/structlava_1_1global__logger.md#function-reset)**()<br>Reset logger.  |

## Public Functions Documentation

### function singleton

```cpp
static inline global_logger & singleton()
```

Get global logger singleton. 

**Return**: [global_logger](/_doxybook/Classes/structlava_1_1global__logger.md)& Global logger 

### function get

```cpp
inline s_logger get()
```

Get logger. 

**Return**: [s_logger](/_doxybook/Namespaces/namespacelava.md#using-s-logger) Logger 

### function set

```cpp
inline void set(
    lava::s_logger l
)
```

Set logger. 

**Parameters**: 

  * **l** Logger 


### function reset

```cpp
inline void reset()
```

Reset logger. 

-------------------------------

Updated on 2026-02-01 at 18:13:39 +0000