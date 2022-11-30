---
title: lava::descriptor
summary: Descriptor. 

---

# lava::descriptor



Descriptor. 


`#include <descriptor.hpp>`

Inherits from [lava::entity](/_doxybook/Classes/structlava_1_1entity.md), [lava::no_copy_no_move](/_doxybook/Classes/structlava_1_1no__copy__no__move.md), [lava::interface](/_doxybook/Classes/structlava_1_1interface.md)

## Public Classes

|                | Name           |
| -------------- | -------------- |
| struct | **[binding](/_doxybook/Classes/structlava_1_1descriptor_1_1binding.md)** <br>Descriptor binding.  |
| struct | **[pool](/_doxybook/Classes/structlava_1_1descriptor_1_1pool.md)** <br>Descriptor pool.  |

## Public Types

|                | Name           |
| -------------- | -------------- |
| using std::shared_ptr< [descriptor](/_doxybook/Classes/structlava_1_1descriptor.md) > | **[ptr](/_doxybook/Classes/structlava_1_1descriptor.md#using-ptr)** <br>Shared pointer to descriptor.  |
| using std::vector< [ptr](/_doxybook/Classes/structlava_1_1descriptor.md#using-ptr) > | **[list](/_doxybook/Classes/structlava_1_1descriptor.md#using-list)** <br>List of descriptors.  |

## Public Functions

|                | Name           |
| -------------- | -------------- |
| [ptr](/_doxybook/Classes/structlava_1_1descriptor.md#using-ptr) | **[make](/_doxybook/Classes/structlava_1_1descriptor.md#function-make)**()<br>Make a new descriptor.  |
| void | **[add_binding](/_doxybook/Classes/structlava_1_1descriptor.md#function-add-binding)**([index](/_doxybook/Namespaces/namespacelava.md#using-index) binding, VkDescriptorType descriptor_type, VkShaderStageFlags stage_flags)<br>Add binding.  |
| void | **[clear_bindings](/_doxybook/Classes/structlava_1_1descriptor.md#function-clear-bindings)**()<br>Clear bindings.  |
| void | **[add](/_doxybook/Classes/structlava_1_1descriptor.md#function-add)**([binding::ptr](/_doxybook/Classes/structlava_1_1descriptor_1_1binding.md#using-ptr) const & binding)<br>Add binding.  |
| bool | **[create](/_doxybook/Classes/structlava_1_1descriptor.md#function-create)**([device_p](/_doxybook/Namespaces/namespacelava.md#using-device-p) device)<br>Create a new descriptor.  |
| void | **[destroy](/_doxybook/Classes/structlava_1_1descriptor.md#function-destroy)**()<br>Destroy the descriptor.  |
| [ui32](/_doxybook/Namespaces/namespacelava.md#using-ui32) | **[get_binding_count](/_doxybook/Classes/structlava_1_1descriptor.md#function-get-binding-count)**() const<br>Get the binding count.  |
| [binding::list](/_doxybook/Classes/structlava_1_1descriptor_1_1binding.md#using-list) const & | **[get_bindings](/_doxybook/Classes/structlava_1_1descriptor.md#function-get-bindings)**()<br>Get the bindings.  |
| VkDescriptorSetLayout | **[get](/_doxybook/Classes/structlava_1_1descriptor.md#function-get)**() const<br>Get descriptor set layout.  |
| [device_p](/_doxybook/Namespaces/namespacelava.md#using-device-p) | **[get_device](/_doxybook/Classes/structlava_1_1descriptor.md#function-get-device)**()<br>Get the device.  |
| VkDescriptorSet | **[allocate_set](/_doxybook/Classes/structlava_1_1descriptor.md#function-allocate-set)**(VkDescriptorPool pool)<br>Allocate descriptor set.  |
| VkDescriptorSet | **[allocate](/_doxybook/Classes/structlava_1_1descriptor.md#function-allocate)**(VkDescriptorPool pool) |
| bool | **[free_set](/_doxybook/Classes/structlava_1_1descriptor.md#function-free-set)**(VkDescriptorSet & descriptor_set, VkDescriptorPool pool)<br>Free descriptor set.  |
| bool | **[free](/_doxybook/Classes/structlava_1_1descriptor.md#function-free)**(VkDescriptorSet & descriptor_set, VkDescriptorPool pool) |
| [VkDescriptorSets](/_doxybook/Namespaces/namespacelava.md#using-vkdescriptorsets) | **[allocate_sets](/_doxybook/Classes/structlava_1_1descriptor.md#function-allocate-sets)**([ui32](/_doxybook/Namespaces/namespacelava.md#using-ui32) size, VkDescriptorPool pool)<br>Allocate descriptor sets.  |
| [VkDescriptorSets](/_doxybook/Namespaces/namespacelava.md#using-vkdescriptorsets) | **[allocate](/_doxybook/Classes/structlava_1_1descriptor.md#function-allocate)**([ui32](/_doxybook/Namespaces/namespacelava.md#using-ui32) size, VkDescriptorPool pool) |
| bool | **[free_sets](/_doxybook/Classes/structlava_1_1descriptor.md#function-free-sets)**([VkDescriptorSets](/_doxybook/Namespaces/namespacelava.md#using-vkdescriptorsets) & descriptor_sets, VkDescriptorPool pool)<br>Free descriptor sets.  |
| bool | **[free](/_doxybook/Classes/structlava_1_1descriptor.md#function-free)**([VkDescriptorSets](/_doxybook/Namespaces/namespacelava.md#using-vkdescriptorsets) & descriptor_sets, VkDescriptorPool pool) |

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
using lava::descriptor::ptr =  std::shared_ptr<descriptor>;
```

Shared pointer to descriptor. 

### using list

```cpp
using lava::descriptor::list =  std::vector<ptr>;
```

List of descriptors. 

## Public Functions Documentation

### function make

```cpp
static inline ptr make()
```

Make a new descriptor. 

**Return**: ptr Shared pointer to descriptor 

### function add_binding

```cpp
void add_binding(
    index binding,
    VkDescriptorType descriptor_type,
    VkShaderStageFlags stage_flags
)
```

Add binding. 

**Parameters**: 

  * **binding** Index of binding 
  * **descriptor_type** Descriptor type 
  * **stage_flags** Shader stage flags 


### function clear_bindings

```cpp
inline void clear_bindings()
```

Clear bindings. 

### function add

```cpp
inline void add(
    binding::ptr const & binding
)
```

Add binding. 

**Parameters**: 

  * **binding** Descriptor binding 


### function create

```cpp
bool create(
    device_p device
)
```

Create a new descriptor. 

**Parameters**: 

  * **device** Vulkan device 


**Return**: Create was successful or failed 

### function destroy

```cpp
void destroy()
```

Destroy the descriptor. 

### function get_binding_count

```cpp
inline ui32 get_binding_count() const
```

Get the binding count. 

**Return**: ui32 Number of bindings 

### function get_bindings

```cpp
inline binding::list const & get_bindings()
```

Get the bindings. 

**Return**: [binding::list](/_doxybook/Classes/structlava_1_1descriptor_1_1binding.md#using-list) const& List of bindings 

### function get

```cpp
inline VkDescriptorSetLayout get() const
```

Get descriptor set layout. 

**Return**: VkDescriptorSetLayout Vulkan descriptor set layout 

### function get_device

```cpp
inline device_p get_device()
```

Get the device. 

**Return**: device_p Vulkan device 

### function allocate_set

```cpp
VkDescriptorSet allocate_set(
    VkDescriptorPool pool
)
```

Allocate descriptor set. 

**Parameters**: 

  * **pool** Descriptor pool 


**Return**: VkDescriptorSet Descriptor set 

### function allocate

```cpp
inline VkDescriptorSet allocate(
    VkDescriptorPool pool
)
```


**See**: [allocate_set](/_doxybook/Classes/structlava_1_1descriptor.md#function-allocate-set)

### function free_set

```cpp
bool free_set(
    VkDescriptorSet & descriptor_set,
    VkDescriptorPool pool
)
```

Free descriptor set. 

**Parameters**: 

  * **descriptor_set** Descriptor set 
  * **pool** Descriptor pool 


**Return**: Free was successful or failed 

### function free

```cpp
inline bool free(
    VkDescriptorSet & descriptor_set,
    VkDescriptorPool pool
)
```


**See**: [free_set](/_doxybook/Classes/structlava_1_1descriptor.md#function-free-set)

### function allocate_sets

```cpp
VkDescriptorSets allocate_sets(
    ui32 size,
    VkDescriptorPool pool
)
```

Allocate descriptor sets. 

**Parameters**: 

  * **size** Number of sets 
  * **pool** Descriptor pool 


**Return**: VkDescriptorSets List of descriptor sets 

### function allocate

```cpp
inline VkDescriptorSets allocate(
    ui32 size,
    VkDescriptorPool pool
)
```


**See**: [allocate_sets](/_doxybook/Classes/structlava_1_1descriptor.md#function-allocate-sets)

### function free_sets

```cpp
bool free_sets(
    VkDescriptorSets & descriptor_sets,
    VkDescriptorPool pool
)
```

Free descriptor sets. 

**Parameters**: 

  * **descriptor_sets** List of descriptor sets 
  * **pool** Descriptor pool 


**Return**: Free was successful or failed 

### function free

```cpp
inline bool free(
    VkDescriptorSets & descriptor_sets,
    VkDescriptorPool pool
)
```


**See**: [free_sets](/_doxybook/Classes/structlava_1_1descriptor.md#function-free-sets)

-------------------------------

Updated on 2022-11-30 at 01:16:03 +0000