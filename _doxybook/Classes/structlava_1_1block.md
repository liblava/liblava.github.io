---
title: lava::block
summary: Block of commands. 

---

# lava::block



Block of commands. 


`#include <block.hpp>`

Inherits from [lava::entity](/_doxybook/Classes/structlava_1_1entity.md), [lava::no_copy_no_move](/_doxybook/Classes/structlava_1_1no__copy__no__move.md), [lava::interface](/_doxybook/Classes/structlava_1_1interface.md)

## Public Types

|                | Name           |
| -------------- | -------------- |
| using std::shared_ptr< [block](/_doxybook/Classes/structlava_1_1block.md) > | **[ptr](/_doxybook/Classes/structlava_1_1block.md#using-ptr)** <br>Shared pointer to block.  |
| using [command](/_doxybook/Classes/structlava_1_1command.md)[const](/_doxybook/Classes/structlava_1_1block.md#using-map)  * | **[cptr](/_doxybook/Classes/structlava_1_1block.md#using-cptr)** <br>Const pointer to block.  |
| using std::map< [id](/_doxybook/Classes/structlava_1_1id.md), [ptr](/_doxybook/Classes/structlava_1_1block.md#using-ptr) > | **[map](/_doxybook/Classes/structlava_1_1block.md#using-map)** <br>Map of blocks.  |
| using std::vector< [cptr](/_doxybook/Classes/structlava_1_1block.md#using-cptr) > | **[clist](/_doxybook/Classes/structlava_1_1block.md#using-clist)** <br>List of blocks.  |

## Public Functions

|                | Name           |
| -------------- | -------------- |
| [ptr](/_doxybook/Classes/structlava_1_1block.md#using-ptr) | **[make](/_doxybook/Classes/structlava_1_1block.md#function-make)**()<br>Make a new block.  |
| | **[~block](/_doxybook/Classes/structlava_1_1block.md#function-~block)**()<br>Destroy the block.  |
| [bool](/_doxybook/Classes/structlava_1_1block.md#using-map) | **[create](/_doxybook/Classes/structlava_1_1block.md#function-create)**([device_p](/_doxybook/Namespaces/namespacelava.md#using-device-p) device, [index](/_doxybook/Namespaces/namespacelava.md#using-index) frame_count, [index](/_doxybook/Namespaces/namespacelava.md#using-index) queue_family)<br>Create a new block.  |
| [void](/_doxybook/Classes/structlava_1_1block.md#using-map) | **[destroy](/_doxybook/Classes/structlava_1_1block.md#function-destroy)**()<br>Destroy the block.  |
| [index](/_doxybook/Namespaces/namespacelava.md#using-index) | **[get_frame_count](/_doxybook/Classes/structlava_1_1block.md#function-get-frame-count)**() const<br>Get the frame count.  |
| [id](/_doxybook/Classes/structlava_1_1id.md) | **[add_cmd](/_doxybook/Classes/structlava_1_1block.md#function-add-cmd)**([command::process_func](/_doxybook/Classes/structlava_1_1command.md#using-process-func) func, [bool](/_doxybook/Classes/structlava_1_1block.md#using-map) active =[true](/_doxybook/Classes/structlava_1_1block.md#using-map)) |
| [id](/_doxybook/Classes/structlava_1_1id.md) | **[add_command](/_doxybook/Classes/structlava_1_1block.md#function-add-command)**([command::process_func](/_doxybook/Classes/structlava_1_1command.md#using-process-func) func, [bool](/_doxybook/Classes/structlava_1_1block.md#using-map) active =[true](/_doxybook/Classes/structlava_1_1block.md#using-map))<br>Add a command.  |
| [void](/_doxybook/Classes/structlava_1_1block.md#using-map) | **[remove_cmd](/_doxybook/Classes/structlava_1_1block.md#function-remove-cmd)**([id::ref](/_doxybook/Classes/structlava_1_1id.md#using-ref) cmd_id) |
| [void](/_doxybook/Classes/structlava_1_1block.md#using-map) | **[remove_command](/_doxybook/Classes/structlava_1_1block.md#function-remove-command)**([id::ref](/_doxybook/Classes/structlava_1_1id.md#using-ref) cmd_id)<br>Remove the command.  |
| [bool](/_doxybook/Classes/structlava_1_1block.md#using-map) | **[process](/_doxybook/Classes/structlava_1_1block.md#function-process)**([index](/_doxybook/Namespaces/namespacelava.md#using-index) frame)<br>Process the block.  |
| [index](/_doxybook/Namespaces/namespacelava.md#using-index) | **[get_current_frame](/_doxybook/Classes/structlava_1_1block.md#function-get-current-frame)**() const<br>Get the current frame.  |
| [VkCommandBuffer](/_doxybook/Classes/structlava_1_1block.md#using-map) | **[get_command_buffer](/_doxybook/Classes/structlava_1_1block.md#function-get-command-buffer)**([id::ref](/_doxybook/Classes/structlava_1_1id.md#using-ref) cmd_id) const<br>Get the command buffer.  |
| [VkCommandBuffer](/_doxybook/Classes/structlava_1_1block.md#using-map) | **[get_command_buffer](/_doxybook/Classes/structlava_1_1block.md#function-get-command-buffer)**([id::ref](/_doxybook/Classes/structlava_1_1id.md#using-ref) cmd_id, [index](/_doxybook/Namespaces/namespacelava.md#using-index) frame) const<br>Get the command buffer.  |
| [VkCommandBuffers](/_doxybook/Namespaces/namespacelava.md#using-vkcommandbuffers) | **[collect_buffers](/_doxybook/Classes/structlava_1_1block.md#function-collect-buffers)**()<br>Collect the buffers.  |
| [command::map](/_doxybook/Classes/structlava_1_1command.md#using-map)[const](/_doxybook/Classes/structlava_1_1block.md#using-map) & | **[get_commands](/_doxybook/Classes/structlava_1_1block.md#function-get-commands)**() const<br>Get the commands.  |
| [command::clist](/_doxybook/Classes/structlava_1_1command.md#using-clist)[const](/_doxybook/Classes/structlava_1_1block.md#using-map) & | **[get_cmd_order](/_doxybook/Classes/structlava_1_1block.md#function-get-cmd-order)**() const<br>Get the cmd order.  |
| [bool](/_doxybook/Classes/structlava_1_1block.md#using-map) | **[activated](/_doxybook/Classes/structlava_1_1block.md#function-activated)**([id::ref](/_doxybook/Classes/structlava_1_1id.md#using-ref) cmd_id)<br>Check if command is activated.  |
| [bool](/_doxybook/Classes/structlava_1_1block.md#using-map) | **[set_active](/_doxybook/Classes/structlava_1_1block.md#function-set-active)**([id::ref](/_doxybook/Classes/structlava_1_1id.md#using-ref) cmd_id, [bool](/_doxybook/Classes/structlava_1_1block.md#using-map) active =[true](/_doxybook/Classes/structlava_1_1block.md#using-map))<br>Set the command active.  |
| [device_p](/_doxybook/Namespaces/namespacelava.md#using-device-p) | **[get_device](/_doxybook/Classes/structlava_1_1block.md#function-get-device)**()<br>Get the device.  |

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

### using ptr

```cpp
using lava::block::ptr =  std::shared_ptr<block>;
```

Shared pointer to block. 

### using cptr

```cpp
using lava::block::cptr =  command const*;
```

Const pointer to block. 

### using map

```cpp
using lava::block::map =  std::map<id, ptr>;
```

Map of blocks. 

### using clist

```cpp
using lava::block::clist =  std::vector<cptr>;
```

List of blocks. 

## Public Functions Documentation

### function make

```cpp
static inline ptr make()
```

Make a new block. 

**Return**: ptr Shared pointer to block 

### function ~block

```cpp
inline ~block()
```

Destroy the block. 

### function create

```cpp
bool create(
    device_p device,
    index frame_count,
    index queue_family
)
```

Create a new block. 

**Parameters**: 

  * **device** Vulkan device 
  * **frame_count** Number of frames 
  * **queue_family** Queue family index 


**Return**: Create was successful or failed 

### function destroy

```cpp
void destroy()
```

Destroy the block. 

### function get_frame_count

```cpp
inline index get_frame_count() const
```

Get the frame count. 

**Return**: index Number of frames 

### function add_cmd

```cpp
id add_cmd(
    command::process_func func,
    bool active =true
)
```


**See**: [add_command](/_doxybook/Classes/structlava_1_1block.md#function-add-command)

### function add_command

```cpp
inline id add_command(
    command::process_func func,
    bool active =true
)
```

Add a command. 

**Parameters**: 

  * **func** Command function 
  * **active** Active state 


**Return**: id Command id 

### function remove_cmd

```cpp
void remove_cmd(
    id::ref cmd_id
)
```


**See**: [remove_command](/_doxybook/Classes/structlava_1_1block.md#function-remove-command)

### function remove_command

```cpp
inline void remove_command(
    id::ref cmd_id
)
```

Remove the command. 

**Parameters**: 

  * **cmd_id** Command id 


### function process

```cpp
bool process(
    index frame
)
```

Process the block. 

**Parameters**: 

  * **frame** Frame index 


**Return**: Process was successful or aborted 

### function get_current_frame

```cpp
inline index get_current_frame() const
```

Get the current frame. 

**Return**: index Current frame 

### function get_command_buffer

```cpp
inline VkCommandBuffer get_command_buffer(
    id::ref cmd_id
) const
```

Get the command buffer. 

**Parameters**: 

  * **cmd_id** Command id 


**Return**: VkCommandBuffer Vulkan command buffer 

### function get_command_buffer

```cpp
inline VkCommandBuffer get_command_buffer(
    id::ref cmd_id,
    index frame
) const
```

Get the command buffer. 

**Parameters**: 

  * **cmd_id** Command id 
  * **frame** Frame index 


**Return**: VkCommandBuffer Vulkan command buffer 

### function collect_buffers

```cpp
inline VkCommandBuffers collect_buffers()
```

Collect the buffers. 

**Return**: VkCommandBuffers List of Vulkan command buffers 

### function get_commands

```cpp
inline command::mapconst & get_commands() const
```

Get the commands. 

**Return**: [command::map](/_doxybook/Classes/structlava_1_1command.md#using-map) const& Map of commands 

### function get_cmd_order

```cpp
inline command::clistconst & get_cmd_order() const
```

Get the cmd order. 

**Return**: command::list const& List of commands 

### function activated

```cpp
bool activated(
    id::ref cmd_id
)
```

Check if command is activated. 

**Parameters**: 

  * **cmd_id** Command id 


**Return**: Command is active or not 

### function set_active

```cpp
bool set_active(
    id::ref cmd_id,
    bool active =true
)
```

Set the command active. 

**Parameters**: 

  * **cmd_id** Command id 
  * **active** Active state 


**Return**: Set was successful or failed 

### function get_device

```cpp
inline device_p get_device()
```

Get the device. 

**Return**: device_p Vulkan device 

-------------------------------

Updated on 2024-03-22 at 21:51:37 +0000