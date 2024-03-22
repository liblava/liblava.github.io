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
| virtual void | **[set_json](/_doxybook/Classes/structlava_1_1configurable.md#function-set-json)**(json_ref j) =0<br>Set json config.  |
| virtual json | **[get_json](/_doxybook/Classes/structlava_1_1configurable.md#function-get-json)**() const =0<br>Get json config.  |

## Additional inherited members

**Public Functions inherited from [lava::interface](/_doxybook/Classes/structlava_1_1interface.md)**

|                | Name           |
| -------------- | -------------- |
| virtual | **[~interface](/_doxybook/Classes/structlava_1_1interface.md#function-~interface)**() =default<br>Destroy the interface.  |


## Public Functions Documentation

### function set_json

```cpp
virtual void set_json(
    json_ref j
) =0
```

Set json config. 

**Parameters**: 

  * **j** Json file 


**Reimplemented by**: [lava::app_config::set_json](/_doxybook/Classes/structlava_1_1app__config.md#function-set-json), [lava::property::set_json](/_doxybook/Classes/structlava_1_1property.md#function-set-json)


### function get_json

```cpp
virtual json get_json() const =0
```

Get json config. 

**Return**: json Json file 

**Reimplemented by**: [lava::app_config::get_json](/_doxybook/Classes/structlava_1_1app__config.md#function-get-json), [lava::property::get_json](/_doxybook/Classes/structlava_1_1property.md#function-get-json)


-------------------------------

Updated on 2024-03-22 at 21:51:37 +0000