---
title: lava::gamepad_manager
summary: Gamepad manager. 

---

# lava::gamepad_manager



Gamepad manager. 


`#include <gamepad.hpp>`

## Public Types

|                | Name           |
| -------------- | -------------- |
| using std::function< bool([gamepad](/_doxybook/Classes/structlava_1_1gamepad.md), bool)> | **[listener_func](/_doxybook/Classes/structlava_1_1gamepad__manager.md#using-listener-func)** <br>Gamepad listener function.  |

## Public Functions

|                | Name           |
| -------------- | -------------- |
| [gamepad_manager](/_doxybook/Classes/structlava_1_1gamepad__manager.md) & | **[singleton](/_doxybook/Classes/structlava_1_1gamepad__manager.md#function-singleton)**()<br>Get gamepad manager singleton.  |
| [id](/_doxybook/Classes/structlava_1_1id.md) | **[add](/_doxybook/Classes/structlava_1_1gamepad__manager.md#function-add)**([listener_func](/_doxybook/Classes/structlava_1_1gamepad__manager.md#using-listener-func) listener)<br>Add listener.  |
| void | **[remove](/_doxybook/Classes/structlava_1_1gamepad__manager.md#function-remove)**([id::ref](/_doxybook/Classes/structlava_1_1id.md#using-ref) func_id)<br>Remove listener.  |

## Public Types Documentation

### using listener_func

```cpp
using lava::gamepad_manager::listener_func =  std::function<bool(gamepad, bool)>;
```

Gamepad listener function. 

## Public Functions Documentation

### function singleton

```cpp
static inline gamepad_manager & singleton()
```

Get gamepad manager singleton. 

**Return**: [gamepad_manager](/_doxybook/Classes/structlava_1_1gamepad__manager.md)& Gamepad manager 

### function add

```cpp
id add(
    listener_func listener
)
```

Add listener. 

**Parameters**: 

  * **listener** Gamepad listener function 


**Return**: id Id of function 

### function remove

```cpp
void remove(
    id::ref func_id
)
```

Remove listener. 

**Parameters**: 

  * **func_id** Id of function 


-------------------------------

Updated on 2026-02-01 at 18:13:39 +0000