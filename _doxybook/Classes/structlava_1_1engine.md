---
title: lava::engine
summary: Engine. 

---

# lava::engine



Engine. 


`#include <engine.hpp>`

Inherits from [lava::app](/_doxybook/Classes/structlava_1_1app.md), [lava::frame](/_doxybook/Classes/structlava_1_1frame.md), [lava::interface](/_doxybook/Classes/structlava_1_1interface.md), [lava::no_copy_no_move](/_doxybook/Classes/structlava_1_1no__copy__no__move.md)

## Public Types

|                | Name           |
| -------------- | -------------- |
| using [engine](/_doxybook/Classes/structlava_1_1engine.md) * | **[ptr](/_doxybook/Classes/structlava_1_1engine.md#using-ptr)**  |
| using std::function< void()> | **[hud_menu_func](/_doxybook/Classes/structlava_1_1engine.md#using-hud-menu-func)** <br>Hud menu function.  |

## Public Functions

|                | Name           |
| -------------- | -------------- |
| virtual bool | **[setup](/_doxybook/Classes/structlava_1_1engine.md#function-setup)**() override<br>Set up the engine.  |
| | **[app](/_doxybook/Classes/structlava_1_1engine.md#function-app)**([frame_env::ref](/_doxybook/Classes/structlava_1_1frame__env.md#using-ref) env)<br>App constructors.  |
| | **[app](/_doxybook/Classes/structlava_1_1engine.md#function-app)**([name](/_doxybook/Namespaces/namespacelava.md#using-name) name, argh::parser cmd_line ={})<br>App constructors.  |

## Public Attributes

|                | Name           |
| -------------- | -------------- |
| [lava::props](/_doxybook/Classes/structlava_1_1props.md) | **[props](/_doxybook/Classes/structlava_1_1engine.md#variable-props)** <br>Props.  |
| [lava::producer](/_doxybook/Classes/structlava_1_1producer.md) | **[producer](/_doxybook/Classes/structlava_1_1engine.md#variable-producer)** <br>Producer.  |
| [hud_menu_func](/_doxybook/Classes/structlava_1_1engine.md#using-hud-menu-func) | **[on_menu](/_doxybook/Classes/structlava_1_1engine.md#variable-on-menu)** <br>Function called on hud menu.  |
| bool | **[hud_active](/_doxybook/Classes/structlava_1_1engine.md#variable-hud-active)** <br>Hud active state.  |

## Additional inherited members

**Public Classes inherited from [lava::app](/_doxybook/Classes/structlava_1_1app.md)**

|                | Name           |
| -------------- | -------------- |
| struct | **[about_info_setting](/_doxybook/Classes/structlava_1_1app_1_1about__info__setting.md)**  |

**Public Types inherited from [lava::app](/_doxybook/Classes/structlava_1_1app.md)**

|                | Name           |
| -------------- | -------------- |
| using std::function< bool([delta](/_doxybook/Namespaces/namespacelava.md#using-delta))> | **[update_func](/_doxybook/Classes/structlava_1_1app.md#using-update-func)** <br>Update function.  |
| using std::function< bool()> | **[create_func](/_doxybook/Classes/structlava_1_1app.md#using-create-func)** <br>Create function.  |
| using std::function< void()> | **[destroy_func](/_doxybook/Classes/structlava_1_1app.md#using-destroy-func)** <br>Destroy function.  |
| using std::function< void(VkCommandBuffer, [index](/_doxybook/Namespaces/namespacelava.md#using-index))> | **[process_func](/_doxybook/Classes/structlava_1_1app.md#using-process-func)** <br>Process function.  |
| using std::function< bool()> | **[setup_func](/_doxybook/Classes/structlava_1_1app.md#using-setup-func)** <br>Set up function.  |

**Public Functions inherited from [lava::app](/_doxybook/Classes/structlava_1_1app.md)**

|                | Name           |
| -------------- | -------------- |
| bool | **[v_sync](/_doxybook/Classes/structlava_1_1app.md#function-v-sync)**() const<br>V-Sync setting.  |
| bool | **[triple_buffer](/_doxybook/Classes/structlava_1_1app.md#function-triple-buffer)**() const<br>Triple buffering setting.  |
| [ui32](/_doxybook/Namespaces/namespacelava.md#using-ui32) | **[fps_cap](/_doxybook/Classes/structlava_1_1app.md#function-fps-cap)**() const<br>Frames per second cap setting.  |
| [ui32](/_doxybook/Namespaces/namespacelava.md#using-ui32) | **[get_frame_counter](/_doxybook/Classes/structlava_1_1app.md#function-get-frame-counter)**() const<br>Get the frame counter.  |
| [string](/_doxybook/Namespaces/namespacelava.md#using-string) | **[get_fps_info](/_doxybook/Classes/structlava_1_1app.md#function-get-fps-info)**() const<br>Get frames per second info.  |
| void | **[draw_about](/_doxybook/Classes/structlava_1_1app.md#function-draw-about)**([about_info_setting](/_doxybook/Classes/structlava_1_1app_1_1about__info__setting.md) setting =[about_info_setting::all](/_doxybook/Classes/structlava_1_1app_1_1about__info__setting.md#function-all)()) const<br>Draw about information.  |
| [id::ref](/_doxybook/Classes/structlava_1_1id.md#using-ref) | **[block_cmd](/_doxybook/Classes/structlava_1_1app.md#function-block-cmd)**() const<br>Get id of the block command.  |
| [string](/_doxybook/Namespaces/namespacelava.md#using-string) | **[screenshot](/_doxybook/Classes/structlava_1_1app.md#function-screenshot)**()<br>Take screenshot and save it to file.  |
| void | **[switch_config](/_doxybook/Classes/structlava_1_1app.md#function-switch-config)**([string_ref](/_doxybook/Namespaces/namespacelava.md#using-string-ref) config_name) |

**Public Attributes inherited from [lava::app](/_doxybook/Classes/structlava_1_1app.md)**

|                | Name           |
| -------------- | -------------- |
| bool | **[headless](/_doxybook/Classes/structlava_1_1app.md#variable-headless)** <br>Headless mode: no window, no input, no camera, no renderer, no block, no target, no shading, no gamepad. Enable it before calling the setup method.  |
| [lava::window](/_doxybook/Classes/structlava_1_1window.md) | **[window](/_doxybook/Classes/structlava_1_1app.md#variable-window)** <br>Main window.  |
| [lava::input](/_doxybook/Classes/structlava_1_1input.md) | **[input](/_doxybook/Classes/structlava_1_1app.md#variable-input)** <br>Window input.  |
| [lava::imgui](/_doxybook/Classes/structlava_1_1imgui.md) | **[imgui](/_doxybook/Classes/structlava_1_1app.md#variable-imgui)** <br>ImGui handling.  |
| [imgui::config](/_doxybook/Classes/structlava_1_1imgui_1_1config.md) | **[imgui_config](/_doxybook/Classes/structlava_1_1app.md#variable-imgui-config)** <br>ImGui configuration.  |
| [tooltip_list](/_doxybook/Classes/structlava_1_1tooltip__list.md) | **[tooltips](/_doxybook/Classes/structlava_1_1app.md#variable-tooltips)** <br>Tooltip list.  |
| [lava::device::ptr](/_doxybook/Classes/structlava_1_1device.md#using-ptr) | **[device](/_doxybook/Classes/structlava_1_1app.md#variable-device)** <br>Vulkan device.  |
| [lava::camera](/_doxybook/Classes/structlava_1_1camera.md) | **[camera](/_doxybook/Classes/structlava_1_1app.md#variable-camera)** <br>Main camera.  |
| [gamepad](/_doxybook/Classes/structlava_1_1gamepad.md) | **[pad](/_doxybook/Classes/structlava_1_1app.md#variable-pad)** <br>Gamepad.  |
| [lava::staging](/_doxybook/Classes/structlava_1_1staging.md) | **[staging](/_doxybook/Classes/structlava_1_1app.md#variable-staging)** <br>Texture staging.  |
| [lava::block](/_doxybook/Classes/structlava_1_1block.md) | **[block](/_doxybook/Classes/structlava_1_1app.md#variable-block)** <br>Basic block.  |
| [lava::renderer](/_doxybook/Classes/structlava_1_1renderer.md) | **[renderer](/_doxybook/Classes/structlava_1_1app.md#variable-renderer)** <br>Plain renderer.  |
| [forward_shading](/_doxybook/Classes/structlava_1_1forward__shading.md) | **[shading](/_doxybook/Classes/structlava_1_1app.md#variable-shading)** <br>Forward shading.  |
| [render_target::s_ptr](/_doxybook/Classes/structlava_1_1render__target.md#using-s-ptr) | **[target](/_doxybook/Classes/structlava_1_1app.md#variable-target)** <br>Render target.  |
| [file_system](/_doxybook/Classes/structlava_1_1file__system.md) | **[fs](/_doxybook/Classes/structlava_1_1app.md#variable-fs)** <br>File system.  |
| VkPipelineCache | **[pipeline_cache](/_doxybook/Classes/structlava_1_1app.md#variable-pipeline-cache)** <br>Pipeline cache.  |
| [update_func](/_doxybook/Classes/structlava_1_1app.md#using-update-func) | **[on_update](/_doxybook/Classes/structlava_1_1app.md#variable-on-update)** <br>Function called on application update.  |
| [create_func](/_doxybook/Classes/structlava_1_1app.md#using-create-func) | **[on_create](/_doxybook/Classes/structlava_1_1app.md#variable-on-create)** <br>Function called on application create.  |
| [destroy_func](/_doxybook/Classes/structlava_1_1app.md#using-destroy-func) | **[on_destroy](/_doxybook/Classes/structlava_1_1app.md#variable-on-destroy)** <br>Function called on application destroy.  |
| [app_config](/_doxybook/Classes/structlava_1_1app__config.md) | **[config](/_doxybook/Classes/structlava_1_1app.md#variable-config)** <br>Application configuration.  |
| [json_file](/_doxybook/Classes/structlava_1_1json__file.md) | **[config_file](/_doxybook/Classes/structlava_1_1app.md#variable-config-file)** <br>Configuration file.  |
| [process_func](/_doxybook/Classes/structlava_1_1app.md#using-process-func) | **[on_process](/_doxybook/Classes/structlava_1_1app.md#variable-on-process)** <br>Function called on application process.  |
| [setup_func](/_doxybook/Classes/structlava_1_1app.md#using-setup-func) | **[on_setup](/_doxybook/Classes/structlava_1_1app.md#variable-on-setup)** <br>Function called on application setup.  |

**Public Types inherited from [lava::frame](/_doxybook/Classes/structlava_1_1frame.md)**

|                | Name           |
| -------------- | -------------- |
| using std::shared_ptr< [frame](/_doxybook/Classes/structlava_1_1frame.md) > | **[s_ptr](/_doxybook/Classes/structlava_1_1frame.md#using-s-ptr)** <br>Shared pointer to framework.  |
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
| [lava::run_time](/_doxybook/Classes/structlava_1_1run__time.md) | **[run_time](/_doxybook/Classes/structlava_1_1frame.md#variable-run-time)** <br>Run time.  |
| [lava::platform](/_doxybook/Classes/structlava_1_1platform.md) | **[platform](/_doxybook/Classes/structlava_1_1frame.md#variable-platform)** <br>Stage platform.  |
| [message_dispatcher](/_doxybook/Classes/structlava_1_1message__dispatcher.md) | **[telegraph](/_doxybook/Classes/structlava_1_1frame.md#variable-telegraph)** <br>Message dispatcher.  |

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

### using ptr

```cpp
using lava::engine::ptr =  engine*;
```


### using hud_menu_func

```cpp
using lava::engine::hud_menu_func =  std::function<void()>;
```

Hud menu function. 

## Public Functions Documentation

### function setup

```cpp
virtual bool setup() override
```

Set up the engine. 

**Return**: Setup was successful or failed 

**Reimplements**: [lava::app::setup](/_doxybook/Classes/structlava_1_1app.md#function-setup)


### function app

```cpp
explicit app(
    frame_env::ref env
)
```

App constructors. 

### function app

```cpp
explicit app(
    name name,
    argh::parser cmd_line ={}
)
```

App constructors. 

## Public Attributes Documentation

### variable props

```cpp
lava::props props;
```

Props. 

### variable producer

```cpp
lava::producer producer;
```

Producer. 

### variable on_menu

```cpp
hud_menu_func on_menu;
```

Function called on hud menu. 

### variable hud_active

```cpp
bool hud_active = false;
```

Hud active state. 

-------------------------------

Updated on 2026-02-01 at 18:13:39 +0000