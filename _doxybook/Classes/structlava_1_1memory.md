---
title: lava::memory
summary: Vulkan memory. 

---

# lava::memory



Vulkan memory. 


`#include <memory.hpp>`

Inherits from [lava::no_copy_no_move](/_doxybook/Classes/structlava_1_1no__copy__no__move.md)

## Public Functions

|                | Name           |
| -------------- | -------------- |
| | **[memory](/_doxybook/Classes/structlava_1_1memory.md#function-memory)**()<br>Construct a new memory.  |
| VkAllocationCallbacks * | **[alloc](/_doxybook/Classes/structlava_1_1memory.md#function-alloc)**()<br>Get allocation callback.  |
| void | **[set_callbacks](/_doxybook/Classes/structlava_1_1memory.md#function-set-callbacks)**(VkAllocationCallbacks const & callbacks)<br>Set the callbacks object.  |
| void | **[set_use_custom_cpu_callbacks](/_doxybook/Classes/structlava_1_1memory.md#function-set-use-custom-cpu-callbacks)**(bool value)<br>Set use custom cpu callbacks.  |
| [memory](/_doxybook/Classes/structlava_1_1memory.md) & | **[instance](/_doxybook/Classes/structlava_1_1memory.md#function-instance)**()<br>Get memory instance.  |

## Additional inherited members

**Public Functions inherited from [lava::no_copy_no_move](/_doxybook/Classes/structlava_1_1no__copy__no__move.md)**

|                | Name           |
| -------------- | -------------- |
| | **[no_copy_no_move](/_doxybook/Classes/structlava_1_1no__copy__no__move.md#function-no-copy-no-move)**() =default<br>Construct a new object.  |
| | **[no_copy_no_move](/_doxybook/Classes/structlava_1_1no__copy__no__move.md#function-no-copy-no-move)**([no_copy_no_move](/_doxybook/Classes/structlava_1_1no__copy__no__move.md) const & ) =delete<br>No copy.  |
| void | **[operator=](/_doxybook/Classes/structlava_1_1no__copy__no__move.md#function-operator=)**([no_copy_no_move](/_doxybook/Classes/structlava_1_1no__copy__no__move.md) const & ) =delete<br>No move.  |


## Public Functions Documentation

### function memory

```cpp
memory()
```

Construct a new memory. 

### function alloc

```cpp
inline VkAllocationCallbacks * alloc()
```

Get allocation callback. 

**Return**: VkAllocationCallbacks* Allocation callbacks 

### function set_callbacks

```cpp
inline void set_callbacks(
    VkAllocationCallbacks const & callbacks
)
```

Set the callbacks object. 

**Parameters**: 

  * **callbacks** Allocation Callbacks 


### function set_use_custom_cpu_callbacks

```cpp
inline void set_use_custom_cpu_callbacks(
    bool value
)
```

Set use custom cpu callbacks. 

**Parameters**: 

  * **value** Value state 


### function instance

```cpp
static inline memory & instance()
```

Get memory instance. 

**Return**: memory& Memory 

-------------------------------

Updated on 2026-02-01 at 18:13:39 +0000