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
| [logger](/_doxybook/Namespaces/namespacelava.md#using-logger) | **[get](/_doxybook/Classes/structlava_1_1global__logger.md#function-get)**()<br>Get logger.  |
| void | **[set](/_doxybook/Classes/structlava_1_1global__logger.md#function-set)**([lava::logger](/_doxybook/Namespaces/namespacelava.md#using-logger) l)<br>Set logger.  |
| void | **[reset](/_doxybook/Classes/structlava_1_1global__logger.md#function-reset)**()<br>Reset logger.  |

## Public Functions Documentation

### function singleton

```cpp
static inline global_logger & singleton()
```

Get global logger singleton. 

**Return**: log_global& Global logger 

### function get

```cpp
inline logger get()
```

Get logger. 

**Return**: logger Logger 

### function set

```cpp
inline void set(
    lava::logger l
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

Updated on 2022-11-30 at 01:16:03 +0000