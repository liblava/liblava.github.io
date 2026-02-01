---
title: lava::command
summary: Block command. 

---

# lava::command



Block command. 


`#include <block.hpp>`

Inherits from [lava::entity](/_doxybook/Classes/structlava_1_1entity.md), [lava::no_copy_no_move](/_doxybook/Classes/structlava_1_1no__copy__no__move.md), [lava::interface](/_doxybook/Classes/structlava_1_1interface.md)

## Public Types

|                | Name           |
| -------------- | -------------- |
| using std::shared_ptr< [command](/_doxybook/Classes/structlava_1_1command.md) > | **[s_ptr](/_doxybook/Classes/structlava_1_1command.md#using-s-ptr)** <br>Shared pointer to command.  |
| using [command](/_doxybook/Classes/structlava_1_1command.md) const  * | **[c_ptr](/_doxybook/Classes/structlava_1_1command.md#using-c-ptr)** <br>Const pointer to command.  |
| using std::map< [id](/_doxybook/Classes/structlava_1_1id.md), [s_ptr](/_doxybook/Classes/structlava_1_1command.md#using-s-ptr) > | **[s_map](/_doxybook/Classes/structlava_1_1command.md#using-s-map)** <br>Map of commands.  |
| using std::vector< [c_ptr](/_doxybook/Classes/structlava_1_1command.md#using-c-ptr) > | **[c_list](/_doxybook/Classes/structlava_1_1command.md#using-c-list)** <br>List of commands.  |
| using std::function< void(VkCommandBuffer)> | **[process_func](/_doxybook/Classes/structlava_1_1command.md#using-process-func)** <br>Command process function.  |

## Public Functions

|                | Name           |
| -------------- | -------------- |
| [s_ptr](/_doxybook/Classes/structlava_1_1command.md#using-s-ptr) | **[make](/_doxybook/Classes/structlava_1_1command.md#function-make)**()<br>Make a new command.  |
| bool | **[create](/_doxybook/Classes/structlava_1_1command.md#function-create)**([device::ptr](/_doxybook/Classes/structlava_1_1device.md#using-ptr) device, [index](/_doxybook/Namespaces/namespacelava.md#using-index) frame_count, [VkCommandPools](/_doxybook/Namespaces/namespacelava.md#using-vkcommandpools) command_pools)<br>Create a new command.  |
| void | **[destroy](/_doxybook/Classes/structlava_1_1command.md#function-destroy)**([device::ptr](/_doxybook/Classes/structlava_1_1device.md#using-ptr) device, [VkCommandPools](/_doxybook/Namespaces/namespacelava.md#using-vkcommandpools) command_pools)<br>Destroy the command.  |

## Public Attributes

|                | Name           |
| -------------- | -------------- |
| [VkCommandBuffers](/_doxybook/Namespaces/namespacelava.md#using-vkcommandbuffers) | **[buffers](/_doxybook/Classes/structlava_1_1command.md#variable-buffers)** <br>List of command buffers.  |
| [process_func](/_doxybook/Classes/structlava_1_1command.md#using-process-func) | **[on_process](/_doxybook/Classes/structlava_1_1command.md#variable-on-process)** <br>Called on command process.  |
| bool | **[active](/_doxybook/Classes/structlava_1_1command.md#variable-active)** <br>Active state.  |

## Additional inherited members

**Public Functions inherited from [lava::entity](/_doxybook/Classes/structlava_1_1entity.md)**

|                | Name           |
| -------------- | -------------- |
| | **[entity](/_doxybook/Classes/structlava_1_1entity.md#function-entity)**()<br>Construct a new entity.  |
| [id::ref](/_doxybook/Classes/structlava_1_1id.md#using-ref) | **[get_id](/_doxybook/Classes/structlava_1_1entity.md#function-get-id)**() const<br>Get the id of entity.  |

**Public Functions inherited from [lava::no_copy_no_move](/_doxybook/Classes/structlava_1_1no__copy__no__move.md)**

|                | Name           |
| -------------- | -------------- |
| | **[no_copy_no_move](/_doxybook/Classes/structlava_1_1no__copy__no__move.md#function-no-copy-no-move)**() =default<br>Construct a new object.  |
| | **[no_copy_no_move](/_doxybook/Classes/structlava_1_1no__copy__no__move.md#function-no-copy-no-move)**([no_copy_no_move](/_doxybook/Classes/structlava_1_1no__copy__no__move.md) const & ) =delete<br>No copy.  |
| void | **[operator=](/_doxybook/Classes/structlava_1_1no__copy__no__move.md#function-operator=)**([no_copy_no_move](/_doxybook/Classes/structlava_1_1no__copy__no__move.md) const & ) =delete<br>No move.  |

**Public Functions inherited from [lava::interface](/_doxybook/Classes/structlava_1_1interface.md)**

|                | Name           |
| -------------- | -------------- |
| virtual | **[~interface](/_doxybook/Classes/structlava_1_1interface.md#function-~interface)**() =default<br>Destroy the interface.  |


## Public Types Documentation

### using s_ptr

```cpp
using lava::command::s_ptr =  std::shared_ptr<command>;
```

Shared pointer to command. 

### using c_ptr

```cpp
using lava::command::c_ptr =  command const*;
```

Const pointer to command. 

### using s_map

```cpp
using lava::command::s_map =  std::map<id, s_ptr>;
```

Map of commands. 

### using c_list

```cpp
using lava::command::c_list =  std::vector<c_ptr>;
```

List of commands. 

### using process_func

```cpp
using lava::command::process_func =  std::function<void(VkCommandBuffer)>;
```

Command process function. 

## Public Functions Documentation

### function make

```cpp
static inline s_ptr make()
```

Make a new command. 

**Return**: [s_ptr](/_doxybook/Classes/structlava_1_1command.md#using-s-ptr) Shared pointer to command 

### function create

```cpp
bool create(
    device::ptr device,
    index frame_count,
    VkCommandPools command_pools
)
```

Create a new command. 

**Parameters**: 

  * **device** Vulkan device 
  * **frame_count** Number of frames 
  * **command_pools** List of command pools 


**Return**: Create was successful or failed 

### function destroy

```cpp
void destroy(
    device::ptr device,
    VkCommandPools command_pools
)
```

Destroy the command. 

**Parameters**: 

  * **device** Vulkan device 
  * **command_pools** List of command pools 


## Public Attributes Documentation

### variable buffers

```cpp
VkCommandBuffers buffers = {};
```

List of command buffers. 

### variable on_process

```cpp
process_func on_process;
```

Called on command process. 

### variable active

```cpp
bool active = true;
```

Active state. 

-------------------------------

Updated on 2026-02-01 at 18:13:39 +0000