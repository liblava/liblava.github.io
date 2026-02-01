---
title: lava::descriptor::binding
summary: Descriptor binding. 

---

# lava::descriptor::binding



Descriptor binding. 


`#include <descriptor.hpp>`

## Public Types

|                | Name           |
| -------------- | -------------- |
| using std::shared_ptr< [binding](/_doxybook/Classes/structlava_1_1descriptor_1_1binding.md) > | **[s_ptr](/_doxybook/Classes/structlava_1_1descriptor_1_1binding.md#using-s-ptr)** <br>Shared pointer to binding.  |
| using std::vector< [s_ptr](/_doxybook/Classes/structlava_1_1descriptor_1_1binding.md#using-s-ptr) > | **[s_list](/_doxybook/Classes/structlava_1_1descriptor_1_1binding.md#using-s-list)** <br>List of bindings.  |

## Public Functions

|                | Name           |
| -------------- | -------------- |
| [s_ptr](/_doxybook/Classes/structlava_1_1descriptor_1_1binding.md#using-s-ptr) | **[make](/_doxybook/Classes/structlava_1_1descriptor_1_1binding.md#function-make)**([index](/_doxybook/Namespaces/namespacelava.md#using-index) index)<br>Make a new descriptor binding.  |
| | **[binding](/_doxybook/Classes/structlava_1_1descriptor_1_1binding.md#function-binding)**()<br>Construct a new binding.  |
| VkDescriptorSetLayoutBinding const & | **[get](/_doxybook/Classes/structlava_1_1descriptor_1_1binding.md#function-get)**() const<br>Get the Vulkan descriptor set layout binding.  |
| void | **[set](/_doxybook/Classes/structlava_1_1descriptor_1_1binding.md#function-set)**([index](/_doxybook/Namespaces/namespacelava.md#using-index) index)<br>Det the binding index.  |
| void | **[set_type](/_doxybook/Classes/structlava_1_1descriptor_1_1binding.md#function-set-type)**(VkDescriptorType descriptor_type)<br>Set the type.  |
| void | **[set_count](/_doxybook/Classes/structlava_1_1descriptor_1_1binding.md#function-set-count)**([ui32](/_doxybook/Namespaces/namespacelava.md#using-ui32) descriptor_count)<br>Set the count.  |
| void | **[set_stage_flags](/_doxybook/Classes/structlava_1_1descriptor_1_1binding.md#function-set-stage-flags)**(VkShaderStageFlags stage_flags)<br>Set the stage flags.  |
| void | **[set_samplers](/_doxybook/Classes/structlava_1_1descriptor_1_1binding.md#function-set-samplers)**(VkSampler const * immutable_samplers)<br>Set the samplers.  |

## Public Types Documentation

### using s_ptr

```cpp
using lava::descriptor::binding::s_ptr =  std::shared_ptr<binding>;
```

Shared pointer to binding. 

### using s_list

```cpp
using lava::descriptor::binding::s_list =  std::vector<s_ptr>;
```

List of bindings. 

## Public Functions Documentation

### function make

```cpp
static inline s_ptr make(
    index index
)
```

Make a new descriptor binding. 

**Parameters**: 

  * **index** Binding index 


**Return**: ptr Shared pointer to descriptor binding 

### function binding

```cpp
explicit binding()
```

Construct a new binding. 

### function get

```cpp
inline VkDescriptorSetLayoutBinding const & get() const
```

Get the Vulkan descriptor set layout binding. 

**Return**: VkDescriptorSetLayoutBinding const& Vulkan binding 

### function set

```cpp
inline void set(
    index index
)
```

Det the binding index. 

**Parameters**: 

  * **index** Binding index 


### function set_type

```cpp
inline void set_type(
    VkDescriptorType descriptor_type
)
```

Set the type. 

**Parameters**: 

  * **descriptor_type** Descriptor type 


### function set_count

```cpp
inline void set_count(
    ui32 descriptor_count
)
```

Set the count. 

**Parameters**: 

  * **descriptor_count** Descriptor count 


### function set_stage_flags

```cpp
inline void set_stage_flags(
    VkShaderStageFlags stage_flags
)
```

Set the stage flags. 

**Parameters**: 

  * **stage_flags** Shader stage flags 


### function set_samplers

```cpp
inline void set_samplers(
    VkSampler const * immutable_samplers
)
```

Set the samplers. 

**Parameters**: 

  * **immutable_samplers** Pointer to immutable samplers 


-------------------------------

Updated on 2026-02-01 at 18:13:39 +0000