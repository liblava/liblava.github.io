---
title: lava::log

---

# lava::log



## Classes

|                | Name           |
| -------------- | -------------- |
| struct | **[lava::log::config](/_doxybook/Classes/structlava_1_1log_1_1config.md)** <br>Log configuration.  |

## Functions

|                | Name           |
| -------------- | -------------- |
| [s_logger](/_doxybook/Namespaces/namespacelava.md#using-s-logger) | **[setup](/_doxybook/Namespaces/namespacelava_1_1log.md#function-setup)**([config](/_doxybook/Classes/structlava_1_1log_1_1config.md) config ={})<br>Set up logging.  |
| void | **[teardown](/_doxybook/Namespaces/namespacelava_1_1log.md#function-teardown)**([config](/_doxybook/Classes/structlava_1_1log_1_1config.md) config ={})<br>Tear down logging.  |


## Functions Documentation

### function setup

```cpp
inline s_logger setup(
    config config ={}
)
```

Set up logging. 

**Parameters**: 

  * **config** Log configuration 


**Return**: [s_logger](/_doxybook/Namespaces/namespacelava.md#using-s-logger) Logger 

### function teardown

```cpp
inline void teardown(
    config config ={}
)
```

Tear down logging. 

**Parameters**: 

  * **config** Log configuration 






-------------------------------

Updated on 2026-02-01 at 18:13:39 +0000