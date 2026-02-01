---
title: lava::pipeline::shader_stage
summary: Shader stage. 

---

# lava::pipeline::shader_stage



Shader stage. 


`#include <pipeline.hpp>`

## Public Types

|                | Name           |
| -------------- | -------------- |
| using std::shared_ptr< [shader_stage](/_doxybook/Classes/structlava_1_1pipeline_1_1shader__stage.md) > | **[s_ptr](/_doxybook/Classes/structlava_1_1pipeline_1_1shader__stage.md#using-s-ptr)** <br>Shared pointer to shader stage.  |
| using std::vector< [s_ptr](/_doxybook/Classes/structlava_1_1pipeline_1_1shader__stage.md#using-s-ptr) > | **[s_list](/_doxybook/Classes/structlava_1_1pipeline_1_1shader__stage.md#using-s-list)** <br>List of shader stages.  |

## Public Functions

|                | Name           |
| -------------- | -------------- |
| [s_ptr](/_doxybook/Classes/structlava_1_1pipeline_1_1shader__stage.md#using-s-ptr) | **[make](/_doxybook/Classes/structlava_1_1pipeline_1_1shader__stage.md#function-make)**(VkShaderStageFlagBits stage)<br>Make a new pipline shader stage.  |
| | **[shader_stage](/_doxybook/Classes/structlava_1_1pipeline_1_1shader__stage.md#function-shader-stage)**()<br>Construct a new shader stage.  |
| | **[~shader_stage](/_doxybook/Classes/structlava_1_1pipeline_1_1shader__stage.md#function-~shader-stage)**()<br>Destroy the shader stage.  |
| void | **[set_stage](/_doxybook/Classes/structlava_1_1pipeline_1_1shader__stage.md#function-set-stage)**(VkShaderStageFlagBits stage)<br>Set the stage.  |
| void | **[add_specialization_entry](/_doxybook/Classes/structlava_1_1pipeline_1_1shader__stage.md#function-add-specialization-entry)**(VkSpecializationMapEntry const & specialization)<br>Add specialization entry.  |
| bool | **[create](/_doxybook/Classes/structlava_1_1pipeline_1_1shader__stage.md#function-create)**([device::ptr](/_doxybook/Classes/structlava_1_1device.md#using-ptr) device, [c_data::ref](/_doxybook/Classes/structlava_1_1c__data.md#using-ref) shader_data, [c_data::ref](/_doxybook/Classes/structlava_1_1c__data.md#using-ref) specialization_data =[data](/_doxybook/Classes/structlava_1_1data.md)())<br>Create a new shader stage.  |
| void | **[destroy](/_doxybook/Classes/structlava_1_1pipeline_1_1shader__stage.md#function-destroy)**()<br>Destroy the shader stage.  |
| VkPipelineShaderStageCreateInfo const & | **[get_create_info](/_doxybook/Classes/structlava_1_1pipeline_1_1shader__stage.md#function-get-create-info)**() const<br>Get the create info.  |

## Public Types Documentation

### using s_ptr

```cpp
using lava::pipeline::shader_stage::s_ptr =  std::shared_ptr<shader_stage>;
```

Shared pointer to shader stage. 

### using s_list

```cpp
using lava::pipeline::shader_stage::s_list =  std::vector<s_ptr>;
```

List of shader stages. 

## Public Functions Documentation

### function make

```cpp
static inline s_ptr make(
    VkShaderStageFlagBits stage
)
```

Make a new pipline shader stage. 

**Parameters**: 

  * **stage** Shader stage flag bits 


**Return**: [s_ptr](/_doxybook/Classes/structlava_1_1pipeline_1_1shader__stage.md#using-s-ptr) Shared pointer to shader stage 

### function shader_stage

```cpp
explicit shader_stage()
```

Construct a new shader stage. 

### function ~shader_stage

```cpp
~shader_stage()
```

Destroy the shader stage. 

### function set_stage

```cpp
inline void set_stage(
    VkShaderStageFlagBits stage
)
```

Set the stage. 

**Parameters**: 

  * **stage** Shader stage flag bits 


### function add_specialization_entry

```cpp
void add_specialization_entry(
    VkSpecializationMapEntry const & specialization
)
```

Add specialization entry. 

**Parameters**: 

  * **specialization** Specialization map entry 


### function create

```cpp
bool create(
    device::ptr device,
    c_data::ref shader_data,
    c_data::ref specialization_data =data()
)
```

Create a new shader stage. 

**Parameters**: 

  * **device** Vulkan device 
  * **shader_data** Shader data 
  * **specialization_data** Specialization data 


**Return**: Create was successful or failed 

### function destroy

```cpp
void destroy()
```

Destroy the shader stage. 

### function get_create_info

```cpp
inline VkPipelineShaderStageCreateInfo const & get_create_info() const
```

Get the create info. 

**Return**: VkPipelineShaderStageCreateInfo const& Pipeline shader stage create information 

-------------------------------

Updated on 2026-02-01 at 18:13:39 +0000