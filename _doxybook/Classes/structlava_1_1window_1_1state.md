---
title: lava::window::state
summary: Window state. 

---

# lava::window::state



Window state. 


`#include <window.hpp>`

## Public Types

|                | Name           |
| -------------- | -------------- |
| using [state](/_doxybook/Classes/structlava_1_1window_1_1state.md) const  & | **[ref](/_doxybook/Classes/structlava_1_1window_1_1state.md#using-ref)** <br>Reference to window state.  |
| using std::optional< [window::state](/_doxybook/Classes/structlava_1_1window_1_1state.md) > | **[optional](/_doxybook/Classes/structlava_1_1window_1_1state.md#using-optional)** <br>Optional window state.  |

## Public Functions

|                | Name           |
| -------------- | -------------- |
| | **[state](/_doxybook/Classes/structlava_1_1window_1_1state.md#function-state)**()<br>Construct a new state.  |

## Public Attributes

|                | Name           |
| -------------- | -------------- |
| [i32](/_doxybook/Namespaces/namespacelava.md#using-i32) | **[x](/_doxybook/Classes/structlava_1_1window_1_1state.md#variable-x)** <br>Window X position.  |
| [i32](/_doxybook/Namespaces/namespacelava.md#using-i32) | **[y](/_doxybook/Classes/structlava_1_1window_1_1state.md#variable-y)** <br>Window Y position.  |
| [ui32](/_doxybook/Namespaces/namespacelava.md#using-ui32) | **[width](/_doxybook/Classes/structlava_1_1window_1_1state.md#variable-width)** <br>Window width.  |
| [ui32](/_doxybook/Namespaces/namespacelava.md#using-ui32) | **[height](/_doxybook/Classes/structlava_1_1window_1_1state.md#variable-height)** <br>Window height.  |
| bool | **[fullscreen](/_doxybook/Classes/structlava_1_1window_1_1state.md#variable-fullscreen)** <br>Fullscreen window.  |
| bool | **[floating](/_doxybook/Classes/structlava_1_1window_1_1state.md#variable-floating)** <br>Floating window.  |
| bool | **[resizable](/_doxybook/Classes/structlava_1_1window_1_1state.md#variable-resizable)** <br>Resizable window.  |
| bool | **[decorated](/_doxybook/Classes/structlava_1_1window_1_1state.md#variable-decorated)** <br>Decorated window.  |
| bool | **[maximized](/_doxybook/Classes/structlava_1_1window_1_1state.md#variable-maximized)** <br>Maximized window.  |
| [index](/_doxybook/Namespaces/namespacelava.md#using-index) | **[monitor](/_doxybook/Classes/structlava_1_1window_1_1state.md#variable-monitor)** <br>Monitor of window.  |

## Public Types Documentation

### using ref

```cpp
using lava::window::state::ref =  state const&;
```

Reference to window state. 

### using optional

```cpp
using lava::window::state::optional =  std::optional<window::state>;
```

Optional window state. 

## Public Functions Documentation

### function state

```cpp
inline explicit state()
```

Construct a new state. 

## Public Attributes Documentation

### variable x

```cpp
i32 x = 0;
```

Window X position. 

### variable y

```cpp
i32 y = 0;
```

Window Y position. 

### variable width

```cpp
ui32 width = 0;
```

Window width. 

### variable height

```cpp
ui32 height = 0;
```

Window height. 

### variable fullscreen

```cpp
bool fullscreen = false;
```

Fullscreen window. 

### variable floating

```cpp
bool floating = false;
```

Floating window. 

### variable resizable

```cpp
bool resizable = true;
```

Resizable window. 

### variable decorated

```cpp
bool decorated = true;
```

Decorated window. 

### variable maximized

```cpp
bool maximized = false;
```

Maximized window. 

### variable monitor

```cpp
index monitor = 0;
```

Monitor of window. 

-------------------------------

Updated on 2026-02-01 at 18:13:39 +0000