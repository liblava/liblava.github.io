---
title: lava::render_pipeline
summary: Render pipeline (Graphics) 

---

# lava::render_pipeline



Render pipeline (Graphics) 


`#include <render_pipeline.hpp>`

Inherits from [lava::pipeline](/_doxybook/Classes/structlava_1_1pipeline.md), [lava::entity](/_doxybook/Classes/structlava_1_1entity.md), [lava::no_copy_no_move](/_doxybook/Classes/structlava_1_1no__copy__no__move.md), [lava::interface](/_doxybook/Classes/structlava_1_1interface.md)

## Public Classes

|                | Name           |
| -------------- | -------------- |
| struct | **[create_info](/_doxybook/Classes/structlava_1_1render__pipeline_1_1create__info.md)** <br>Render pipeline create information.  |

## Public Types

|                | Name           |
| -------------- | -------------- |
| enum class [index](/_doxybook/Namespaces/namespacelava.md#using-index) | **[sizing_mode](/_doxybook/Classes/structlava_1_1render__pipeline.md#enum-sizing-mode)** { input = 0, absolute, relative}<br>Sizing modes.  |
| using std::shared_ptr< [render_pipeline](/_doxybook/Classes/structlava_1_1render__pipeline.md) > | **[ptr](/_doxybook/Classes/structlava_1_1render__pipeline.md#using-ptr)** <br>Shared pointer to render pipeline.  |
| using std::map< [id](/_doxybook/Classes/structlava_1_1id.md), [ptr](/_doxybook/Classes/structlava_1_1render__pipeline.md#using-ptr) > | **[map](/_doxybook/Classes/structlava_1_1render__pipeline.md#using-map)** <br>Map of render pipelines.  |
| using std::vector< [ptr](/_doxybook/Classes/structlava_1_1render__pipeline.md#using-ptr) > | **[list](/_doxybook/Classes/structlava_1_1render__pipeline.md#using-list)** <br>List of render pipelines.  |
| using std::function< [bool](/_doxybook/Classes/structlava_1_1render__pipeline.md#using-map)([create_info](/_doxybook/Classes/structlava_1_1render__pipeline_1_1create__info.md) &)> | **[create_func](/_doxybook/Classes/structlava_1_1render__pipeline.md#using-create-func)** <br>Create function.  |

## Public Functions

|                | Name           |
| -------------- | -------------- |
| [ptr](/_doxybook/Classes/structlava_1_1render__pipeline.md#using-ptr) | **[make](/_doxybook/Classes/structlava_1_1render__pipeline.md#function-make)**([device_p](/_doxybook/Namespaces/namespacelava.md#using-device-p) device, [VkPipelineCache](/_doxybook/Classes/structlava_1_1render__pipeline.md#using-map) pipeline_cache =0)<br>Make a new render pipeline.  |
| | **[render_pipeline](/_doxybook/Classes/structlava_1_1render__pipeline.md#function-render-pipeline)**([device_p](/_doxybook/Namespaces/namespacelava.md#using-device-p) device, [VkPipelineCache](/_doxybook/Classes/structlava_1_1render__pipeline.md#using-map) pipeline_cache)<br>Construct a new render pipeline.  |
| virtual [void](/_doxybook/Classes/structlava_1_1render__pipeline.md#using-map) | **[bind](/_doxybook/Classes/structlava_1_1render__pipeline.md#function-bind)**([VkCommandBuffer](/_doxybook/Classes/structlava_1_1render__pipeline.md#using-map) cmd_buf) override<br>Bind the pipeline.  |
| [void](/_doxybook/Classes/structlava_1_1render__pipeline.md#using-map) | **[set_viewport_and_scissor](/_doxybook/Classes/structlava_1_1render__pipeline.md#function-set-viewport-and-scissor)**([VkCommandBuffer](/_doxybook/Classes/structlava_1_1render__pipeline.md#using-map) cmd_buf, [uv2](/_doxybook/Namespaces/namespacelava.md#using-uv2) size)<br>Set the viewport and scissor.  |
| [void](/_doxybook/Classes/structlava_1_1render__pipeline.md#using-map) | **[set_render_pass](/_doxybook/Classes/structlava_1_1render__pipeline.md#function-set-render-pass)**([VkRenderPass](/_doxybook/Classes/structlava_1_1render__pipeline.md#using-map) pass)<br>Set the render pass.  |
| [void](/_doxybook/Classes/structlava_1_1render__pipeline.md#using-map) | **[set](/_doxybook/Classes/structlava_1_1render__pipeline.md#function-set)**([VkRenderPass](/_doxybook/Classes/structlava_1_1render__pipeline.md#using-map) pass) |
| [VkRenderPass](/_doxybook/Classes/structlava_1_1render__pipeline.md#using-map) | **[get_render_pass](/_doxybook/Classes/structlava_1_1render__pipeline.md#function-get-render-pass)**() const<br>Get the render pass.  |
| [index](/_doxybook/Namespaces/namespacelava.md#using-index) | **[get_subpass](/_doxybook/Classes/structlava_1_1render__pipeline.md#function-get-subpass)**() const<br>Get the subpass.  |
| [void](/_doxybook/Classes/structlava_1_1render__pipeline.md#using-map) | **[set_subpass](/_doxybook/Classes/structlava_1_1render__pipeline.md#function-set-subpass)**([index](/_doxybook/Namespaces/namespacelava.md#using-index) value)<br>Set the subpass.  |
| [bool](/_doxybook/Classes/structlava_1_1render__pipeline.md#using-map) | **[create](/_doxybook/Classes/structlava_1_1render__pipeline.md#function-create)**([VkRenderPass](/_doxybook/Classes/structlava_1_1render__pipeline.md#using-map) pass)<br>Create a new render pipeline.  |
| [void](/_doxybook/Classes/structlava_1_1render__pipeline.md#using-map) | **[set_vertex_input_binding](/_doxybook/Classes/structlava_1_1render__pipeline.md#function-set-vertex-input-binding)**([VkVertexInputBindingDescription](/_doxybook/Classes/structlava_1_1render__pipeline.md#using-map)[const](/_doxybook/Classes/structlava_1_1render__pipeline.md#using-map) & description)<br>Set the vertex input binding.  |
| [void](/_doxybook/Classes/structlava_1_1render__pipeline.md#using-map) | **[set_vertex_input_bindings](/_doxybook/Classes/structlava_1_1render__pipeline.md#function-set-vertex-input-bindings)**([VkVertexInputBindingDescriptions](/_doxybook/Namespaces/namespacelava.md#using-vkvertexinputbindingdescriptions)[const](/_doxybook/Classes/structlava_1_1render__pipeline.md#using-map) & descriptions)<br>Set the vertex input bindings.  |
| [void](/_doxybook/Classes/structlava_1_1render__pipeline.md#using-map) | **[set_vertex_input_attribute](/_doxybook/Classes/structlava_1_1render__pipeline.md#function-set-vertex-input-attribute)**([VkVertexInputAttributeDescription](/_doxybook/Classes/structlava_1_1render__pipeline.md#using-map)[const](/_doxybook/Classes/structlava_1_1render__pipeline.md#using-map) & attribute)<br>Set the vertex input attribute.  |
| [void](/_doxybook/Classes/structlava_1_1render__pipeline.md#using-map) | **[set_vertex_input_attributes](/_doxybook/Classes/structlava_1_1render__pipeline.md#function-set-vertex-input-attributes)**([VkVertexInputAttributeDescriptions](/_doxybook/Namespaces/namespacelava.md#using-vkvertexinputattributedescriptions)[const](/_doxybook/Classes/structlava_1_1render__pipeline.md#using-map) & attributes)<br>Set the vertex input attributes.  |
| [void](/_doxybook/Classes/structlava_1_1render__pipeline.md#using-map) | **[set_input_topology](/_doxybook/Classes/structlava_1_1render__pipeline.md#function-set-input-topology)**([VkPrimitiveTopology](/_doxybook/Classes/structlava_1_1render__pipeline.md#using-map)[const](/_doxybook/Classes/structlava_1_1render__pipeline.md#using-map) & topology)<br>Set the input assembler's topology.  |
| [void](/_doxybook/Classes/structlava_1_1render__pipeline.md#using-map) | **[set_depth_test_and_write](/_doxybook/Classes/structlava_1_1render__pipeline.md#function-set-depth-test-and-write)**([bool](/_doxybook/Classes/structlava_1_1render__pipeline.md#using-map) test_enable =[true](/_doxybook/Classes/structlava_1_1render__pipeline.md#using-map), [bool](/_doxybook/Classes/structlava_1_1render__pipeline.md#using-map) write_enable =[true](/_doxybook/Classes/structlava_1_1render__pipeline.md#using-map))<br>Set the depth test and write.  |
| [void](/_doxybook/Classes/structlava_1_1render__pipeline.md#using-map) | **[set_depth_compare_op](/_doxybook/Classes/structlava_1_1render__pipeline.md#function-set-depth-compare-op)**([VkCompareOp](/_doxybook/Classes/structlava_1_1render__pipeline.md#using-map) compare_op)<br>Set the depth compare operation.  |
| [void](/_doxybook/Classes/structlava_1_1render__pipeline.md#using-map) | **[set_rasterization_cull_mode](/_doxybook/Classes/structlava_1_1render__pipeline.md#function-set-rasterization-cull-mode)**([VkCullModeFlags](/_doxybook/Classes/structlava_1_1render__pipeline.md#using-map) cull_mode)<br>Set the rasterization cull mode.  |
| [void](/_doxybook/Classes/structlava_1_1render__pipeline.md#using-map) | **[set_rasterization_front_face](/_doxybook/Classes/structlava_1_1render__pipeline.md#function-set-rasterization-front-face)**([VkFrontFace](/_doxybook/Classes/structlava_1_1render__pipeline.md#using-map) front_face)<br>Set the rasterization front face.  |
| [void](/_doxybook/Classes/structlava_1_1render__pipeline.md#using-map) | **[set_rasterization_polygon_mode](/_doxybook/Classes/structlava_1_1render__pipeline.md#function-set-rasterization-polygon-mode)**([VkPolygonMode](/_doxybook/Classes/structlava_1_1render__pipeline.md#using-map) polygon_mode)<br>Set the rasterization polygon mode.  |
| [void](/_doxybook/Classes/structlava_1_1render__pipeline.md#using-map) | **[add_color_blend_attachment](/_doxybook/Classes/structlava_1_1render__pipeline.md#function-add-color-blend-attachment)**([VkPipelineColorBlendAttachmentState](/_doxybook/Classes/structlava_1_1render__pipeline.md#using-map)[const](/_doxybook/Classes/structlava_1_1render__pipeline.md#using-map) & attachment)<br>Add color blend attachment.  |
| [void](/_doxybook/Classes/structlava_1_1render__pipeline.md#using-map) | **[add_color_blend_attachment](/_doxybook/Classes/structlava_1_1render__pipeline.md#function-add-color-blend-attachment)**()<br>Add color blend attachment (default)  |
| [void](/_doxybook/Classes/structlava_1_1render__pipeline.md#using-map) | **[clear_color_blend_attachment](/_doxybook/Classes/structlava_1_1render__pipeline.md#function-clear-color-blend-attachment)**()<br>Clear color blend attachment.  |
| [void](/_doxybook/Classes/structlava_1_1render__pipeline.md#using-map) | **[set_dynamic_states](/_doxybook/Classes/structlava_1_1render__pipeline.md#function-set-dynamic-states)**([VkDynamicStates](/_doxybook/Namespaces/namespacelava.md#using-vkdynamicstates)[const](/_doxybook/Classes/structlava_1_1render__pipeline.md#using-map) & states)<br>Set the dynamic states.  |
| [void](/_doxybook/Classes/structlava_1_1render__pipeline.md#using-map) | **[add_dynamic_state](/_doxybook/Classes/structlava_1_1render__pipeline.md#function-add-dynamic-state)**([VkDynamicState](/_doxybook/Classes/structlava_1_1render__pipeline.md#using-map) state)<br>Add a dynamic state.  |
| [void](/_doxybook/Classes/structlava_1_1render__pipeline.md#using-map) | **[clear_dynamic_states](/_doxybook/Classes/structlava_1_1render__pipeline.md#function-clear-dynamic-states)**()<br>Clear dynamic states.  |
| [bool](/_doxybook/Classes/structlava_1_1render__pipeline.md#using-map) | **[add_shader_stage](/_doxybook/Classes/structlava_1_1render__pipeline.md#function-add-shader-stage)**([cdata::ref](/_doxybook/Classes/structlava_1_1cdata.md#using-ref) data, [VkShaderStageFlagBits](/_doxybook/Classes/structlava_1_1render__pipeline.md#using-map) stage)<br>Add shader stage.  |
| [bool](/_doxybook/Classes/structlava_1_1render__pipeline.md#using-map) | **[add_shader](/_doxybook/Classes/structlava_1_1render__pipeline.md#function-add-shader)**([cdata::ref](/_doxybook/Classes/structlava_1_1cdata.md#using-ref) data, [VkShaderStageFlagBits](/_doxybook/Classes/structlava_1_1render__pipeline.md#using-map) stage)<br>Add shader.  |
| [void](/_doxybook/Classes/structlava_1_1render__pipeline.md#using-map) | **[add](/_doxybook/Classes/structlava_1_1render__pipeline.md#function-add)**(shader_stage::ptr [const](/_doxybook/Classes/structlava_1_1render__pipeline.md#using-map) & shader_stage)<br>Add shader stage.  |
| shader_stage::list [const](/_doxybook/Classes/structlava_1_1render__pipeline.md#using-map) & | **[get_shader_stages](/_doxybook/Classes/structlava_1_1render__pipeline.md#function-get-shader-stages)**() const<br>Get the shader stages.  |
| [void](/_doxybook/Classes/structlava_1_1render__pipeline.md#using-map) | **[clear_shader_stages](/_doxybook/Classes/structlava_1_1render__pipeline.md#function-clear-shader-stages)**()<br>Clear the shader stages.  |
| [void](/_doxybook/Classes/structlava_1_1render__pipeline.md#using-map) | **[clear](/_doxybook/Classes/structlava_1_1render__pipeline.md#function-clear)**()<br>Clear the render pipeline.  |
| [void](/_doxybook/Classes/structlava_1_1render__pipeline.md#using-map) | **[set_auto_size](/_doxybook/Classes/structlava_1_1render__pipeline.md#function-set-auto-size)**([bool](/_doxybook/Classes/structlava_1_1render__pipeline.md#using-map) value =[true](/_doxybook/Classes/structlava_1_1render__pipeline.md#using-map))<br>Set the auto size.  |
| [bool](/_doxybook/Classes/structlava_1_1render__pipeline.md#using-map) | **[auto_sizing](/_doxybook/Classes/structlava_1_1render__pipeline.md#function-auto-sizing)**() const<br>Get the auto sizing state.  |
| [VkViewport](/_doxybook/Classes/structlava_1_1render__pipeline.md#using-map) | **[get_viewport](/_doxybook/Classes/structlava_1_1render__pipeline.md#function-get-viewport)**() const<br>Get the viewport.  |
| [void](/_doxybook/Classes/structlava_1_1render__pipeline.md#using-map) | **[set_viewport](/_doxybook/Classes/structlava_1_1render__pipeline.md#function-set-viewport)**([VkViewport](/_doxybook/Classes/structlava_1_1render__pipeline.md#using-map) value)<br>Set the viewport.  |
| [VkRect2D](/_doxybook/Classes/structlava_1_1render__pipeline.md#using-map) | **[get_scissor](/_doxybook/Classes/structlava_1_1render__pipeline.md#function-get-scissor)**() const<br>Get the scissor.  |
| [void](/_doxybook/Classes/structlava_1_1render__pipeline.md#using-map) | **[set_scissor](/_doxybook/Classes/structlava_1_1render__pipeline.md#function-set-scissor)**([VkRect2D](/_doxybook/Classes/structlava_1_1render__pipeline.md#using-map) value)<br>Set the scissor.  |
| [sizing_mode](/_doxybook/Classes/structlava_1_1render__pipeline.md#enum-sizing-mode) | **[get_sizing](/_doxybook/Classes/structlava_1_1render__pipeline.md#function-get-sizing)**() const<br>Get the sizing.  |
| [void](/_doxybook/Classes/structlava_1_1render__pipeline.md#using-map) | **[set_sizing](/_doxybook/Classes/structlava_1_1render__pipeline.md#function-set-sizing)**([sizing_mode](/_doxybook/Classes/structlava_1_1render__pipeline.md#enum-sizing-mode) value)<br>Set the sizing.  |
| [void](/_doxybook/Classes/structlava_1_1render__pipeline.md#using-map) | **[copy_to](/_doxybook/Classes/structlava_1_1render__pipeline.md#function-copy-to)**([render_pipeline](/_doxybook/Classes/structlava_1_1render__pipeline.md) * target) const<br>Copy pipeline configuration to target.  |
| [void](/_doxybook/Classes/structlava_1_1render__pipeline.md#using-map) | **[copy_from](/_doxybook/Classes/structlava_1_1render__pipeline.md#function-copy-from)**([ptr](/_doxybook/Classes/structlava_1_1render__pipeline.md#using-ptr)[const](/_doxybook/Classes/structlava_1_1render__pipeline.md#using-map) & source)<br>Copy pipeline configuration from source.  |
| [void](/_doxybook/Classes/structlava_1_1render__pipeline.md#using-map) | **[set_line_width](/_doxybook/Classes/structlava_1_1render__pipeline.md#function-set-line-width)**([r32](/_doxybook/Namespaces/namespacelava.md#using-r32) value)<br>Set the line width.  |
| [r32](/_doxybook/Namespaces/namespacelava.md#using-r32) | **[get_line_width](/_doxybook/Classes/structlava_1_1render__pipeline.md#function-get-line-width)**() const<br>Get the line width.  |
| [bool](/_doxybook/Classes/structlava_1_1render__pipeline.md#using-map) | **[auto_line_width](/_doxybook/Classes/structlava_1_1render__pipeline.md#function-auto-line-width)**() const<br>Check if auto line width is active.  |
| [void](/_doxybook/Classes/structlava_1_1render__pipeline.md#using-map) | **[set_auto_line_width](/_doxybook/Classes/structlava_1_1render__pipeline.md#function-set-auto-line-width)**([bool](/_doxybook/Classes/structlava_1_1render__pipeline.md#using-map) value =[true](/_doxybook/Classes/structlava_1_1render__pipeline.md#using-map))<br>Set the auto line width.  |
| [void](/_doxybook/Classes/structlava_1_1render__pipeline.md#using-map) | **[set_line_width](/_doxybook/Classes/structlava_1_1render__pipeline.md#function-set-line-width)**([VkCommandBuffer](/_doxybook/Classes/structlava_1_1render__pipeline.md#using-map) cmd_buf)<br>Set the line width.  |

## Public Attributes

|                | Name           |
| -------------- | -------------- |
| [create_func](/_doxybook/Classes/structlava_1_1render__pipeline.md#using-create-func) | **[on_create](/_doxybook/Classes/structlava_1_1render__pipeline.md#variable-on-create)** <br>Called on render pipeline create.  |

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
| | **[pipeline](/_doxybook/Classes/structlava_1_1pipeline.md#function-pipeline)**([device_p](/_doxybook/Namespaces/namespacelava.md#using-device-p) device, VkPipelineCache pipeline_cache =0)<br>Construct a new pipeline.  |
| | **[~pipeline](/_doxybook/Classes/structlava_1_1pipeline.md#function-~pipeline)**() override<br>Destroy the pipeline.  |
| void | **[destroy](/_doxybook/Classes/structlava_1_1pipeline.md#function-destroy)**()<br>Destroy the pipeline.  |
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

**Public Attributes inherited from [lava::pipeline](/_doxybook/Classes/structlava_1_1pipeline.md)**

|                | Name           |
| -------------- | -------------- |
| [process_func](/_doxybook/Classes/structlava_1_1pipeline.md#using-process-func) | **[on_process](/_doxybook/Classes/structlava_1_1pipeline.md#variable-on-process)** <br>Called on pipeline process.  |

**Protected Attributes inherited from [lava::pipeline](/_doxybook/Classes/structlava_1_1pipeline.md)**

|                | Name           |
| -------------- | -------------- |
| [device_p](/_doxybook/Namespaces/namespacelava.md#using-device-p) | **[device](/_doxybook/Classes/structlava_1_1pipeline.md#variable-device)** <br>Vulkan device.  |
| VkPipeline | **[vk_pipeline](/_doxybook/Classes/structlava_1_1pipeline.md#variable-vk-pipeline)** <br>Vulkan pipeline.  |
| VkPipelineCache | **[pipeline_cache](/_doxybook/Classes/structlava_1_1pipeline.md#variable-pipeline-cache)** <br>Vulkan pipeline cache.  |
| [pipeline_layout::ptr](/_doxybook/Classes/structlava_1_1pipeline__layout.md#using-ptr) | **[layout](/_doxybook/Classes/structlava_1_1pipeline.md#variable-layout)** <br>Pipeline layout.  |

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

### enum sizing_mode

| Enumerator | Value | Description |
| ---------- | ----- | ----------- |
| input | 0|   |
| absolute | |   |
| relative | |   |



Sizing modes. 

### using ptr

```cpp
using lava::render_pipeline::ptr =  std::shared_ptr<render_pipeline>;
```

Shared pointer to render pipeline. 

### using map

```cpp
using lava::render_pipeline::map =  std::map<id, ptr>;
```

Map of render pipelines. 

### using list

```cpp
using lava::render_pipeline::list =  std::vector<ptr>;
```

List of render pipelines. 

### using create_func

```cpp
using lava::render_pipeline::create_func =  std::function<bool(create_info&)>;
```

Create function. 

## Public Functions Documentation

### function make

```cpp
static inline ptr make(
    device_p device,
    VkPipelineCache pipeline_cache =0
)
```

Make a new render pipeline. 

**Parameters**: 

  * **device** Vulkan device 
  * **pipeline_cache** Pipeline cache 


**Return**: ptr Shared pointer to render pipeline 

### function render_pipeline

```cpp
explicit render_pipeline(
    device_p device,
    VkPipelineCache pipeline_cache
)
```

Construct a new render pipeline. 

**Parameters**: 

  * **device** Vulkan device 
  * **pipeline_cache** Pipeline cache 


### function bind

```cpp
virtual void bind(
    VkCommandBuffer cmd_buf
) override
```

Bind the pipeline. 

**Parameters**: 

  * **cmd_buf** Command buffer 


**Reimplements**: [lava::pipeline::bind](/_doxybook/Classes/structlava_1_1pipeline.md#function-bind)


### function set_viewport_and_scissor

```cpp
void set_viewport_and_scissor(
    VkCommandBuffer cmd_buf,
    uv2 size
)
```

Set the viewport and scissor. 

**Parameters**: 

  * **cmd_buf** Command buffer 
  * **size** Viewport and scissor size 


### function set_render_pass

```cpp
inline void set_render_pass(
    VkRenderPass pass
)
```

Set the render pass. 

**Parameters**: 

  * **pass** Render pass 


### function set

```cpp
inline void set(
    VkRenderPass pass
)
```


**See**: [set_render_pass](/_doxybook/Classes/structlava_1_1render__pipeline.md#function-set-render-pass)

### function get_render_pass

```cpp
inline VkRenderPass get_render_pass() const
```

Get the render pass. 

**Return**: VkRenderPass Render pass 

### function get_subpass

```cpp
inline index get_subpass() const
```

Get the subpass. 

**Return**: index Index of subpass 

### function set_subpass

```cpp
inline void set_subpass(
    index value
)
```

Set the subpass. 

**Parameters**: 

  * **value** Index of subpass 


### function create

```cpp
inline bool create(
    VkRenderPass pass
)
```

Create a new render pipeline. 

**Parameters**: 

  * **pass** Vulkan render pass 


**Return**: Create was successful or failed 

### function set_vertex_input_binding

```cpp
void set_vertex_input_binding(
    VkVertexInputBindingDescriptionconst & description
)
```

Set the vertex input binding. 

**Parameters**: 

  * **description** Vertex input binding description 


### function set_vertex_input_bindings

```cpp
void set_vertex_input_bindings(
    VkVertexInputBindingDescriptionsconst & descriptions
)
```

Set the vertex input bindings. 

**Parameters**: 

  * **descriptions** List of vertex input binding descriptions 


### function set_vertex_input_attribute

```cpp
void set_vertex_input_attribute(
    VkVertexInputAttributeDescriptionconst & attribute
)
```

Set the vertex input attribute. 

**Parameters**: 

  * **attribute** Vertex input attribute description 


### function set_vertex_input_attributes

```cpp
void set_vertex_input_attributes(
    VkVertexInputAttributeDescriptionsconst & attributes
)
```

Set the vertex input attributes. 

**Parameters**: 

  * **attributes** List of vertex input attributes descriptions 


### function set_input_topology

```cpp
void set_input_topology(
    VkPrimitiveTopologyconst & topology
)
```

Set the input assembler's topology. 

**Parameters**: 

  * **topology** Enum describing polygon primitives 


### function set_depth_test_and_write

```cpp
void set_depth_test_and_write(
    bool test_enable =true,
    bool write_enable =true
)
```

Set the depth test and write. 

**Parameters**: 

  * **test_enable** Enable depth test 
  * **write_enable** Enable depth write 


### function set_depth_compare_op

```cpp
void set_depth_compare_op(
    VkCompareOp compare_op
)
```

Set the depth compare operation. 

**Parameters**: 

  * **compare_op** Depth compare operation 


### function set_rasterization_cull_mode

```cpp
void set_rasterization_cull_mode(
    VkCullModeFlags cull_mode
)
```

Set the rasterization cull mode. 

**Parameters**: 

  * **cull_mode** Cull mode flags 


### function set_rasterization_front_face

```cpp
void set_rasterization_front_face(
    VkFrontFace front_face
)
```

Set the rasterization front face. 

**Parameters**: 

  * **front_face** Front face 


### function set_rasterization_polygon_mode

```cpp
void set_rasterization_polygon_mode(
    VkPolygonMode polygon_mode
)
```

Set the rasterization polygon mode. 

**Parameters**: 

  * **polygon_mode** Polygon mode 


### function add_color_blend_attachment

```cpp
void add_color_blend_attachment(
    VkPipelineColorBlendAttachmentStateconst & attachment
)
```

Add color blend attachment. 

**Parameters**: 

  * **attachment** Pipeline color blend attachment state 


### function add_color_blend_attachment

```cpp
void add_color_blend_attachment()
```

Add color blend attachment (default) 

### function clear_color_blend_attachment

```cpp
void clear_color_blend_attachment()
```

Clear color blend attachment. 

### function set_dynamic_states

```cpp
void set_dynamic_states(
    VkDynamicStatesconst & states
)
```

Set the dynamic states. 

**Parameters**: 

  * **states** List of dynamic states 


### function add_dynamic_state

```cpp
void add_dynamic_state(
    VkDynamicState state
)
```

Add a dynamic state. 

**Parameters**: 

  * **state** Dynamic state 


### function clear_dynamic_states

```cpp
void clear_dynamic_states()
```

Clear dynamic states. 

### function add_shader_stage

```cpp
bool add_shader_stage(
    cdata::ref data,
    VkShaderStageFlagBits stage
)
```

Add shader stage. 

**Parameters**: 

  * **data** Shader data 
  * **stage** Shader stage flag bits 


**Return**: Add was successful or failed 

### function add_shader

```cpp
inline bool add_shader(
    cdata::ref data,
    VkShaderStageFlagBits stage
)
```

Add shader. 

**Parameters**: 

  * **data** Shader data 
  * **stage** Shader stage flag bits 


**Return**: Add was successful or failed 

### function add

```cpp
inline void add(
    shader_stage::ptr const & shader_stage
)
```

Add shader stage. 

**Parameters**: 

  * **shader_stage** Shader stage 


### function get_shader_stages

```cpp
inline shader_stage::list const & get_shader_stages() const
```

Get the shader stages. 

**Return**: shader_stage::list const& List of shader stages 

### function clear_shader_stages

```cpp
inline void clear_shader_stages()
```

Clear the shader stages. 

### function clear

```cpp
inline void clear()
```

Clear the render pipeline. 

### function set_auto_size

```cpp
inline void set_auto_size(
    bool value =true
)
```

Set the auto size. 

**Parameters**: 

  * **value** Enable state 


### function auto_sizing

```cpp
inline bool auto_sizing() const
```

Get the auto sizing state. 

**Return**: Auto sizing is enabled or not 

### function get_viewport

```cpp
inline VkViewport get_viewport() const
```

Get the viewport. 

**Return**: VkViewport Vulkan viewport 

### function set_viewport

```cpp
inline void set_viewport(
    VkViewport value
)
```

Set the viewport. 

**Parameters**: 

  * **value** Vulkan viewport 


### function get_scissor

```cpp
inline VkRect2D get_scissor() const
```

Get the scissor. 

**Return**: VkRect2D Scissor rectangle 

### function set_scissor

```cpp
inline void set_scissor(
    VkRect2D value
)
```

Set the scissor. 

**Parameters**: 

  * **value** Scissor rectangle 


### function get_sizing

```cpp
inline sizing_mode get_sizing() const
```

Get the sizing. 

**Return**: sizing_mode Sizing mode 

### function set_sizing

```cpp
inline void set_sizing(
    sizing_mode value
)
```

Set the sizing. 

**Parameters**: 

  * **value** Sizing mode 


### function copy_to

```cpp
void copy_to(
    render_pipeline * target
) const
```

Copy pipeline configuration to target. 

**Parameters**: 

  * **target** Render pipeline 


### function copy_from

```cpp
inline void copy_from(
    ptrconst & source
)
```

Copy pipeline configuration from source. 

**Parameters**: 

  * **source** Render pipeline 


### function set_line_width

```cpp
inline void set_line_width(
    r32 value
)
```

Set the line width. 

**Parameters**: 

  * **value** Line width 


### function get_line_width

```cpp
inline r32 get_line_width() const
```

Get the line width. 

**Return**: r32 Line width 

### function auto_line_width

```cpp
inline bool auto_line_width() const
```

Check if auto line width is active. 

**Return**: Auto line width is enabled or not 

### function set_auto_line_width

```cpp
inline void set_auto_line_width(
    bool value =true
)
```

Set the auto line width. 

**Parameters**: 

  * **value** Enable state 


### function set_line_width

```cpp
inline void set_line_width(
    VkCommandBuffer cmd_buf
)
```

Set the line width. 

**Parameters**: 

  * **cmd_buf** Command buffer 


## Public Attributes Documentation

### variable on_create

```cpp
create_func on_create;
```

Called on render pipeline create. 

-------------------------------

Updated on 2024-03-22 at 21:51:38 +0000