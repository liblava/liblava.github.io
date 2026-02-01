---
title: lava::frame_env
summary: Framework environment. 

---

# lava::frame_env



Framework environment. 


`#include <frame.hpp>`

## Public Types

|                | Name           |
| -------------- | -------------- |
| using [frame_env](/_doxybook/Classes/structlava_1_1frame__env.md) const  & | **[ref](/_doxybook/Classes/structlava_1_1frame__env.md#using-ref)** <br>Reference to frame environment.  |

## Public Functions

|                | Name           |
| -------------- | -------------- |
| | **[frame_env](/_doxybook/Classes/structlava_1_1frame__env.md#function-frame-env)**()<br>Construct a new frame environment.  |
| | **[frame_env](/_doxybook/Classes/structlava_1_1frame__env.md#function-frame-env)**([name](/_doxybook/Namespaces/namespacelava.md#using-name) app_name, argh::parser cmd_line)<br>Construct a new frame environment.  |
| void | **[set_default](/_doxybook/Classes/structlava_1_1frame__env.md#function-set-default)**()<br>Set default settings.  |

## Public Attributes

|                | Name           |
| -------------- | -------------- |
| argh::parser | **[cmd_line](/_doxybook/Classes/structlava_1_1frame__env.md#variable-cmd-line)** <br>Command line arguments.  |
| [log::config](/_doxybook/Classes/structlava_1_1log_1_1config.md) | **[log](/_doxybook/Classes/structlava_1_1frame__env.md#variable-log)** <br>Logging configuration.  |
| [instance_info](/_doxybook/Classes/structlava_1_1instance__info.md) | **[info](/_doxybook/Classes/structlava_1_1frame__env.md#variable-info)** <br>Instance information.  |
| [instance::create_param](/_doxybook/Classes/structlava_1_1instance_1_1create__param.md) | **[param](/_doxybook/Classes/structlava_1_1frame__env.md#variable-param)** <br>Instance create parameters.  |
| [instance::debug_config](/_doxybook/Classes/structlava_1_1instance_1_1debug__config.md) | **[debug](/_doxybook/Classes/structlava_1_1frame__env.md#variable-debug)** <br>Intance debug configuration.  |
| [ui32](/_doxybook/Namespaces/namespacelava.md#using-ui32) | **[telegraph_thread_count](/_doxybook/Classes/structlava_1_1frame__env.md#variable-telegraph-thread-count)** <br>Message dispatcher threads.  |

## Public Types Documentation

### using ref

```cpp
using lava::frame_env::ref =  frame_env const&;
```

Reference to frame environment. 

## Public Functions Documentation

### function frame_env

```cpp
inline explicit frame_env()
```

Construct a new frame environment. 

### function frame_env

```cpp
inline explicit frame_env(
    name app_name,
    argh::parser cmd_line
)
```

Construct a new frame environment. 

**Parameters**: 

  * **app_name** Name of application 
  * **cmd_line** Command line arguments 


### function set_default

```cpp
void set_default()
```

Set default settings. 

## Public Attributes Documentation

### variable cmd_line

```cpp
argh::parser cmd_line;
```

Command line arguments. 

### variable log

```cpp
log::config log;
```

Logging configuration. 

### variable info

```cpp
instance_info info;
```

Instance information. 

### variable param

```cpp
instance::create_param param;
```

Instance create parameters. 

### variable debug

```cpp
instance::debug_config debug;
```

Intance debug configuration. 

### variable telegraph_thread_count

```cpp
ui32 telegraph_thread_count = 4;
```

Message dispatcher threads. 

-------------------------------

Updated on 2026-02-01 at 18:13:39 +0000