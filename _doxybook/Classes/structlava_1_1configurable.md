---
title: lava::configurable
summary: Configurable interface. 

---

# lava::configurable



Configurable interface. 


`#include <json.hpp>`

Inherits from [lava::interface](/_doxybook/Classes/structlava_1_1interface.md)

Inherited by [lava::app_config](/_doxybook/Classes/structlava_1_1app__config.md), [lava::property](/_doxybook/Classes/structlava_1_1property.md)

## Public Functions

|                | Name           |
| -------------- | -------------- |
| virtual void | **[set_config](/_doxybook/Classes/structlava_1_1configurable.md#function-set-config)**(json_ref j) =0<br>Set config.  |
| virtual json | **[get_config](/_doxybook/Classes/structlava_1_1configurable.md#function-get-config)**() const =0<br>Get config.  |

## Additional inherited members

**Public Functions inherited from [lava::interface](/_doxybook/Classes/structlava_1_1interface.md)**

|                | Name           |
| -------------- | -------------- |
| virtual | **[~interface](/_doxybook/Classes/structlava_1_1interface.md#function-~interface)**() =default<br>Destroy the interface.  |


## Public Functions Documentation

### function set_config

```cpp
virtual void set_config(
    json_ref j
) =0
```

Set config. 

**Parameters**: 

  * **j** Json file 


**Reimplemented by**: [lava::app_config::set_config](/_doxybook/Classes/structlava_1_1app__config.md#function-set-config), [lava::property::set_config](/_doxybook/Classes/structlava_1_1property.md#function-set-config)


### function get_config

```cpp
virtual json get_config() const =0
```

Get config. 

**Return**: json Json file 

**Reimplemented by**: [lava::app_config::get_config](/_doxybook/Classes/structlava_1_1app__config.md#function-get-config), [lava::property::get_config](/_doxybook/Classes/structlava_1_1property.md#function-get-config)


-------------------------------

Updated on 2022-11-30 at 01:16:03 +0000