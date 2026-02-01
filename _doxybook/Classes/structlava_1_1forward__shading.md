---
title: lava::forward_shading
summary: Forward shading. 

---

# lava::forward_shading



Forward shading. 


`#include <forward_shading.hpp>`

## Public Functions

|                | Name           |
| -------------- | -------------- |
| | **[forward_shading](/_doxybook/Classes/structlava_1_1forward__shading.md#function-forward-shading)**() =default<br>Construct a new forward shading.  |
| | **[~forward_shading](/_doxybook/Classes/structlava_1_1forward__shading.md#function-~forward-shading)**()<br>Destroy the forward shading.  |
| bool | **[create](/_doxybook/Classes/structlava_1_1forward__shading.md#function-create)**([render_target::s_ptr](/_doxybook/Classes/structlava_1_1render__target.md#using-s-ptr) target)<br>Create a forward shading for a render target.  |
| void | **[destroy](/_doxybook/Classes/structlava_1_1forward__shading.md#function-destroy)**()<br>Destroy the forward shading.  |
| [render_pass::s_ptr](/_doxybook/Classes/structlava_1_1render__pass.md#using-s-ptr) | **[get_pass](/_doxybook/Classes/structlava_1_1forward__shading.md#function-get-pass)**() const<br>Get the render pass.  |
| VkRenderPass | **[get_vk_pass](/_doxybook/Classes/structlava_1_1forward__shading.md#function-get-vk-pass)**() const<br>Get the Vulkan render pass.  |
| [image::s_ptr](/_doxybook/Classes/structlava_1_1image.md#using-s-ptr) | **[get_depth_stencil](/_doxybook/Classes/structlava_1_1forward__shading.md#function-get-depth-stencil)**() const<br>Get the depth stencil image.  |

## Public Functions Documentation

### function forward_shading

```cpp
explicit forward_shading() =default
```

Construct a new forward shading. 

### function ~forward_shading

```cpp
inline ~forward_shading()
```

Destroy the forward shading. 

### function create

```cpp
bool create(
    render_target::s_ptr target
)
```

Create a forward shading for a render target. 

**Parameters**: 

  * **target** Render target 


**Return**: Create was successful or failed 

### function destroy

```cpp
void destroy()
```

Destroy the forward shading. 

### function get_pass

```cpp
inline render_pass::s_ptr get_pass() const
```

Get the render pass. 

**Return**: [render_pass::s_ptr](/_doxybook/Classes/structlava_1_1render__pass.md#using-s-ptr) Render pass 

### function get_vk_pass

```cpp
inline VkRenderPass get_vk_pass() const
```

Get the Vulkan render pass. 

**Return**: VkRenderPass Vulkan Render pass 

### function get_depth_stencil

```cpp
inline image::s_ptr get_depth_stencil() const
```

Get the depth stencil image. 

**Return**: [image::s_ptr](/_doxybook/Classes/structlava_1_1image.md#using-s-ptr) Depth stencil Image 

-------------------------------

Updated on 2026-02-01 at 18:13:39 +0000