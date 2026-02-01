---
title: lava::instance
summary: Vulkan instance. 

---

# lava::instance



Vulkan instance. 


`#include <instance.hpp>`

Inherits from [lava::no_copy_no_move](/_doxybook/Classes/structlava_1_1no__copy__no__move.md)

## Public Classes

|                | Name           |
| -------------- | -------------- |
| struct | **[create_param](/_doxybook/Classes/structlava_1_1instance_1_1create__param.md)** <br>Instance create parameters.  |
| struct | **[debug_config](/_doxybook/Classes/structlava_1_1instance_1_1debug__config.md)** <br>Debug configuration.  |

## Public Functions

|                | Name           |
| -------------- | -------------- |
| [instance](/_doxybook/Classes/structlava_1_1instance.md) & | **[singleton](/_doxybook/Classes/structlava_1_1instance.md#function-singleton)**()<br>Instance singleton.  |
| bool | **[create](/_doxybook/Classes/structlava_1_1instance.md#function-create)**([create_param](/_doxybook/Classes/structlava_1_1instance_1_1create__param.md) & param, [debug_config::ref](/_doxybook/Classes/structlava_1_1instance_1_1debug__config.md#using-ref) debug, [instance_info::ref](/_doxybook/Classes/structlava_1_1instance__info.md#using-ref) info)<br>Create a new instance.  |
| void | **[destroy](/_doxybook/Classes/structlava_1_1instance.md#function-destroy)**()<br>Destroy the instance.  |
| [physical_device::s_list](/_doxybook/Classes/structlava_1_1physical__device.md#using-s-list) const & | **[get_physical_devices](/_doxybook/Classes/structlava_1_1instance.md#function-get-physical-devices)**() const<br>Get the physical devices.  |
| [physical_device::ref](/_doxybook/Classes/structlava_1_1physical__device.md#using-ref) | **[get_first_physical_device](/_doxybook/Classes/structlava_1_1instance.md#function-get-first-physical-device)**() const<br>Get the first physical device.  |
| VkInstance | **[get](/_doxybook/Classes/structlava_1_1instance.md#function-get)**() const<br>Get the Vulkan instance.  |
| [debug_config::ref](/_doxybook/Classes/structlava_1_1instance_1_1debug__config.md#using-ref) | **[get_debug_config](/_doxybook/Classes/structlava_1_1instance.md#function-get-debug-config)**() const<br>Get the debug configuration.  |
| [instance_info::ref](/_doxybook/Classes/structlava_1_1instance__info.md#using-ref) | **[get_info](/_doxybook/Classes/structlava_1_1instance.md#function-get-info)**() const<br>Get the instance information.  |

## Additional inherited members

**Public Functions inherited from [lava::no_copy_no_move](/_doxybook/Classes/structlava_1_1no__copy__no__move.md)**

|                | Name           |
| -------------- | -------------- |
| | **[no_copy_no_move](/_doxybook/Classes/structlava_1_1no__copy__no__move.md#function-no-copy-no-move)**() =default<br>Construct a new object.  |
| | **[no_copy_no_move](/_doxybook/Classes/structlava_1_1no__copy__no__move.md#function-no-copy-no-move)**([no_copy_no_move](/_doxybook/Classes/structlava_1_1no__copy__no__move.md) const & ) =delete<br>No copy.  |
| void | **[operator=](/_doxybook/Classes/structlava_1_1no__copy__no__move.md#function-operator=)**([no_copy_no_move](/_doxybook/Classes/structlava_1_1no__copy__no__move.md) const & ) =delete<br>No move.  |


## Public Functions Documentation

### function singleton

```cpp
static inline instance & singleton()
```

Instance singleton. 

**Return**: instance& Instance 

### function create

```cpp
bool create(
    create_param & param,
    debug_config::ref debug,
    instance_info::ref info
)
```

Create a new instance. 

**Parameters**: 

  * **param** Create parameters 
  * **debug** Debug configuration 
  * **info** Instance information 


**Return**: Create was successful or failed 

### function destroy

```cpp
void destroy()
```

Destroy the instance. 

### function get_physical_devices

```cpp
inline physical_device::s_list const & get_physical_devices() const
```

Get the physical devices. 

**Return**: [physical_device::s_list](/_doxybook/Classes/structlava_1_1physical__device.md#using-s-list) const& List of physical devices 

### function get_first_physical_device

```cpp
inline physical_device::ref get_first_physical_device() const
```

Get the first physical device. 

**Return**: [physical_device::ref](/_doxybook/Classes/structlava_1_1physical__device.md#using-ref) Physcial device 

### function get

```cpp
inline VkInstance get() const
```

Get the Vulkan instance. 

**Return**: VkInstance Vulkan instance 

### function get_debug_config

```cpp
inline debug_config::ref get_debug_config() const
```

Get the debug configuration. 

**Return**: [debug_config::ref](/_doxybook/Classes/structlava_1_1instance_1_1debug__config.md#using-ref) Debug configuration 

### function get_info

```cpp
inline instance_info::ref get_info() const
```

Get the instance information. 

**Return**: [instance_info::ref](/_doxybook/Classes/structlava_1_1instance__info.md#using-ref) Instance information 

-------------------------------

Updated on 2026-02-01 at 18:13:39 +0000