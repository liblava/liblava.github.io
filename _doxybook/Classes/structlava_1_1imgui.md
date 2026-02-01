---
title: lava::imgui
summary: ImGui integration. 

---

# lava::imgui



ImGui integration. 


`#include <imgui.hpp>`

## Public Classes

|                | Name           |
| -------------- | -------------- |
| struct | **[config](/_doxybook/Classes/structlava_1_1imgui_1_1config.md)** <br>ImGui configuration.  |
| struct | **[font](/_doxybook/Classes/structlava_1_1imgui_1_1font.md)** <br>ImGui font settings.  |
| struct | **[icon_font](/_doxybook/Classes/structlava_1_1imgui_1_1icon__font.md)** <br>ImGui icon font settings.  |

## Public Types

|                | Name           |
| -------------- | -------------- |
| using [imgui](/_doxybook/Classes/structlava_1_1imgui.md) * | **[ptr](/_doxybook/Classes/structlava_1_1imgui.md#using-ptr)** <br>Pointer to imgui.  |
| using std::function< void()> | **[draw_func](/_doxybook/Classes/structlava_1_1imgui.md#using-draw-func)** <br>Draw function.  |

## Public Functions

|                | Name           |
| -------------- | -------------- |
| | **[imgui](/_doxybook/Classes/structlava_1_1imgui.md#function-imgui)**() =default<br>Construct a new ImGui.  |
| | **[imgui](/_doxybook/Classes/structlava_1_1imgui.md#function-imgui)**(GLFWwindow * window)<br>Construct a new ImGui.  |
| | **[~imgui](/_doxybook/Classes/structlava_1_1imgui.md#function-~imgui)**()<br>Destroy the ImGui.  |
| void | **[setup](/_doxybook/Classes/structlava_1_1imgui.md#function-setup)**(GLFWwindow * window, [config](/_doxybook/Classes/structlava_1_1imgui_1_1config.md) config)<br>Set up ImGui with configuration.  |
| void | **[setup](/_doxybook/Classes/structlava_1_1imgui.md#function-setup)**(GLFWwindow * win)<br>Set up default ImGui.  |
| bool | **[create](/_doxybook/Classes/structlava_1_1imgui.md#function-create)**([render_pipeline::s_ptr](/_doxybook/Classes/structlava_1_1render__pipeline.md#using-s-ptr) pipeline, [index](/_doxybook/Namespaces/namespacelava.md#using-index) max_frames)<br>Create pipeline for ImGui.  |
| bool | **[create](/_doxybook/Classes/structlava_1_1imgui.md#function-create)**([device::ptr](/_doxybook/Classes/structlava_1_1device.md#using-ptr) dev, [index](/_doxybook/Namespaces/namespacelava.md#using-index) frames, VkPipelineCache pipeline_cache)<br>Create pipeline for ImGui with device.  |
| bool | **[create](/_doxybook/Classes/structlava_1_1imgui.md#function-create)**([device::ptr](/_doxybook/Classes/structlava_1_1device.md#using-ptr) dev, [index](/_doxybook/Namespaces/namespacelava.md#using-index) frames, VkRenderPass pass, VkPipelineCache pipeline_cache =0)<br>Create pipeline for ImGui with device and render pass.  |
| bool | **[upload_fonts](/_doxybook/Classes/structlava_1_1imgui.md#function-upload-fonts)**([texture::s_ptr](/_doxybook/Classes/structlava_1_1texture.md#using-s-ptr) texture)<br>Upload font texture.  |
| void | **[destroy](/_doxybook/Classes/structlava_1_1imgui.md#function-destroy)**()<br>Destroy ImGui.  |
| bool | **[ready](/_doxybook/Classes/structlava_1_1imgui.md#function-ready)**() const<br>Check if ImGui is ready.  |
| [render_pipeline::s_ptr](/_doxybook/Classes/structlava_1_1render__pipeline.md#using-s-ptr) | **[get_pipeline](/_doxybook/Classes/structlava_1_1imgui.md#function-get-pipeline)**()<br>Get the pipeline.  |
| bool | **[capture_mouse](/_doxybook/Classes/structlava_1_1imgui.md#function-capture-mouse)**() const<br>Check if mouse capture is active.  |
| bool | **[capture_keyboard](/_doxybook/Classes/structlava_1_1imgui.md#function-capture-keyboard)**() const<br>Check if keyboard capture is active.  |
| void | **[set_active](/_doxybook/Classes/structlava_1_1imgui.md#function-set-active)**(bool value =true)<br>Set ImGui active.  |
| bool | **[activated](/_doxybook/Classes/structlava_1_1imgui.md#function-activated)**() const<br>Check if ImGui is activated.  |
| void | **[toggle](/_doxybook/Classes/structlava_1_1imgui.md#function-toggle)**()<br>Togge active state.  |
| void | **[set_ini_file](/_doxybook/Classes/structlava_1_1imgui.md#function-set-ini-file)**(std::filesystem::path dir)<br>Set the ini file.  |
| std::filesystem::path | **[get_ini_file](/_doxybook/Classes/structlava_1_1imgui.md#function-get-ini-file)**() const<br>Get the ini file.  |
| void | **[convert_style_to_srgb](/_doxybook/Classes/structlava_1_1imgui.md#function-convert-style-to-srgb)**()<br>Convert style to sRGB.  |
| [input_callback](/_doxybook/Classes/structlava_1_1input__callback.md) const & | **[get_input_callback](/_doxybook/Classes/structlava_1_1imgui.md#function-get-input-callback)**() const<br>Get the input callback.  |

## Public Attributes

|                | Name           |
| -------------- | -------------- |
| [draw_func](/_doxybook/Classes/structlava_1_1imgui.md#using-draw-func) | **[on_draw](/_doxybook/Classes/structlava_1_1imgui.md#variable-on-draw)** <br>Function called on ImGui draw.  |
| [layer_list](/_doxybook/Classes/structlava_1_1layer__list.md) | **[layers](/_doxybook/Classes/structlava_1_1imgui.md#variable-layers)** <br>Layer list.  |

## Public Types Documentation

### using ptr

```cpp
using lava::imgui::ptr =  imgui*;
```

Pointer to imgui. 

### using draw_func

```cpp
using lava::imgui::draw_func =  std::function<void()>;
```

Draw function. 

## Public Functions Documentation

### function imgui

```cpp
explicit imgui() =default
```

Construct a new ImGui. 

### function imgui

```cpp
inline explicit imgui(
    GLFWwindow * window
)
```

Construct a new ImGui. 

**Parameters**: 

  * **window** Window for ImGui 


### function ~imgui

```cpp
inline ~imgui()
```

Destroy the ImGui. 

### function setup

```cpp
void setup(
    GLFWwindow * window,
    config config
)
```

Set up ImGui with configuration. 

**Parameters**: 

  * **window** Target window 
  * **config** Configuration 


### function setup

```cpp
inline void setup(
    GLFWwindow * win
)
```

Set up default ImGui. 

**Parameters**: 

  * **win** Target window 


### function create

```cpp
bool create(
    render_pipeline::s_ptr pipeline,
    index max_frames
)
```

Create pipeline for ImGui. 

**Parameters**: 

  * **pipeline** Render pipeline 
  * **max_frames** Number of frames 


**Return**: Create was successful or failed 

### function create

```cpp
inline bool create(
    device::ptr dev,
    index frames,
    VkPipelineCache pipeline_cache
)
```

Create pipeline for ImGui with device. 

**Parameters**: 

  * **dev** Vulkan device 
  * **frames** Number of frames 
  * **pipeline_cache** Pipeline cache 


**Return**: Create was successful or failed 

### function create

```cpp
inline bool create(
    device::ptr dev,
    index frames,
    VkRenderPass pass,
    VkPipelineCache pipeline_cache =0
)
```

Create pipeline for ImGui with device and render pass. 

**Parameters**: 

  * **dev** Vulkan device 
  * **frames** Number of frames 
  * **pass** Render pass 
  * **pipeline_cache** Pipeline cache 


**Return**: Create was successful or failed 

### function upload_fonts

```cpp
bool upload_fonts(
    texture::s_ptr texture
)
```

Upload font texture. 

**Parameters**: 

  * **texture** Texture to upload 


**Return**: Upload was successful or failed 

### function destroy

```cpp
void destroy()
```

Destroy ImGui. 

### function ready

```cpp
inline bool ready() const
```

Check if ImGui is ready. 

**Return**: ImGui is ready or not 

### function get_pipeline

```cpp
inline render_pipeline::s_ptr get_pipeline()
```

Get the pipeline. 

**Return**: [render_pipeline::s_ptr](/_doxybook/Classes/structlava_1_1render__pipeline.md#using-s-ptr) Render pipeline 

### function capture_mouse

```cpp
bool capture_mouse() const
```

Check if mouse capture is active. 

**Return**: Capture is active or not 

### function capture_keyboard

```cpp
bool capture_keyboard() const
```

Check if keyboard capture is active. 

**Return**: Capture is active or not 

### function set_active

```cpp
inline void set_active(
    bool value =true
)
```

Set ImGui active. 

**Parameters**: 

  * **value** Active state 


### function activated

```cpp
inline bool activated() const
```

Check if ImGui is activated. 

**Return**: ImGui is active or not 

### function toggle

```cpp
inline void toggle()
```

Togge active state. 

### function set_ini_file

```cpp
void set_ini_file(
    std::filesystem::path dir
)
```

Set the ini file. 

**Parameters**: 

  * **dir** Path for file 


### function get_ini_file

```cpp
inline std::filesystem::path get_ini_file() const
```

Get the ini file. 

**Return**: fs::path Path of file 

### function convert_style_to_srgb

```cpp
void convert_style_to_srgb()
```

Convert style to sRGB. 

### function get_input_callback

```cpp
inline input_callback const & get_input_callback() const
```

Get the input callback. 

**Return**: [input_callback](/_doxybook/Classes/structlava_1_1input__callback.md) const& Input callback 

## Public Attributes Documentation

### variable on_draw

```cpp
draw_func on_draw;
```

Function called on ImGui draw. 

### variable layers

```cpp
layer_list layers;
```

Layer list. 

-------------------------------

Updated on 2026-02-01 at 18:13:39 +0000