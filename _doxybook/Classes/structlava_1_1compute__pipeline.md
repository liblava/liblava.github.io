---
title: lava::compute_pipeline
summary: Compute pipeline. 

---

# lava::compute_pipeline



Compute pipeline. 


`#include <compute_pipeline.hpp>`

Inherits from [lava::pipeline](/_doxybook/Classes/structlava_1_1pipeline.md), [lava::entity](/_doxybook/Classes/structlava_1_1entity.md), [lava::no_copy_no_move](/_doxybook/Classes/structlava_1_1no__copy__no__move.md), [lava::interface](/_doxybook/Classes/structlava_1_1interface.md)

## Public Types

|                | Name           |
| -------------- | -------------- |
| using std::shared_ptr< [compute_pipeline](/_doxybook/Classes/structlava_1_1compute__pipeline.md) > | **[s_ptr](/_doxybook/Classes/structlava_1_1compute__pipeline.md#using-s-ptr)** <br>Shared pointer to compute pipeline.  |
| using std::map< [id](/_doxybook/Classes/structlava_1_1id.md), [s_ptr](/_doxybook/Classes/structlava_1_1compute__pipeline.md#using-s-ptr) > | **[s_map](/_doxybook/Classes/structlava_1_1compute__pipeline.md#using-s-map)** <br>Map of compute pipelines.  |
| using std::vector< [s_ptr](/_doxybook/Classes/structlava_1_1compute__pipeline.md#using-s-ptr) > | **[s_list](/_doxybook/Classes/structlava_1_1compute__pipeline.md#using-s-list)** <br>List of compute pipelines.  |

## Public Functions

|                | Name           |
| -------------- | -------------- |
| [s_ptr](/_doxybook/Classes/structlava_1_1compute__pipeline.md#using-s-ptr) | **[make](/_doxybook/Classes/structlava_1_1compute__pipeline.md#function-make)**([device::ptr](/_doxybook/Classes/structlava_1_1device.md#using-ptr) device, VkPipelineCache pipeline_cache =0)<br>Make a new compute pipeline.  |
| virtual void | **[bind](/_doxybook/Classes/structlava_1_1compute__pipeline.md#function-bind)**(VkCommandBuffer cmdBuffer) override<br>Bind the pipeline.  |
| bool | **[set_shader_stage](/_doxybook/Classes/structlava_1_1compute__pipeline.md#function-set-shader-stage)**([c_data::ref](/_doxybook/Classes/structlava_1_1c__data.md#using-ref) data, VkShaderStageFlagBits stage)<br>Set shader stage.  |
| void | **[set](/_doxybook/Classes/structlava_1_1compute__pipeline.md#function-set)**(shader_stage::s_ptr const & stage)<br>Set shader stage.  |
| shader_stage::s_ptr const & | **[get_shader_stage](/_doxybook/Classes/structlava_1_1compute__pipeline.md#function-get-shader-stage)**() const<br>Get the shader stage.  |
| void | **[copy_to](/_doxybook/Classes/structlava_1_1compute__pipeline.md#function-copy-to)**([compute_pipeline](/_doxybook/Classes/structlava_1_1compute__pipeline.md) * target) const<br>Copy configuration to target pipeline.  |
| void | **[copy_from](/_doxybook/Classes/structlava_1_1compute__pipeline.md#function-copy-from)**([s_ptr](/_doxybook/Classes/structlava_1_1compute__pipeline.md#using-s-ptr) const & source)<br>Copy configuration from source.  |
| | **[pipeline](/_doxybook/Classes/structlava_1_1compute__pipeline.md#function-pipeline)**([device::ptr](/_doxybook/Classes/structlava_1_1device.md#using-ptr) device, VkPipelineCache pipeline_cache =0)<br>Pipeline constructors.  |

## Additional inherited members

**Public Classes inherited from [lava::pipeline](/_doxybook/Classes/structlava_1_1pipeline.md)**

|                | Name           |
| -------------- | -------------- |
| struct | **[shader_stage](/_doxybook/Classes/structlava_1_1pipeline_1_1shader__stage.md)** <br>Shader stage.  |

**Public Types inherited from [lava::pipeline](/_doxybook/Classes/structlava_1_1pipeline.md)**

|                | Name           |
| -------------- | -------------- |
| using std::function< void(VkCommandBuffer)> | **[process_func](/_doxybook/Classes/structlava_1_1pipeline.md#using-process-func)** <br>Pipeline process function.  |

**Public Functions inherited from [lava::pipeline](/_doxybook/Classes/structlava_1_1pipeline.md)**

|                | Name           |
| -------------- | -------------- |
| | **[~pipeline](/_doxybook/Classes/structlava_1_1pipeline.md#function-~pipeline)**() override<br>Destroy the pipeline.  |
| bool | **[create](/_doxybook/Classes/structlava_1_1pipeline.md#function-create)**()<br>Create a new pipeline.  |
| void | **[destroy](/_doxybook/Classes/structlava_1_1pipeline.md#function-destroy)**()<br>Destroy the pipeline.  |
| void | **[set_active](/_doxybook/Classes/structlava_1_1pipeline.md#function-set-active)**(bool value =true)<br>Set pipeline active.  |
| bool | **[activated](/_doxybook/Classes/structlava_1_1pipeline.md#function-activated)**() const<br>Check if pipeline is active.  |
| void | **[toggle](/_doxybook/Classes/structlava_1_1pipeline.md#function-toggle)**()<br>Toggle activation.  |
| void | **[set_auto_bind](/_doxybook/Classes/structlava_1_1pipeline.md#function-set-auto-bind)**(bool value =true)<br>Set auto bind.  |
| bool | **[auto_bind](/_doxybook/Classes/structlava_1_1pipeline.md#function-auto-bind)**() const<br>Check if auto bind is enabled.  |
| bool | **[ready](/_doxybook/Classes/structlava_1_1pipeline.md#function-ready)**() const<br>Check if pipeline is ready.  |
| VkPipeline | **[get](/_doxybook/Classes/structlava_1_1pipeline.md#function-get)**() const<br>Get the pipeline.  |
| [device::ptr](/_doxybook/Classes/structlava_1_1device.md#using-ptr) | **[get_device](/_doxybook/Classes/structlava_1_1pipeline.md#function-get-device)**()<br>Get the device.  |
| [pipeline_layout::s_ptr](/_doxybook/Classes/structlava_1_1pipeline__layout.md#using-s-ptr) | **[get_layout](/_doxybook/Classes/structlava_1_1pipeline.md#function-get-layout)**() const<br>Get the layout.  |
| void | **[set_layout](/_doxybook/Classes/structlava_1_1pipeline.md#function-set-layout)**([pipeline_layout::s_ptr](/_doxybook/Classes/structlava_1_1pipeline__layout.md#using-s-ptr) const & value)<br>Set the layout.  |

**Public Attributes inherited from [lava::pipeline](/_doxybook/Classes/structlava_1_1pipeline.md)**

|                | Name           |
| -------------- | -------------- |
| [process_func](/_doxybook/Classes/structlava_1_1pipeline.md#using-process-func) | **[on_process](/_doxybook/Classes/structlava_1_1pipeline.md#variable-on-process)** <br>Called on pipeline process.  |

**Protected Attributes inherited from [lava::pipeline](/_doxybook/Classes/structlava_1_1pipeline.md)**

|                | Name           |
| -------------- | -------------- |
| [device::ptr](/_doxybook/Classes/structlava_1_1device.md#using-ptr) | **[m_device](/_doxybook/Classes/structlava_1_1pipeline.md#variable-m-device)** <br>Vulkan device.  |
| VkPipeline | **[m_vk_pipeline](/_doxybook/Classes/structlava_1_1pipeline.md#variable-m-vk-pipeline)** <br>Vulkan pipeline.  |
| VkPipelineCache | **[m_pipeline_cache](/_doxybook/Classes/structlava_1_1pipeline.md#variable-m-pipeline-cache)** <br>Vulkan pipeline cache.  |
| [pipeline_layout::s_ptr](/_doxybook/Classes/structlava_1_1pipeline__layout.md#using-s-ptr) | **[m_layout](/_doxybook/Classes/structlava_1_1pipeline.md#variable-m-layout)** <br>Pipeline layout.  |

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
using lava::compute_pipeline::s_ptr =  std::shared_ptr<compute_pipeline>;
```

Shared pointer to compute pipeline. 

### using s_map

```cpp
using lava::compute_pipeline::s_map =  std::map<id, s_ptr>;
```

Map of compute pipelines. 

### using s_list

```cpp
using lava::compute_pipeline::s_list =  std::vector<s_ptr>;
```

List of compute pipelines. 

## Public Functions Documentation

### function make

```cpp
static inline s_ptr make(
    device::ptr device,
    VkPipelineCache pipeline_cache =0
)
```

Make a new compute pipeline. 

**Parameters**: 

  * **device** Vulkan device 
  * **pipeline_cache** Pipeline cache 


**Return**: [s_ptr](/_doxybook/Classes/structlava_1_1compute__pipeline.md#using-s-ptr) Shared pointer to compute pipeline 

### function bind

```cpp
virtual void bind(
    VkCommandBuffer cmdBuffer
) override
```

Bind the pipeline. 

**Parameters**: 

  * **cmdBuffer** Command buffer 


**Reimplements**: [lava::pipeline::bind](/_doxybook/Classes/structlava_1_1pipeline.md#function-bind)


### function set_shader_stage

```cpp
bool set_shader_stage(
    c_data::ref data,
    VkShaderStageFlagBits stage
)
```

Set shader stage. 

**Parameters**: 

  * **data** Shader data 
  * **stage** Shader stage flag bits 


**Return**: Set was successful or failed 

### function set

```cpp
inline void set(
    shader_stage::s_ptr const & stage
)
```

Set shader stage. 

**Parameters**: 

  * **stage** Shader state 


### function get_shader_stage

```cpp
inline shader_stage::s_ptr const & get_shader_stage() const
```

Get the shader stage. 

**Return**: shader_stage::s_ptr const& Shader state 

### function copy_to

```cpp
void copy_to(
    compute_pipeline * target
) const
```

Copy configuration to target pipeline. 

**Parameters**: 

  * **target** Compute pipeline 


### function copy_from

```cpp
inline void copy_from(
    s_ptr const & source
)
```

Copy configuration from source. 

**Parameters**: 

  * **source** Compute pipeline 


### function pipeline

```cpp
explicit pipeline(
    device::ptr device,
    VkPipelineCache pipeline_cache =0
)
```

Pipeline constructors. 

-------------------------------

Updated on 2026-02-01 at 18:13:39 +0000