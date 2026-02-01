---
title: lava::window
summary: Window. 

---

# lava::window



Window. 


`#include <window.hpp>`

Inherits from [lava::entity](/_doxybook/Classes/structlava_1_1entity.md), [lava::no_copy_no_move](/_doxybook/Classes/structlava_1_1no__copy__no__move.md), [lava::interface](/_doxybook/Classes/structlava_1_1interface.md)

## Public Classes

|                | Name           |
| -------------- | -------------- |
| struct | **[state](/_doxybook/Classes/structlava_1_1window_1_1state.md)** <br>Window state.  |

## Public Types

|                | Name           |
| -------------- | -------------- |
| using [window](/_doxybook/Classes/structlava_1_1window.md) * | **[ptr](/_doxybook/Classes/structlava_1_1window.md#using-ptr)** <br>Pointer to window.  |
| using std::shared_ptr< [window](/_doxybook/Classes/structlava_1_1window.md) > | **[s_ptr](/_doxybook/Classes/structlava_1_1window.md#using-s-ptr)** <br>Shared pointer to window.  |
| using std::function< void([s_ptr](/_doxybook/Classes/structlava_1_1window.md#using-s-ptr))> | **[event](/_doxybook/Classes/structlava_1_1window.md#using-event)** <br>Window event function.  |
| using std::map< [id](/_doxybook/Classes/structlava_1_1id.md), [s_ptr](/_doxybook/Classes/structlava_1_1window.md#using-s-ptr) > | **[s_map](/_doxybook/Classes/structlava_1_1window.md#using-s-map)** <br>Map of windows.  |
| using [window](/_doxybook/Classes/structlava_1_1window.md) const  & | **[ref](/_doxybook/Classes/structlava_1_1window.md#using-ref)** <br>Reference to window.  |
| using std::function< bool([ui32](/_doxybook/Namespaces/namespacelava.md#using-ui32), [ui32](/_doxybook/Namespaces/namespacelava.md#using-ui32))> | **[resize_func](/_doxybook/Classes/structlava_1_1window.md#using-resize-func)** <br>Resize window function.  |

## Public Functions

|                | Name           |
| -------------- | -------------- |
| | **[window](/_doxybook/Classes/structlava_1_1window.md#function-window)**() =default<br>Construct a new window.  |
| | **[window](/_doxybook/Classes/structlava_1_1window.md#function-window)**([name](/_doxybook/Namespaces/namespacelava.md#using-name) title)<br>Construct a new window.  |
| bool | **[create](/_doxybook/Classes/structlava_1_1window.md#function-create)**([state::optional](/_doxybook/Classes/structlava_1_1window_1_1state.md#using-optional) state ={})<br>Create a new window with optional state.  |
| void | **[destroy](/_doxybook/Classes/structlava_1_1window.md#function-destroy)**()<br>Destroy the window.  |
| [state](/_doxybook/Classes/structlava_1_1window_1_1state.md) | **[get_state](/_doxybook/Classes/structlava_1_1window.md#function-get-state)**() const<br>Get the window state.  |
| void | **[set_state](/_doxybook/Classes/structlava_1_1window.md#function-set-state)**([state](/_doxybook/Classes/structlava_1_1window_1_1state.md) & s)<br>Set the window state.  |
| void | **[set_title](/_doxybook/Classes/structlava_1_1window.md#function-set-title)**([string_ref](/_doxybook/Namespaces/namespacelava.md#using-string-ref) text)<br>Set the window title.  |
| [string_ref](/_doxybook/Namespaces/namespacelava.md#using-string-ref) | **[get_title](/_doxybook/Classes/structlava_1_1window.md#function-get-title)**() const<br>Get the window title.  |
| void | **[set_save_name](/_doxybook/Classes/structlava_1_1window.md#function-set-save-name)**([string_ref](/_doxybook/Namespaces/namespacelava.md#using-string-ref) save)<br>Set the save name.  |
| [string_ref](/_doxybook/Namespaces/namespacelava.md#using-string-ref) | **[get_save_name](/_doxybook/Classes/structlava_1_1window.md#function-get-save-name)**() const<br>Get the save name.  |
| void | **[set_position](/_doxybook/Classes/structlava_1_1window.md#function-set-position)**([i32](/_doxybook/Namespaces/namespacelava.md#using-i32) x, [i32](/_doxybook/Namespaces/namespacelava.md#using-i32) y)<br>Set the position of window.  |
| void | **[get_position](/_doxybook/Classes/structlava_1_1window.md#function-get-position)**([i32](/_doxybook/Namespaces/namespacelava.md#using-i32) & x, [i32](/_doxybook/Namespaces/namespacelava.md#using-i32) & y) const<br>Get the position of window.  |
| void | **[set_size](/_doxybook/Classes/structlava_1_1window.md#function-set-size)**([ui32](/_doxybook/Namespaces/namespacelava.md#using-ui32) width, [ui32](/_doxybook/Namespaces/namespacelava.md#using-ui32) height)<br>Set the size of window.  |
| void | **[get_size](/_doxybook/Classes/structlava_1_1window.md#function-get-size)**([ui32](/_doxybook/Namespaces/namespacelava.md#using-ui32) & width, [ui32](/_doxybook/Namespaces/namespacelava.md#using-ui32) & height) const<br>Get the size of window.  |
| void | **[get_framebuffer_size](/_doxybook/Classes/structlava_1_1window.md#function-get-framebuffer-size)**([ui32](/_doxybook/Namespaces/namespacelava.md#using-ui32) & width, [ui32](/_doxybook/Namespaces/namespacelava.md#using-ui32) & height) const<br>Get the framebuffer size.  |
| [uv2](/_doxybook/Namespaces/namespacelava.md#using-uv2) | **[get_size](/_doxybook/Classes/structlava_1_1window.md#function-get-size)**() const<br>Get the size.  |
| [uv2](/_doxybook/Namespaces/namespacelava.md#using-uv2) | **[get_framebuffer_size](/_doxybook/Classes/structlava_1_1window.md#function-get-framebuffer-size)**() const<br>Get the framebuffer size.  |
| void | **[set_mouse_position](/_doxybook/Classes/structlava_1_1window.md#function-set-mouse-position)**([r64](/_doxybook/Namespaces/namespacelava.md#using-r64) x, [r64](/_doxybook/Namespaces/namespacelava.md#using-r64) y)<br>Set the mouse position.  |
| void | **[get_mouse_position](/_doxybook/Classes/structlava_1_1window.md#function-get-mouse-position)**([r64](/_doxybook/Namespaces/namespacelava.md#using-r64) & x, [r64](/_doxybook/Namespaces/namespacelava.md#using-r64) & y) const<br>Get the mouse position.  |
| [v2](/_doxybook/Namespaces/namespacelava.md#using-v2) | **[get_content_scale](/_doxybook/Classes/structlava_1_1window.md#function-get-content-scale)**() const<br>Get the content scale.  |
| [mouse_position](/_doxybook/Classes/structlava_1_1mouse__position.md) | **[get_mouse_position](/_doxybook/Classes/structlava_1_1window.md#function-get-mouse-position)**() const<br>Get the mouse position in window.  |
| void | **[hide_mouse_cursor](/_doxybook/Classes/structlava_1_1window.md#function-hide-mouse-cursor)**()<br>Hide mouse cursor.  |
| void | **[show_mouse_cursor](/_doxybook/Classes/structlava_1_1window.md#function-show-mouse-cursor)**()<br>Show mouse cursor.  |
| [r32](/_doxybook/Namespaces/namespacelava.md#using-r32) | **[get_aspect_ratio](/_doxybook/Classes/structlava_1_1window.md#function-get-aspect-ratio)**() const<br>Get the aspect ratio of window.  |
| void | **[show](/_doxybook/Classes/structlava_1_1window.md#function-show)**()<br>Show the window.  |
| void | **[hide](/_doxybook/Classes/structlava_1_1window.md#function-hide)**()<br>Hide the window.  |
| bool | **[visible](/_doxybook/Classes/structlava_1_1window.md#function-visible)**() const<br>Check if window is visible.  |
| void | **[iconify](/_doxybook/Classes/structlava_1_1window.md#function-iconify)**()<br>Iconify the window.  |
| bool | **[iconified](/_doxybook/Classes/structlava_1_1window.md#function-iconified)**() const<br>Check if the window is iconified.  |
| void | **[restore](/_doxybook/Classes/structlava_1_1window.md#function-restore)**()<br>Restore the window.  |
| void | **[maximize](/_doxybook/Classes/structlava_1_1window.md#function-maximize)**()<br>Maximize the window.  |
| bool | **[maximized](/_doxybook/Classes/structlava_1_1window.md#function-maximized)**() const<br>Check if the window is maximized.  |
| void | **[focus](/_doxybook/Classes/structlava_1_1window.md#function-focus)**()<br>Focus the window.  |
| bool | **[focused](/_doxybook/Classes/structlava_1_1window.md#function-focused)**() const<br>Check if the window is focused.  |
| void | **[set_fullscreen](/_doxybook/Classes/structlava_1_1window.md#function-set-fullscreen)**(bool active)<br>Set the window to fullscreen.  |
| bool | **[fullscreen](/_doxybook/Classes/structlava_1_1window.md#function-fullscreen)**() const<br>Check if the window is fullscreen.  |
| bool | **[hovered](/_doxybook/Classes/structlava_1_1window.md#function-hovered)**() const<br>Check if mouse hovered over the window.  |
| bool | **[resizable](/_doxybook/Classes/structlava_1_1window.md#function-resizable)**() const<br>Check if the window is resizable.  |
| void | **[set_resizable](/_doxybook/Classes/structlava_1_1window.md#function-set-resizable)**(bool value)<br>Set the window resizable.  |
| bool | **[decorated](/_doxybook/Classes/structlava_1_1window.md#function-decorated)**() const<br>Check if the window is decorated.  |
| void | **[set_decorated](/_doxybook/Classes/structlava_1_1window.md#function-set-decorated)**(bool value)<br>Set the window decorated.  |
| bool | **[floating](/_doxybook/Classes/structlava_1_1window.md#function-floating)**() const<br>Check if the window is floating.  |
| void | **[set_floating](/_doxybook/Classes/structlava_1_1window.md#function-set-floating)**(bool value)<br>Set the window floating.  |
| bool | **[close_request](/_doxybook/Classes/structlava_1_1window.md#function-close-request)**() const<br>Check if the window request to close.  |
| bool | **[switch_mode_request](/_doxybook/Classes/structlava_1_1window.md#function-switch-mode-request)**() const<br>Check if the window request to switch mode.  |
| bool | **[switch_mode](/_doxybook/Classes/structlava_1_1window.md#function-switch-mode)**([state::optional](/_doxybook/Classes/structlava_1_1window_1_1state.md#using-optional) state ={})<br>Switch mode of the window.  |
| GLFWwindow * | **[get](/_doxybook/Classes/structlava_1_1window.md#function-get)**() const<br>Get GLFW handle.  |
| bool | **[resize_request](/_doxybook/Classes/structlava_1_1window.md#function-resize-request)**() const<br>Check if the window request to resize.  |
| bool | **[handle_resize](/_doxybook/Classes/structlava_1_1window.md#function-handle-resize)**()<br>Handle window resize.  |
| void | **[update_state](/_doxybook/Classes/structlava_1_1window.md#function-update-state)**()<br>Update window state.  |
| void | **[assign](/_doxybook/Classes/structlava_1_1window.md#function-assign)**([input::ptr](/_doxybook/Classes/structlava_1_1input.md#using-ptr) callback)<br>Assign input callback.  |
| void | **[show_save_title](/_doxybook/Classes/structlava_1_1window.md#function-show-save-title)**(bool value =true)<br>Show the save title in the window.  |
| bool | **[save_title](/_doxybook/Classes/structlava_1_1window.md#function-save-title)**() const<br>Check the show save title state.  |
| void | **[update_title](/_doxybook/Classes/structlava_1_1window.md#function-update-title)**()<br>Update the window title.  |
| VkSurfaceKHR | **[create_surface](/_doxybook/Classes/structlava_1_1window.md#function-create-surface)**()<br>Create a surface.  |
| void | **[set_icon](/_doxybook/Classes/structlava_1_1window.md#function-set-icon)**([data::c_ptr](/_doxybook/Classes/structlava_1_1data.md#using-c-ptr) data, [uv2](/_doxybook/Namespaces/namespacelava.md#using-uv2) size)<br>Set the window icon.  |
| [index](/_doxybook/Namespaces/namespacelava.md#using-index) | **[detect_monitor](/_doxybook/Classes/structlava_1_1window.md#function-detect-monitor)**() const<br>Detect the monitor index of the window.  |
| void | **[center](/_doxybook/Classes/structlava_1_1window.md#function-center)**()<br>Center the window on the monitor.  |

## Public Attributes

|                | Name           |
| -------------- | -------------- |
| [resize_func](/_doxybook/Classes/structlava_1_1window.md#using-resize-func) | **[on_resize](/_doxybook/Classes/structlava_1_1window.md#variable-on-resize)** <br>Called on window resize.  |

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
using lava::window::ptr =  window*;
```

Pointer to window. 

### using s_ptr

```cpp
using lava::window::s_ptr =  std::shared_ptr<window>;
```

Shared pointer to window. 

### using event

```cpp
using lava::window::event =  std::function<void(s_ptr)>;
```

Window event function. 

### using s_map

```cpp
using lava::window::s_map =  std::map<id, s_ptr>;
```

Map of windows. 

### using ref

```cpp
using lava::window::ref =  window const&;
```

Reference to window. 

### using resize_func

```cpp
using lava::window::resize_func =  std::function<bool(ui32, ui32)>;
```

Resize window function. 

## Public Functions Documentation

### function window

```cpp
window() =default
```

Construct a new window. 

### function window

```cpp
inline explicit window(
    name title
)
```

Construct a new window. 

**Parameters**: 

  * **title** Title of window 


### function create

```cpp
bool create(
    state::optional state ={}
)
```

Create a new window with optional state. 

**Parameters**: 

  * **state** Window state 


**Return**: Create was successful or failed 

### function destroy

```cpp
void destroy()
```

Destroy the window. 

### function get_state

```cpp
state get_state() const
```

Get the window state. 

**Return**: state Window state 

### function set_state

```cpp
void set_state(
    state & s
)
```

Set the window state. 

**Parameters**: 

  * **s** Window state 


### function set_title

```cpp
void set_title(
    string_ref text
)
```

Set the window title. 

**Parameters**: 

  * **text** Title of window 


### function get_title

```cpp
inline string_ref get_title() const
```

Get the window title. 

**Return**: name Title of window 

### function set_save_name

```cpp
inline void set_save_name(
    string_ref save
)
```

Set the save name. 

**Parameters**: 

  * **save** Save name of window 


### function get_save_name

```cpp
inline string_ref get_save_name() const
```

Get the save name. 

**Return**: name Save name of window 

### function set_position

```cpp
void set_position(
    i32 x,
    i32 y
)
```

Set the position of window. 

**Parameters**: 

  * **x** X positoin 
  * **y** Y position 


### function get_position

```cpp
void get_position(
    i32 & x,
    i32 & y
) const
```

Get the position of window. 

**Parameters**: 

  * **x** X position 
  * **y** Y position 


### function set_size

```cpp
void set_size(
    ui32 width,
    ui32 height
)
```

Set the size of window. 

**Parameters**: 

  * **width** Window width 
  * **height** Window height 


### function get_size

```cpp
void get_size(
    ui32 & width,
    ui32 & height
) const
```

Get the size of window. 

**Parameters**: 

  * **width** Window width 
  * **height** Window height 


### function get_framebuffer_size

```cpp
void get_framebuffer_size(
    ui32 & width,
    ui32 & height
) const
```

Get the framebuffer size. 

**Parameters**: 

  * **width** Framebuffer width 
  * **height** Framebuffer height 


### function get_size

```cpp
uv2 get_size() const
```

Get the size. 

**Return**: [uv2](/_doxybook/Namespaces/namespacelava.md#using-uv2) Size of window 

### function get_framebuffer_size

```cpp
uv2 get_framebuffer_size() const
```

Get the framebuffer size. 

**Return**: [uv2](/_doxybook/Namespaces/namespacelava.md#using-uv2) Size of framebuffer 

### function set_mouse_position

```cpp
void set_mouse_position(
    r64 x,
    r64 y
)
```

Set the mouse position. 

**Parameters**: 

  * **x** Mouse X position 
  * **y** Mouse Y position 


### function get_mouse_position

```cpp
void get_mouse_position(
    r64 & x,
    r64 & y
) const
```

Get the mouse position. 

**Parameters**: 

  * **x** Mouse X position 
  * **y** Mouse Y position 


### function get_content_scale

```cpp
v2 get_content_scale() const
```

Get the content scale. 

**Return**: [v2](/_doxybook/Namespaces/namespacelava.md#using-v2) Window content scale 

### function get_mouse_position

```cpp
mouse_position get_mouse_position() const
```

Get the mouse position in window. 

**Return**: [mouse_position](/_doxybook/Classes/structlava_1_1mouse__position.md) Position of mouse 

### function hide_mouse_cursor

```cpp
void hide_mouse_cursor()
```

Hide mouse cursor. 

### function show_mouse_cursor

```cpp
void show_mouse_cursor()
```

Show mouse cursor. 

### function get_aspect_ratio

```cpp
r32 get_aspect_ratio() const
```

Get the aspect ratio of window. 

**Return**: [r32](/_doxybook/Namespaces/namespacelava.md#using-r32) Aspect ratio 

### function show

```cpp
void show()
```

Show the window. 

### function hide

```cpp
void hide()
```

Hide the window. 

### function visible

```cpp
bool visible() const
```

Check if window is visible. 

**Return**: Window is visible or not 

### function iconify

```cpp
void iconify()
```

Iconify the window. 

### function iconified

```cpp
bool iconified() const
```

Check if the window is iconified. 

**Return**: Window is iconified or not 

### function restore

```cpp
void restore()
```

Restore the window. 

### function maximize

```cpp
void maximize()
```

Maximize the window. 

### function maximized

```cpp
bool maximized() const
```

Check if the window is maximized. 

**Return**: Window is maximized or not 

### function focus

```cpp
void focus()
```

Focus the window. 

### function focused

```cpp
bool focused() const
```

Check if the window is focused. 

**Return**: Window is focused or not 

### function set_fullscreen

```cpp
inline void set_fullscreen(
    bool active
)
```

Set the window to fullscreen. 

**Parameters**: 

  * **active** Fullscreen or windowed mode 


### function fullscreen

```cpp
inline bool fullscreen() const
```

Check if the window is fullscreen. 

**Return**: Window is fullscreen or not 

### function hovered

```cpp
bool hovered() const
```

Check if mouse hovered over the window. 

**Return**: Mouse hovered or not 

### function resizable

```cpp
bool resizable() const
```

Check if the window is resizable. 

**Return**: Window is resizable or not 

### function set_resizable

```cpp
void set_resizable(
    bool value
)
```

Set the window resizable. 

**Parameters**: 

  * **value** Resizable state 


### function decorated

```cpp
bool decorated() const
```

Check if the window is decorated. 

**Return**: Window is decorated or not 

### function set_decorated

```cpp
void set_decorated(
    bool value
)
```

Set the window decorated. 

**Parameters**: 

  * **value** Decorated state 


### function floating

```cpp
bool floating() const
```

Check if the window is floating. 

**Return**: Window is floating or not 

### function set_floating

```cpp
void set_floating(
    bool value
)
```

Set the window floating. 

**Parameters**: 

  * **value** Floating state 


### function close_request

```cpp
bool close_request() const
```

Check if the window request to close. 

**Return**: Window has close request or not 

### function switch_mode_request

```cpp
inline bool switch_mode_request() const
```

Check if the window request to switch mode. 

**Return**: Window has switch mode request or not 

### function switch_mode

```cpp
bool switch_mode(
    state::optional state ={}
)
```

Switch mode of the window. 

**Parameters**: 

  * **state** Target window state 


**Return**: Switch was successful or failed 

### function get

```cpp
inline GLFWwindow * get() const
```

Get GLFW handle. 

**Return**: GLFWwindow* GLFW window handle 

### function resize_request

```cpp
inline bool resize_request() const
```

Check if the window request to resize. 

**Return**: Window has resize request or not 

### function handle_resize

```cpp
inline bool handle_resize()
```

Handle window resize. 

**Return**: Resize was successful or failed 

### function update_state

```cpp
inline void update_state()
```

Update window state. 

### function assign

```cpp
inline void assign(
    input::ptr callback
)
```

Assign input callback. 

**Parameters**: 

  * **callback** Input callbacl 


### function show_save_title

```cpp
inline void show_save_title(
    bool value =true
)
```

Show the save title in the window. 

**Parameters**: 

  * **value** Save title state 


### function save_title

```cpp
inline bool save_title() const
```

Check the show save title state. 

**Return**: Save title is active or not 

### function update_title

```cpp
inline void update_title()
```

Update the window title. 

### function create_surface

```cpp
VkSurfaceKHR create_surface()
```

Create a surface. 

**Return**: VkSurfaceKHR Vulkan surface 

### function set_icon

```cpp
void set_icon(
    data::c_ptr data,
    uv2 size
)
```

Set the window icon. 

**Parameters**: 

  * **data** Image data 
  * **size** Image size 


### function detect_monitor

```cpp
index detect_monitor() const
```

Detect the monitor index of the window. 

**Return**: index Monitor index 

### function center

```cpp
void center()
```

Center the window on the monitor. 

## Public Attributes Documentation

### variable on_resize

```cpp
resize_func on_resize;
```

Called on window resize. 

-------------------------------

Updated on 2026-02-01 at 18:13:39 +0000