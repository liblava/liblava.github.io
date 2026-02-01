---
title: lava::driver
summary: Stage driver. 

---

# lava::driver



Stage driver. 


`#include <driver.hpp>`

## Public Classes

|                | Name           |
| -------------- | -------------- |
| struct | **[result](/_doxybook/Classes/structlava_1_1driver_1_1result.md)** <br>Driver result.  |

## Public Types

|                | Name           |
| -------------- | -------------- |
| enum| **[error](/_doxybook/Classes/structlava_1_1driver.md#enum-error)** { stages_empty = -1, stage_not_found = -2, undef_run = -3}<br>Driver error codes.  |
| using std::function< [result](/_doxybook/Classes/structlava_1_1driver_1_1result.md)(argh::parser)> | **[run_func](/_doxybook/Classes/structlava_1_1driver.md#using-run-func)** <br>Run function.  |

## Public Functions

|                | Name           |
| -------------- | -------------- |
| [driver](/_doxybook/Classes/structlava_1_1driver.md) & | **[instance](/_doxybook/Classes/structlava_1_1driver.md#function-instance)**()<br>Get driver instance.  |
| void | **[add_stage](/_doxybook/Classes/structlava_1_1driver.md#function-add-stage)**([stage](/_doxybook/Classes/structlava_1_1stage.md) * stage)<br>Add a stage.  |
| [stage::map](/_doxybook/Classes/structlava_1_1stage.md#using-map) const & | **[get_stages](/_doxybook/Classes/structlava_1_1driver.md#function-get-stages)**() const<br>Get all stages.  |
| [i32](/_doxybook/Namespaces/namespacelava.md#using-i32) | **[run](/_doxybook/Classes/structlava_1_1driver.md#function-run)**(argh::parser cmd_line ={})<br>Run the driver.  |

## Public Attributes

|                | Name           |
| -------------- | -------------- |
| [run_func](/_doxybook/Classes/structlava_1_1driver.md#using-run-func) | **[on_run](/_doxybook/Classes/structlava_1_1driver.md#variable-on-run)** <br>Called if no stage has been selected.  |

## Public Types Documentation

### enum error

| Enumerator | Value | Description |
| ---------- | ----- | ----------- |
| stages_empty | -1|   |
| stage_not_found | -2|   |
| undef_run | -3|   |



Driver error codes. 

### using run_func

```cpp
using lava::driver::run_func =  std::function<result(argh::parser)>;
```

Run function. 

## Public Functions Documentation

### function instance

```cpp
static inline driver & instance()
```

Get driver instance. 

**Return**: driver& Stage driver 

### function add_stage

```cpp
inline void add_stage(
    stage * stage
)
```

Add a stage. 

**Parameters**: 

  * **stage** Stage to add 


### function get_stages

```cpp
inline stage::map const & get_stages() const
```

Get all stages. 

**Return**: [stage::map](/_doxybook/Classes/structlava_1_1stage.md#using-map) const& Map of stages 

### function run

```cpp
i32 run(
    argh::parser cmd_line ={}
)
```

Run the driver. 

**Parameters**: 

  * **[cmd_line](/_doxybook/Namespaces/namespacelava.md#using-cmd-line)** Command line arguments 


**Return**: [i32](/_doxybook/Namespaces/namespacelava.md#using-i32) Result code 

## Public Attributes Documentation

### variable on_run

```cpp
run_func on_run;
```

Called if no stage has been selected. 

-------------------------------

Updated on 2026-02-01 at 18:13:39 +0000