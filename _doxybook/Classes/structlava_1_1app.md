---
title: lava::app
summary: Application with basic functionality. 

---

# lava::app



Application with basic functionality. 


`#include <app.hpp>`

Inherits from [lava::frame](/_doxybook/Classes/structlava_1_1frame.md), [lava::interface](/_doxybook/Classes/structlava_1_1interface.md), [lava::no_copy_no_move](/_doxybook/Classes/structlava_1_1no__copy__no__move.md)

Inherited by [lava::engine](/_doxybook/Classes/structlava_1_1engine.md)

## Public Types

|                | Name           |
| -------------- | -------------- |
| using std::function< bool([delta](/_doxybook/Namespaces/namespacelava.md#using-delta))> | **[update_func](/_doxybook/Classes/structlava_1_1app.md#using-update-func)** <br>Update function.  |
| using std::function< bool()> | **[create_func](/_doxybook/Classes/structlava_1_1app.md#using-create-func)** <br>Create function.  |
| using std::function< void()> | **[destroy_func](/_doxybook/Classes/structlava_1_1app.md#using-destroy-func)** <br>Destroy function.  |
| using std::function< void(VkCommandBuffer, [index](/_doxybook/Namespaces/namespacelava.md#using-index))> | **[process_func](/_doxybook/Classes/structlava_1_1app.md#using-process-func)** <br>Process function.  |
| using std::function< bool()> | **[setup_func](/_doxybook/Classes/structlava_1_1app.md#using-setup-func)** <br>Set up function.  |

## Public Functions

|                | Name           |
| -------------- | -------------- |
| | **[app](/_doxybook/Classes/structlava_1_1app.md#function-app)**([frame_env::ref](/_doxybook/Classes/structlava_1_1frame__env.md#using-ref) env)<br>Construct a new app.  |
| | **[app](/_doxybook/Classes/structlava_1_1app.md#function-app)**([name](/_doxybook/Namespaces/namespacelava.md#using-name) name, argh::parser cmd_line ={})<br>Construct a new app.  |
| virtual bool | **[setup](/_doxybook/Classes/structlava_1_1app.md#function-setup)**()<br>Set up the application.  |
| bool | **[v_sync](/_doxybook/Classes/structlava_1_1app.md#function-v-sync)**() const<br>V-Sync setting.  |
| [ui32](/_doxybook/Namespaces/namespacelava.md#using-ui32) | **[get_frame_counter](/_doxybook/Classes/structlava_1_1app.md#function-get-frame-counter)**() const<br>Get the frame counter.  |
| void | **[draw_about](/_doxybook/Classes/structlava_1_1app.md#function-draw-about)**(bool separator =[draw_separator](/_doxybook/Namespaces/namespacelava.md#variable-draw-separator), bool fps =[draw_fps](/_doxybook/Namespaces/namespacelava.md#variable-draw-fps), bool spacing =[draw_spacing](/_doxybook/Namespaces/namespacelava.md#variable-draw-spacing)) const<br>Draw about information.  |
| [id::ref](/_doxybook/Classes/structlava_1_1id.md#using-ref) | **[block_cmd](/_doxybook/Classes/structlava_1_1app.md#function-block-cmd)**() const<br>Get id of the block command.  |
| [string](/_doxybook/Namespaces/namespacelava.md#using-string) | **[screenshot](/_doxybook/Classes/structlava_1_1app.md#function-screenshot)**()<br>Take screenshot and save it to file.  |
| void | **[parse_config](/_doxybook/Classes/structlava_1_1app.md#function-parse-config)**(argh::parser cmd_line)<br>Parse config.  |

## Public Attributes

|                | Name           |
| -------------- | -------------- |
| [window_t](/_doxybook/Namespaces/namespacelava.md#using-window-t) | **[window](/_doxybook/Classes/structlava_1_1app.md#variable-window)** <br>Main window.  |
| [input_t](/_doxybook/Namespaces/namespacelava.md#using-input-t) | **[input](/_doxybook/Classes/structlava_1_1app.md#variable-input)** <br>Window input.  |
| [imgui_t](/_doxybook/Namespaces/namespacelava.md#using-imgui-t) | **[imgui](/_doxybook/Classes/structlava_1_1app.md#variable-imgui)** <br>ImGui handling.  |
| [imgui::config](/_doxybook/Classes/structlava_1_1imgui_1_1config.md) | **[imgui_config](/_doxybook/Classes/structlava_1_1app.md#variable-imgui-config)** <br>ImGui configuration.  |
| [tooltip_list](/_doxybook/Classes/structlava_1_1tooltip__list.md) | **[tooltips](/_doxybook/Classes/structlava_1_1app.md#variable-tooltips)** <br>Tooltip list.  |
| [device_p](/_doxybook/Namespaces/namespacelava.md#using-device-p) | **[device](/_doxybook/Classes/structlava_1_1app.md#variable-device)** <br>Vulkan device.  |
| [camera_t](/_doxybook/Namespaces/namespacelava.md#using-camera-t) | **[camera](/_doxybook/Classes/structlava_1_1app.md#variable-camera)** <br>Main camera.  |
| [gamepad](/_doxybook/Classes/structlava_1_1gamepad.md) | **[pad](/_doxybook/Classes/structlava_1_1app.md#variable-pad)** <br>Gamepad.  |
| [staging_t](/_doxybook/Namespaces/namespacelava.md#using-staging-t) | **[staging](/_doxybook/Classes/structlava_1_1app.md#variable-staging)** <br>Texture staging.  |
| [block_t](/_doxybook/Namespaces/namespacelava.md#using-block-t) | **[block](/_doxybook/Classes/structlava_1_1app.md#variable-block)** <br>Basic block.  |
| [renderer_t](/_doxybook/Namespaces/namespacelava.md#using-renderer-t) | **[renderer](/_doxybook/Classes/structlava_1_1app.md#variable-renderer)** <br>Plain renderer.  |
| [forward_shading](/_doxybook/Classes/structlava_1_1forward__shading.md) | **[shading](/_doxybook/Classes/structlava_1_1app.md#variable-shading)** <br>Forward shading.  |
| [render_target::ptr](/_doxybook/Classes/structlava_1_1render__target.md#using-ptr) | **[target](/_doxybook/Classes/structlava_1_1app.md#variable-target)** <br>Render target.  |
| [run_time_t](/_doxybook/Namespaces/namespacelava.md#using-run-time-t) | **[run_time](/_doxybook/Classes/structlava_1_1app.md#variable-run-time)** <br>Run time.  |
| [file_system](/_doxybook/Classes/structlava_1_1file__system.md) | **[fs](/_doxybook/Classes/structlava_1_1app.md#variable-fs)** <br>File system.  |
| VkPipelineCache | **[pipeline_cache](/_doxybook/Classes/structlava_1_1app.md#variable-pipeline-cache)** <br>Pipeline cache.  |
| [update_func](/_doxybook/Classes/structlava_1_1app.md#using-update-func) | **[on_update](/_doxybook/Classes/structlava_1_1app.md#variable-on-update)** <br>Function called on application update.  |
| [create_func](/_doxybook/Classes/structlava_1_1app.md#using-create-func) | **[on_create](/_doxybook/Classes/structlava_1_1app.md#variable-on-create)** <br>Function called on application create.  |
| [destroy_func](/_doxybook/Classes/structlava_1_1app.md#using-destroy-func) | **[on_destroy](/_doxybook/Classes/structlava_1_1app.md#variable-on-destroy)** <br>Function called on application destroy.  |
| [app_config](/_doxybook/Classes/structlava_1_1app__config.md) | **[config](/_doxybook/Classes/structlava_1_1app.md#variable-config)** <br>Application configuration.  |
| [json_file](/_doxybook/Classes/structlava_1_1json__file.md) | **[config_file](/_doxybook/Classes/structlava_1_1app.md#variable-config-file)** <br>Configuration file.  |
| [process_func](/_doxybook/Classes/structlava_1_1app.md#using-process-func) | **[on_process](/_doxybook/Classes/structlava_1_1app.md#variable-on-process)** <br>Function called on application process.  |
| [setup_func](/_doxybook/Classes/structlava_1_1app.md#using-setup-func) | **[on_setup](/_doxybook/Classes/structlava_1_1app.md#variable-on-setup)** <br>Function called on application setup.  |

## Additional inherited members

**Public Types inherited from [lava::frame](/_doxybook/Classes/structlava_1_1frame.md)**

|                | Name           |
| -------------- | -------------- |
| using std::shared_ptr< [frame](/_doxybook/Classes/structlava_1_1frame.md) > | **[ptr](/_doxybook/Classes/structlava_1_1frame.md#using-ptr)** <br>Shared pointer to framework.  |
| using [i32](/_doxybook/Namespaces/namespacelava.md#using-i32) | **[result](/_doxybook/Classes/structlava_1_1frame.md#using-result)** <br>Framework result.  |
| using std::function< bool([id::ref](/_doxybook/Classes/structlava_1_1id.md#using-ref))> | **[run_func](/_doxybook/Classes/structlava_1_1frame.md#using-run-func)** <br>Run function.  |
| using [run_func](/_doxybook/Classes/structlava_1_1frame.md#using-run-func) const  & | **[run_func_ref](/_doxybook/Classes/structlava_1_1frame.md#using-run-func-ref)** <br>Reference to run function.  |
| using std::function< void()> | **[run_end_func](/_doxybook/Classes/structlava_1_1frame.md#using-run-end-func)** <br>Run end function.  |
| using [run_end_func](/_doxybook/Classes/structlava_1_1frame.md#using-run-end-func) const  & | **[run_end_func_ref](/_doxybook/Classes/structlava_1_1frame.md#using-run-end-func-ref)** <br>Reference to run end function.  |
| using std::function< bool()> | **[run_once_func](/_doxybook/Classes/structlava_1_1frame.md#using-run-once-func)** <br>Run once function.  |
| using [run_once_func](/_doxybook/Classes/structlava_1_1frame.md#using-run-once-func) const  & | **[run_once_func_ref](/_doxybook/Classes/structlava_1_1frame.md#using-run-once-func-ref)** <br>Reference to run once function.  |

**Public Functions inherited from [lava::frame](/_doxybook/Classes/structlava_1_1frame.md)**

|                | Name           |
| -------------- | -------------- |
| | **[frame](/_doxybook/Classes/structlava_1_1frame.md#function-frame)**(argh::parser cmd_line)<br>Construct a new framework.  |
| | **[frame](/_doxybook/Classes/structlava_1_1frame.md#function-frame)**([frame_env](/_doxybook/Classes/structlava_1_1frame__env.md) env)<br>Construct a new framework.  |
| | **[~frame](/_doxybook/Classes/structlava_1_1frame.md#function-~frame)**() override<br>Destroy the framework.  |
| bool | **[ready](/_doxybook/Classes/structlava_1_1frame.md#function-ready)**() const<br>Check if framework is ready.  |
| [result](/_doxybook/Classes/structlava_1_1frame.md#using-result) | **[run](/_doxybook/Classes/structlava_1_1frame.md#function-run)**()<br>Run the framework.  |
| bool | **[shut_down](/_doxybook/Classes/structlava_1_1frame.md#function-shut-down)**()<br>Shut down the framework.  |
| [id](/_doxybook/Classes/structlava_1_1id.md) | **[add_run](/_doxybook/Classes/structlava_1_1frame.md#function-add-run)**([run_func_ref](/_doxybook/Classes/structlava_1_1frame.md#using-run-func-ref) func)<br>Add run to framework.  |
| [id](/_doxybook/Classes/structlava_1_1id.md) | **[add_run_end](/_doxybook/Classes/structlava_1_1frame.md#function-add-run-end)**([run_end_func_ref](/_doxybook/Classes/structlava_1_1frame.md#using-run-end-func-ref) func)<br>Add run end to framework.  |
| void | **[add_run_once](/_doxybook/Classes/structlava_1_1frame.md#function-add-run-once)**([run_once_func_ref](/_doxybook/Classes/structlava_1_1frame.md#using-run-once-func-ref) func)<br>Add run once to framework.  |
| bool | **[remove](/_doxybook/Classes/structlava_1_1frame.md#function-remove)**([id::ref](/_doxybook/Classes/structlava_1_1id.md#using-ref) func_id)<br>Remove a function from framework.  |
| [ms](/_doxybook/Namespaces/namespacelava.md#using-ms) | **[get_running_time](/_doxybook/Classes/structlava_1_1frame.md#function-get-running-time)**() const<br>Get the running time.  |
| [r64](/_doxybook/Namespaces/namespacelava.md#using-r64) | **[get_running_time_sec](/_doxybook/Classes/structlava_1_1frame.md#function-get-running-time-sec)**() const<br>Get the running time in seconds.  |
| [cmd_line](/_doxybook/Namespaces/namespacelava.md#using-cmd-line) | **[get_cmd_line](/_doxybook/Classes/structlava_1_1frame.md#function-get-cmd-line)**() const<br>Get the command line arguments.  |
| [frame_env::ref](/_doxybook/Classes/structlava_1_1frame__env.md#using-ref) | **[get_env](/_doxybook/Classes/structlava_1_1frame.md#function-get-env)**() const<br>Get the framework environment.  |
| [name](/_doxybook/Namespaces/namespacelava.md#using-name) | **[get_name](/_doxybook/Classes/structlava_1_1frame.md#function-get-name)**() const<br>Get the name of application.  |
| bool | **[waiting_for_events](/_doxybook/Classes/structlava_1_1frame.md#function-waiting-for-events)**() const<br>Check if framework is waiting for events.  |
| void | **[set_wait_for_events](/_doxybook/Classes/structlava_1_1frame.md#function-set-wait-for-events)**(bool value =true)<br>Set wait for events in framework.  |

**Public Attributes inherited from [lava::frame](/_doxybook/Classes/structlava_1_1frame.md)**

|                | Name           |
| -------------- | -------------- |
| [platform_t](/_doxybook/Namespaces/namespacelava.md#using-platform-t) | **[platform](/_doxybook/Classes/structlava_1_1frame.md#variable-platform)** <br>Stage platform.  |

**Public Functions inherited from [lava::interface](/_doxybook/Classes/structlava_1_1interface.md)**

|                | Name           |
| -------------- | -------------- |
| virtual | **[~interface](/_doxybook/Classes/structlava_1_1interface.md#function-~interface)**() =default<br>Destroy the interface.  |

**Public Functions inherited from [lava::no_copy_no_move](/_doxybook/Classes/structlava_1_1no__copy__no__move.md)**

|                | Name           |
| -------------- | -------------- |
| | **[no_copy_no_move](/_doxybook/Classes/structlava_1_1no__copy__no__move.md#function-no-copy-no-move)**() =default<br>Construct a new object.  |
| | **[no_copy_no_move](/_doxybook/Classes/structlava_1_1no__copy__no__move.md#function-no-copy-no-move)**([no_copy_no_move](/_doxybook/Classes/structlava_1_1no__copy__no__move.md) const & ) =delete<br>No copy.  |
| void | **[operator=](/_doxybook/Classes/structlava_1_1no__copy__no__move.md#function-operator=)**([no_copy_no_move](/_doxybook/Classes/structlava_1_1no__copy__no__move.md) const & ) =delete<br>No move.  |


## Public Types Documentation

### using update_func

```cpp
using lava::app::update_func =  std::function<bool(delta)>;
```

Update function. 

### using create_func

```cpp
using lava::app::create_func =  std::function<bool()>;
```

Create function. 

### using destroy_func

```cpp
using lava::app::destroy_func =  std::function<void()>;
```

Destroy function. 

### using process_func

```cpp
using lava::app::process_func =  std::function<void(VkCommandBuffer, index)>;
```

Process function. 

### using setup_func

```cpp
using lava::app::setup_func =  std::function<bool()>;
```

Set up function. 

## Public Functions Documentation

### function app

```cpp
explicit app(
    frame_env::ref env
)
```

Construct a new app. 

**Parameters**: 

  * **env** Frame environment 


### function app

```cpp
explicit app(
    name name,
    argh::parser cmd_line ={}
)
```

Construct a new app. 

**Parameters**: 

  * **name** Application name 
  * **cmd_line** Command line arguments 


### function setup

```cpp
virtual bool setup()
```

Set up the application. 

**Return**: Setup was successful or failed 

**Reimplemented by**: [lava::engine::setup](/_doxybook/Classes/structlava_1_1engine.md#function-setup)


### function v_sync

```cpp
inline bool v_sync() const
```

V-Sync setting. 

**Return**: V-Sync is active or not 

### function get_frame_counter

```cpp
inline ui32 get_frame_counter() const
```

Get the frame counter. 

**Return**: ui32 Number of rendered frames 

### function draw_about

```cpp
void draw_about(
    bool separator =draw_separator,
    bool fps =draw_fps,
    bool spacing =draw_spacing
) const
```

Draw about information. 

**Parameters**: 

  * **separator** Prepend separator 
  * **fps** FPS counter 
  * **spacing** Spacing 


### function block_cmd

```cpp
inline id::ref block_cmd() const
```

Get id of the block command. 

**Return**: [id::ref](/_doxybook/Classes/structlava_1_1id.md#using-ref) Id to access the command 

### function screenshot

```cpp
string screenshot()
```

Take screenshot and save it to file. 

**Return**: string Screenshot file path (empty: failed) 

### function parse_config

```cpp
void parse_config(
    argh::parser cmd_line
)
```

Parse config. 

**Parameters**: 

  * **cmd_line** Command line arguments 


## Public Attributes Documentation

### variable window

```cpp
window_t window;
```

Main window. 

### variable input

```cpp
input_t input;
```

Window input. 

### variable imgui

```cpp
imgui_t imgui;
```

ImGui handling. 

### variable imgui_config

```cpp
imgui::config imgui_config;
```

ImGui configuration. 

### variable tooltips

```cpp
tooltip_list tooltips;
```

Tooltip list. 

### variable device

```cpp
device_p device = nullptr;
```

Vulkan device. 

### variable camera

```cpp
camera_t camera;
```

Main camera. 

### variable pad

```cpp
gamepad pad;
```

Gamepad. 

### variable staging

```cpp
staging_t staging;
```

Texture staging. 

### variable block

```cpp
block_t block;
```

Basic block. 

### variable renderer

```cpp
renderer_t renderer;
```

Plain renderer. 

### variable shading

```cpp
forward_shading shading;
```

Forward shading. 

### variable target

```cpp
render_target::ptr target;
```

Render target. 

### variable run_time

```cpp
run_time_t run_time;
```

Run time. 

### variable fs

```cpp
file_system fs;
```

File system. 

### variable pipeline_cache

```cpp
VkPipelineCache pipeline_cache = nullptr;
```

Pipeline cache. 

### variable on_update

```cpp
update_func on_update;
```

Function called on application update. 

### variable on_create

```cpp
create_func on_create;
```

Function called on application create. 

### variable on_destroy

```cpp
destroy_func on_destroy;
```

Function called on application destroy. 

### variable config

```cpp
app_config config;
```

Application configuration. 

### variable config_file

```cpp
json_file config_file;
```

Configuration file. 

### variable on_process

```cpp
process_func on_process;
```

Function called on application process. 

### variable on_setup

```cpp
setup_func on_setup;
```

Function called on application setup. 

-------------------------------

Updated on 2022-11-30 at 01:16:03 +0000