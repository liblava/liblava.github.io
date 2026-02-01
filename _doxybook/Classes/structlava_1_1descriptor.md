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
| using std::shared_ptr< [descriptor](/_doxybook/Classes/structlava_1_1descriptor.md) > | **[s_ptr](/_doxybook/Classes/structlava_1_1descriptor.md#using-s-ptr)** <br>Shared pointer to descriptor.  |
| using std::vector< [s_ptr](/_doxybook/Classes/structlava_1_1descriptor.md#using-s-ptr) > | **[s_list](/_doxybook/Classes/structlava_1_1descriptor.md#using-s-list)** <br>List of descriptors.  |

## Public Functions

|                | Name           |
| -------------- | -------------- |
| [s_ptr](/_doxybook/Classes/structlava_1_1descriptor.md#using-s-ptr) | **[make](/_doxybook/Classes/structlava_1_1descriptor.md#function-make)**()<br>Make a new descriptor.  |
| void | **[add_binding](/_doxybook/Classes/structlava_1_1descriptor.md#function-add-binding)**([index](/_doxybook/Namespaces/namespacelava.md#using-index) binding, VkDescriptorType descriptor_type, VkShaderStageFlags stage_flags)<br>Add binding.  |
| void | **[clear_bindings](/_doxybook/Classes/structlava_1_1descriptor.md#function-clear-bindings)**()<br>Clear bindings.  |
| void | **[add](/_doxybook/Classes/structlava_1_1descriptor.md#function-add)**([binding::s_ptr](/_doxybook/Classes/structlava_1_1descriptor_1_1binding.md#using-s-ptr) const & binding)<br>Add binding.  |
| bool | **[create](/_doxybook/Classes/structlava_1_1descriptor.md#function-create)**([device::ptr](/_doxybook/Classes/structlava_1_1device.md#using-ptr) device)<br>Create a new descriptor.  |
| void | **[destroy](/_doxybook/Classes/structlava_1_1descriptor.md#function-destroy)**()<br>Destroy the descriptor.  |
| [ui32](/_doxybook/Namespaces/namespacelava.md#using-ui32) | **[get_binding_count](/_doxybook/Classes/structlava_1_1descriptor.md#function-get-binding-count)**() const<br>Get the binding count.  |
| [binding::s_list](/_doxybook/Classes/structlava_1_1descriptor_1_1binding.md#using-s-list) const & | **[get_bindings](/_doxybook/Classes/structlava_1_1descriptor.md#function-get-bindings)**()<br>Get the bindings.  |
| VkDescriptorSetLayout | **[get](/_doxybook/Classes/structlava_1_1descriptor.md#function-get)**() const<br>Get descriptor set layout.  |
| [device::ptr](/_doxybook/Classes/structlava_1_1device.md#using-ptr) | **[get_device](/_doxybook/Classes/structlava_1_1descriptor.md#function-get-device)**()<br>Get the device.  |
| VkDescriptorSet | **[allocate_set](/_doxybook/Classes/structlava_1_1descriptor.md#function-allocate-set)**(VkDescriptorPool pool)<br>Allocate descriptor set.  |
| VkDescriptorSet | **[allocate](/_doxybook/Classes/structlava_1_1descriptor.md#function-allocate)**(VkDescriptorPool pool) |
| bool | **[deallocate_set](/_doxybook/Classes/structlava_1_1descriptor.md#function-deallocate-set)**(VkDescriptorSet & descriptor_set, VkDescriptorPool pool)<br>Deallocate descriptor set.  |
| bool | **[deallocate](/_doxybook/Classes/structlava_1_1descriptor.md#function-deallocate)**(VkDescriptorSet & descriptor_set, VkDescriptorPool pool) |
| [VkDescriptorSets](/_doxybook/Namespaces/namespacelava.md#using-vkdescriptorsets) | **[allocate_sets](/_doxybook/Classes/structlava_1_1descriptor.md#function-allocate-sets)**([ui32](/_doxybook/Namespaces/namespacelava.md#using-ui32) size, VkDescriptorPool pool)<br>Allocate descriptor sets.  |
| [VkDescriptorSets](/_doxybook/Namespaces/namespacelava.md#using-vkdescriptorsets) | **[allocate](/_doxybook/Classes/structlava_1_1descriptor.md#function-allocate)**([ui32](/_doxybook/Namespaces/namespacelava.md#using-ui32) size, VkDescriptorPool pool) |
| bool | **[deallocate_sets](/_doxybook/Classes/structlava_1_1descriptor.md#function-deallocate-sets)**([VkDescriptorSets](/_doxybook/Namespaces/namespacelava.md#using-vkdescriptorsets) & descriptor_sets, VkDescriptorPool pool)<br>Deallocate descriptor sets.  |
| bool | **[deallocate](/_doxybook/Classes/structlava_1_1descriptor.md#function-deallocate)**([VkDescriptorSets](/_doxybook/Namespaces/namespacelava.md#using-vkdescriptorsets) & descriptor_sets, VkDescriptorPool pool) |

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
using lava::descriptor::s_ptr =  std::shared_ptr<descriptor>;
```

Shared pointer to descriptor. 

### using s_list

```cpp
using lava::descriptor::s_list =  std::vector<s_ptr>;
```

List of descriptors. 

## Public Functions Documentation

### function make

```cpp
static inline s_ptr make()
```

Make a new descriptor. 

**Return**: [s_ptr](/_doxybook/Classes/structlava_1_1descriptor.md#using-s-ptr) Shared pointer to descriptor 

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
    binding::s_ptr const & binding
)
```

Add binding. 

**Parameters**: 

  * **binding** Descriptor binding 


### function create

```cpp
bool create(
    device::ptr device
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

**Return**: [ui32](/_doxybook/Namespaces/namespacelava.md#using-ui32) Number of bindings 

### function get_bindings

```cpp
inline binding::s_list const & get_bindings()
```

Get the bindings. 

**Return**: [binding::s_list](/_doxybook/Classes/structlava_1_1descriptor_1_1binding.md#using-s-list) const& List of bindings 

### function get

```cpp
inline VkDescriptorSetLayout get() const
```

Get descriptor set layout. 

**Return**: VkDescriptorSetLayout Vulkan descriptor set layout 

### function get_device

```cpp
inline device::ptr get_device()
```

Get the device. 

**Return**: [device::ptr](/_doxybook/Classes/structlava_1_1device.md#using-ptr) Vulkan device 

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

### function deallocate_set

```cpp
bool deallocate_set(
    VkDescriptorSet & descriptor_set,
    VkDescriptorPool pool
)
```

Deallocate descriptor set. 

**Parameters**: 

  * **descriptor_set** Descriptor set 
  * **pool** Descriptor pool 


**Return**: Deallocate was successful or failed 

### function deallocate

```cpp
inline bool deallocate(
    VkDescriptorSet & descriptor_set,
    VkDescriptorPool pool
)
```


**See**: [deallocate_set](/_doxybook/Classes/structlava_1_1descriptor.md#function-deallocate-set)

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


**Return**: [VkDescriptorSets](/_doxybook/Namespaces/namespacelava.md#using-vkdescriptorsets) List of descriptor sets 

### function allocate

```cpp
inline VkDescriptorSets allocate(
    ui32 size,
    VkDescriptorPool pool
)
```


**See**: [allocate_sets](/_doxybook/Classes/structlava_1_1descriptor.md#function-allocate-sets)

### function deallocate_sets

```cpp
bool deallocate_sets(
    VkDescriptorSets & descriptor_sets,
    VkDescriptorPool pool
)
```

Deallocate descriptor sets. 

**Parameters**: 

  * **descriptor_sets** List of descriptor sets 
  * **pool** Descriptor pool 


**Return**: Deallocate was successful or failed 

### function deallocate

```cpp
inline bool deallocate(
    VkDescriptorSets & descriptor_sets,
    VkDescriptorPool pool
)
```


**See**: [deallocate_sets](/_doxybook/Classes/structlava_1_1descriptor.md#function-deallocate-sets)

-------------------------------

Updated on 2026-02-01 at 18:13:39 +0000