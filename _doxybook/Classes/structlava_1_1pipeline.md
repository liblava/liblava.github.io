---
title: lava::pipeline
summary: Pipeline. 

---

# lava::pipeline



Pipeline. 


`#include <pipeline.hpp>`

Inherits from [lava::entity](/_doxybook/Classes/structlava_1_1entity.md), [lava::no_copy_no_move](/_doxybook/Classes/structlava_1_1no__copy__no__move.md), [lava::interface](/_doxybook/Classes/structlava_1_1interface.md)

Inherited by [lava::compute_pipeline](/_doxybook/Classes/structlava_1_1compute__pipeline.md), [lava::render_pipeline](/_doxybook/Classes/structlava_1_1render__pipeline.md)

## Public Classes

|                | Name           |
| -------------- | -------------- |
| struct | **[shader_stage](/_doxybook/Classes/structlava_1_1pipeline_1_1shader__stage.md)** <br>Shader stage.  |

## Public Types

|                | Name           |
| -------------- | -------------- |
| using std::shared_ptr< [pipeline](/_doxybook/Classes/structlava_1_1pipeline.md) > | **[ptr](/_doxybook/Classes/structlava_1_1pipeline.md#using-ptr)** <br>Shared pointer to pipeline.  |
| using std::vector< [ptr](/_doxybook/Classes/structlava_1_1pipeline.md#using-ptr) > | **[list](/_doxybook/Classes/structlava_1_1pipeline.md#using-list)** <br>List of pipelines.  |
| using std::function< void(VkCommandBuffer)> | **[process_func](/_doxybook/Classes/structlava_1_1pipeline.md#using-process-func)** <br>Pipeline process function.  |

## Public Functions

|                | Name           |
| -------------- | -------------- |
| | **[pipeline](/_doxybook/Classes/structlava_1_1pipeline.md#function-pipeline)**([device_p](/_doxybook/Namespaces/namespacelava.md#using-device-p) device, VkPipelineCache pipeline_cache =0)<br>Construct a new pipeline.  |
| | **[~pipeline](/_doxybook/Classes/structlava_1_1pipeline.md#function-~pipeline)**() override<br>Destroy the pipeline.  |
| bool | **[create](/_doxybook/Classes/structlava_1_1pipeline.md#function-create)**()<br>Create a new pipeline.  |
| void | **[destroy](/_doxybook/Classes/structlava_1_1pipeline.md#function-destroy)**()<br>Destroy the pipeline.  |
| virtual void | **[bind](/_doxybook/Classes/structlava_1_1pipeline.md#function-bind)**(VkCommandBuffer cmd_buf) =0<br>Bind the pipeline.  |
| void | **[set_active](/_doxybook/Classes/structlava_1_1pipeline.md#function-set-active)**(bool value =true)<br>Set pipeline active.  |
| bool | **[activated](/_doxybook/Classes/structlava_1_1pipeline.md#function-activated)**() const<br>Check if pipeline is active.  |
| void | **[toggle](/_doxybook/Classes/structlava_1_1pipeline.md#function-toggle)**()<br>Toggle activation.  |
| void | **[set_auto_bind](/_doxybook/Classes/structlava_1_1pipeline.md#function-set-auto-bind)**(bool value =true)<br>Set auto bind.  |
| bool | **[auto_bind](/_doxybook/Classes/structlava_1_1pipeline.md#function-auto-bind)**() const<br>Check if auto bind is enabled.  |
| bool | **[ready](/_doxybook/Classes/structlava_1_1pipeline.md#function-ready)**() const<br>Check if pipeline is ready.  |
| VkPipeline | **[get](/_doxybook/Classes/structlava_1_1pipeline.md#function-get)**() const<br>Get the pipeline.  |
| [device_p](/_doxybook/Namespaces/namespacelava.md#using-device-p) | **[get_device](/_doxybook/Classes/structlava_1_1pipeline.md#function-get-device)**()<br>Get the device.  |
| [pipeline_layout::ptr](/_doxybook/Classes/structlava_1_1pipeline__layout.md#using-ptr) | **[get_layout](/_doxybook/Classes/structlava_1_1pipeline.md#function-get-layout)**() const<br>Get the layout.  |
| void | **[set_layout](/_doxybook/Classes/structlava_1_1pipeline.md#function-set-layout)**([pipeline_layout::ptr](/_doxybook/Classes/structlava_1_1pipeline__layout.md#using-ptr) const & value)<br>Set the layout.  |

## Protected Functions

|                | Name           |
| -------------- | -------------- |
| virtual bool | **[setup](/_doxybook/Classes/structlava_1_1pipeline.md#function-setup)**() =0<br>Set up the pipeline.  |
| virtual void | **[teardown](/_doxybook/Classes/structlava_1_1pipeline.md#function-teardown)**() =0<br>Tear down the pipeline.  |

## Public Attributes

|                | Name           |
| -------------- | -------------- |
| [process_func](/_doxybook/Classes/structlava_1_1pipeline.md#using-process-func) | **[on_process](/_doxybook/Classes/structlava_1_1pipeline.md#variable-on-process)** <br>Called on pipeline process.  |

## Protected Attributes

|                | Name           |
| -------------- | -------------- |
| [device_p](/_doxybook/Namespaces/namespacelava.md#using-device-p) | **[device](/_doxybook/Classes/structlava_1_1pipeline.md#variable-device)** <br>Vulkan device.  |
| VkPipeline | **[vk_pipeline](/_doxybook/Classes/structlava_1_1pipeline.md#variable-vk-pipeline)** <br>Vulkan pipeline.  |
| VkPipelineCache | **[pipeline_cache](/_doxybook/Classes/structlava_1_1pipeline.md#variable-pipeline-cache)** <br>Vulkan pipeline cache.  |
| [pipeline_layout::ptr](/_doxybook/Classes/structlava_1_1pipeline__layout.md#using-ptr) | **[layout](/_doxybook/Classes/structlava_1_1pipeline.md#variable-layout)** <br>Pipeline layout.  |

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
using lava::pipeline::ptr =  std::shared_ptr<pipeline>;
```

Shared pointer to pipeline. 

### using list

```cpp
using lava::pipeline::list =  std::vector<ptr>;
```

List of pipelines. 

### using process_func

```cpp
using lava::pipeline::process_func =  std::function<void(VkCommandBuffer)>;
```

Pipeline process function. 

## Public Functions Documentation

### function pipeline

```cpp
explicit pipeline(
    device_p device,
    VkPipelineCache pipeline_cache =0
)
```

Construct a new pipeline. 

**Parameters**: 

  * **device** Vulkan device 
  * **pipeline_cache** Pipeline cache 


### function ~pipeline

```cpp
~pipeline() override
```

Destroy the pipeline. 

### function create

```cpp
bool create()
```

Create a new pipeline. 

**Return**: Create was successful or failed 

### function destroy

```cpp
void destroy()
```

Destroy the pipeline. 

### function bind

```cpp
virtual void bind(
    VkCommandBuffer cmd_buf
) =0
```

Bind the pipeline. 

**Parameters**: 

  * **cmd_buf** Command buffer 


**Reimplemented by**: [lava::render_pipeline::bind](/_doxybook/Classes/structlava_1_1render__pipeline.md#function-bind), [lava::compute_pipeline::bind](/_doxybook/Classes/structlava_1_1compute__pipeline.md#function-bind)


### function set_active

```cpp
inline void set_active(
    bool value =true
)
```

Set pipeline active. 

**Parameters**: 

  * **value** Active state 


### function activated

```cpp
inline bool activated() const
```

Check if pipeline is active. 

**Return**: Pipeline is active or note 

### function toggle

```cpp
inline void toggle()
```

Toggle activation. 

### function set_auto_bind

```cpp
inline void set_auto_bind(
    bool value =true
)
```

Set auto bind. 

**Parameters**: 

  * **value** Enable state 


### function auto_bind

```cpp
inline bool auto_bind() const
```

Check if auto bind is enabled. 

**Return**: Auto bind is enabled or not 

### function ready

```cpp
inline bool ready() const
```

Check if pipeline is ready. 

**Return**: Pipeline is ready or not 

### function get

```cpp
inline VkPipeline get() const
```

Get the pipeline. 

**Return**: VkPipeline Vulkan pipeline 

### function get_device

```cpp
inline device_p get_device()
```

Get the device. 

**Return**: device_p Vulkan device 

### function get_layout

```cpp
inline pipeline_layout::ptr get_layout() const
```

Get the layout. 

**Return**: [pipeline_layout::ptr](/_doxybook/Classes/structlava_1_1pipeline__layout.md#using-ptr) Pipeline layout 

### function set_layout

```cpp
inline void set_layout(
    pipeline_layout::ptr const & value
)
```

Set the layout. 

**Parameters**: 

  * **value** Pipeline layout 


## Protected Functions Documentation

### function setup

```cpp
virtual bool setup() =0
```

Set up the pipeline. 

**Return**: Setup was successful or failed 

**Reimplemented by**: [lava::compute_pipeline::setup](/_doxybook/Classes/structlava_1_1compute__pipeline.md#function-setup), [lava::render_pipeline::setup](/_doxybook/Classes/structlava_1_1render__pipeline.md#function-setup)


### function teardown

```cpp
virtual void teardown() =0
```

Tear down the pipeline. 

**Reimplemented by**: [lava::compute_pipeline::teardown](/_doxybook/Classes/structlava_1_1compute__pipeline.md#function-teardown), [lava::render_pipeline::teardown](/_doxybook/Classes/structlava_1_1render__pipeline.md#function-teardown)


## Public Attributes Documentation

### variable on_process

```cpp
process_func on_process;
```

Called on pipeline process. 

## Protected Attributes Documentation

### variable device

```cpp
device_p device = nullptr;
```

Vulkan device. 

### variable vk_pipeline

```cpp
VkPipeline vk_pipeline = VK_NULL_HANDLE;
```

Vulkan pipeline. 

### variable pipeline_cache

```cpp
VkPipelineCache pipeline_cache = VK_NULL_HANDLE;
```

Vulkan pipeline cache. 

### variable layout

```cpp
pipeline_layout::ptr layout;
```

Pipeline layout. 

-------------------------------

Updated on 2024-03-22 at 21:51:38 +0000