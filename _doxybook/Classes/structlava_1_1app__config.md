---
title: lava::app_config
summary: Application configuration. 

---

# lava::app_config



Application configuration. 


`#include <config.hpp>`

Inherits from [lava::configurable](/_doxybook/Classes/structlava_1_1configurable.md), [lava::interface](/_doxybook/Classes/structlava_1_1interface.md)

## Public Functions

|                | Name           |
| -------------- | -------------- |
| virtual void | **[set_json](/_doxybook/Classes/structlava_1_1app__config.md#function-set-json)**(json_ref j) override |
| virtual json | **[get_json](/_doxybook/Classes/structlava_1_1app__config.md#function-get-json)**() const override |
| void | **[update_window_state](/_doxybook/Classes/structlava_1_1app__config.md#function-update-window-state)**()<br>Update window state.  |

## Public Attributes

|                | Name           |
| -------------- | -------------- |
| [app](/_doxybook/Classes/structlava_1_1app.md) * | **[context](/_doxybook/Classes/structlava_1_1app__config.md#variable-context)** <br>Application.  |
| [name](/_doxybook/Namespaces/namespacelava.md#using-name) | **[org](/_doxybook/Classes/structlava_1_1app__config.md#variable-org)** <br>Organization name.  |
| [name](/_doxybook/Namespaces/namespacelava.md#using-name) | **[ext](/_doxybook/Classes/structlava_1_1app__config.md#variable-ext)** <br>Preferred compression file format.  |
| bool | **[save_window](/_doxybook/Classes/structlava_1_1app__config.md#variable-save-window)** <br>Save window state.  |
| bool | **[handle_key_events](/_doxybook/Classes/structlava_1_1app__config.md#variable-handle-key-events)** <br>Handle key events.  |
| bool | **[v_sync](/_doxybook/Classes/structlava_1_1app__config.md#variable-v-sync)** <br>Activate V-Sync.  |
| bool | **[triple_buffer](/_doxybook/Classes/structlava_1_1app__config.md#variable-triple-buffer)** <br>Prefer VK_PRESENT_MODE_MAILBOX_KHR over VK_PRESENT_MODE_IMMEDIATE_KHR.  |
| [ui32](/_doxybook/Namespaces/namespacelava.md#using-ui32) | **[fps_cap](/_doxybook/Classes/structlava_1_1app__config.md#variable-fps-cap)** <br>Frames per second cap.  |
| [surface_format_request](/_doxybook/Classes/structlava_1_1surface__format__request.md) | **[surface](/_doxybook/Classes/structlava_1_1app__config.md#variable-surface)** <br>Request surface formats.  |
| [index](/_doxybook/Namespaces/namespacelava.md#using-index) | **[physical_device](/_doxybook/Classes/structlava_1_1app__config.md#variable-physical-device)** <br>Physical device index.  |
| [imgui::font](/_doxybook/Classes/structlava_1_1imgui_1_1font.md) | **[imgui_font](/_doxybook/Classes/structlava_1_1app__config.md#variable-imgui-font)** <br>ImGui font settings.  |
| [string](/_doxybook/Namespaces/namespacelava.md#using-string) | **[name_id](/_doxybook/Classes/structlava_1_1app__config.md#variable-name-id)** <br>Identification.  |
| [window::state::optional](/_doxybook/Classes/structlava_1_1window_1_1state.md#using-optional) | **[window_state](/_doxybook/Classes/structlava_1_1app__config.md#variable-window-state)** <br>Window state if available.  |

## Additional inherited members

**Public Functions inherited from [lava::interface](/_doxybook/Classes/structlava_1_1interface.md)**

|                | Name           |
| -------------- | -------------- |
| virtual | **[~interface](/_doxybook/Classes/structlava_1_1interface.md#function-~interface)**() =default<br>Destroy the interface.  |


## Public Functions Documentation

### function set_json

```cpp
virtual void set_json(
    json_ref j
) override
```


**See**: [configurable::set_json](/_doxybook/Classes/structlava_1_1configurable.md#function-set-json)

**Reimplements**: [lava::configurable::set_json](/_doxybook/Classes/structlava_1_1configurable.md#function-set-json)


### function get_json

```cpp
virtual json get_json() const override
```


**See**: [configurable::get_json](/_doxybook/Classes/structlava_1_1configurable.md#function-get-json)

**Reimplements**: [lava::configurable::get_json](/_doxybook/Classes/structlava_1_1configurable.md#function-get-json)


### function update_window_state

```cpp
void update_window_state()
```

Update window state. 

## Public Attributes Documentation

### variable context

```cpp
app * context = nullptr;
```

Application. 

### variable org

```cpp
name org = _liblava_;
```

Organization name. 

### variable ext

```cpp
name ext = "zip";
```

Preferred compression file format. 

### variable save_window

```cpp
bool save_window = true;
```

Save window state. 

### variable handle_key_events

```cpp
bool handle_key_events = true;
```

Handle key events. 

### variable v_sync

```cpp
bool v_sync = false;
```

Activate V-Sync. 

### variable triple_buffer

```cpp
bool triple_buffer = true;
```

Prefer VK_PRESENT_MODE_MAILBOX_KHR over VK_PRESENT_MODE_IMMEDIATE_KHR. 

### variable fps_cap

```cpp
ui32 fps_cap = 0;
```

Frames per second cap. 

### variable surface

```cpp
surface_format_request surface;
```

Request surface formats. 

### variable physical_device

```cpp
index physical_device = 0;
```

Physical device index. 

### variable imgui_font

```cpp
imgui::font imgui_font;
```

ImGui font settings. 

### variable name_id

```cpp
string name_id = _default_;
```

Identification. 

### variable window_state

```cpp
window::state::optional window_state;
```

Window state if available. 

-------------------------------

Updated on 2026-02-01 at 18:13:39 +0000