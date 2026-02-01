---
title: lava::platform
summary: Stage platform. 

---

# lava::platform



Stage platform. 


`#include <platform.hpp>`

## Public Types

|                | Name           |
| -------------- | -------------- |
| using [platform](/_doxybook/Classes/structlava_1_1platform.md) * | **[ptr](/_doxybook/Classes/structlava_1_1platform.md#using-ptr)** <br>Pointer to platform.  |
| using std::function< void([device::create_param](/_doxybook/Classes/structlava_1_1device_1_1create__param.md) &)> | **[create_param_func](/_doxybook/Classes/structlava_1_1platform.md#using-create-param-func)** <br>Create parameter function.  |

## Public Functions

|                | Name           |
| -------------- | -------------- |
| [device::s_ptr](/_doxybook/Classes/structlava_1_1device.md#using-s-ptr) | **[create](/_doxybook/Classes/structlava_1_1platform.md#function-create)**([index](/_doxybook/Namespaces/namespacelava.md#using-index) physical_device =0)<br>Create a managed device from a physical device.  |
| [device::s_ptr](/_doxybook/Classes/structlava_1_1device.md#using-s-ptr) | **[create](/_doxybook/Classes/structlava_1_1platform.md#function-create)**([device::create_param::ref](/_doxybook/Classes/structlava_1_1device_1_1create__param.md#using-ref) param)<br>Create a managed device with create parameters.  |
| [device::ptr](/_doxybook/Classes/structlava_1_1device.md#using-ptr) | **[create_device](/_doxybook/Classes/structlava_1_1platform.md#function-create-device)**([index](/_doxybook/Namespaces/namespacelava.md#using-index) physical_device =0)<br>Create a managed device.  |
| [device::s_list](/_doxybook/Classes/structlava_1_1device.md#using-s-list) const & | **[get_devices](/_doxybook/Classes/structlava_1_1platform.md#function-get-devices)**() const<br>Get all devices.  |
| void | **[wait_idle](/_doxybook/Classes/structlava_1_1platform.md#function-wait-idle)**()<br>Wait for idle on all managed devices.  |
| bool | **[remove](/_doxybook/Classes/structlava_1_1platform.md#function-remove)**([id::ref](/_doxybook/Classes/structlava_1_1id.md#using-ref) device_id)<br>Remove device from platform.  |
| void | **[clear](/_doxybook/Classes/structlava_1_1platform.md#function-clear)**()<br>Clear all managed devices.  |

## Public Attributes

|                | Name           |
| -------------- | -------------- |
| [create_param_func](/_doxybook/Classes/structlava_1_1platform.md#using-create-param-func) | **[on_create_param](/_doxybook/Classes/structlava_1_1platform.md#variable-on-create-param)** <br>Called on create to adjust the create parameters.  |

## Public Types Documentation

### using ptr

```cpp
using lava::platform::ptr =  platform*;
```

Pointer to platform. 

### using create_param_func

```cpp
using lava::platform::create_param_func =  std::function<void(device::create_param&)>;
```

Create parameter function. 

## Public Functions Documentation

### function create

```cpp
device::s_ptr create(
    index physical_device =0
)
```

Create a managed device from a physical device. 

**Parameters**: 

  * **[physical_device](/_doxybook/Classes/structlava_1_1physical__device.md)** Index of physical device 


**Return**: [device::s_ptr](/_doxybook/Classes/structlava_1_1device.md#using-s-ptr) Vulkan device 

### function create

```cpp
device::s_ptr create(
    device::create_param::ref param
)
```

Create a managed device with create parameters. 

**Parameters**: 

  * **param** Create parameters 


**Return**: [device::s_ptr](/_doxybook/Classes/structlava_1_1device.md#using-s-ptr) Vulkan device 

### function create_device

```cpp
device::ptr create_device(
    index physical_device =0
)
```

Create a managed device. 

**Parameters**: 

  * **[physical_device](/_doxybook/Classes/structlava_1_1physical__device.md)** Physical device 


**Return**: [device::s_ptr](/_doxybook/Classes/structlava_1_1device.md#using-s-ptr) Pointer to device 

### function get_devices

```cpp
inline device::s_list const & get_devices() const
```

Get all devices. 

**Return**: [device::s_list](/_doxybook/Classes/structlava_1_1device.md#using-s-list) const& List of devices 

### function wait_idle

```cpp
void wait_idle()
```

Wait for idle on all managed devices. 

### function remove

```cpp
bool remove(
    id::ref device_id
)
```

Remove device from platform. 

**Parameters**: 

  * **device_id** Id of device 


**Return**: Remove was successful or failed 

### function clear

```cpp
void clear()
```

Clear all managed devices. 

## Public Attributes Documentation

### variable on_create_param

```cpp
create_param_func on_create_param;
```

Called on create to adjust the create parameters. 

-------------------------------

Updated on 2026-02-01 at 18:13:39 +0000