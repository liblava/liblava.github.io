---
title: lava::imgui::font
summary: ImGui font settings. 

---

# lava::imgui::font



ImGui font settings. 


`#include <imgui.hpp>`

## Public Types

|                | Name           |
| -------------- | -------------- |
| using [font](/_doxybook/Classes/structlava_1_1imgui_1_1font.md) const  & | **[ref](/_doxybook/Classes/structlava_1_1imgui_1_1font.md#using-ref)** <br>Const font reference.  |

## Public Attributes

|                | Name           |
| -------------- | -------------- |
| [string](/_doxybook/Namespaces/namespacelava.md#using-string) | **[file](/_doxybook/Classes/structlava_1_1imgui_1_1font.md#variable-file)** <br>Font file.  |
| [r32](/_doxybook/Namespaces/namespacelava.md#using-r32) | **[size](/_doxybook/Classes/structlava_1_1imgui_1_1font.md#variable-size)** <br>Font size.  |
| [string](/_doxybook/Namespaces/namespacelava.md#using-string) | **[icon_file](/_doxybook/Classes/structlava_1_1imgui_1_1font.md#variable-icon-file)** <br>Font icon file.  |
| [r32](/_doxybook/Namespaces/namespacelava.md#using-r32) | **[icon_size](/_doxybook/Classes/structlava_1_1imgui_1_1font.md#variable-icon-size)** <br>Font icon size.  |
| [ui16](/_doxybook/Namespaces/namespacelava.md#using-ui16) | **[icon_range_begin](/_doxybook/Classes/structlava_1_1imgui_1_1font.md#variable-icon-range-begin)** <br>Font range begin.  |
| [ui16](/_doxybook/Namespaces/namespacelava.md#using-ui16) | **[icon_range_end](/_doxybook/Classes/structlava_1_1imgui_1_1font.md#variable-icon-range-end)** <br>Font range end.  |

## Public Types Documentation

### using ref

```cpp
using lava::imgui::font::ref =  font const&;
```

Const font reference. 

## Public Attributes Documentation

### variable file

```cpp
string file;
```

Font file. 

### variable size

```cpp
r32 size = 21.f;
```

Font size. 

### variable icon_file

```cpp
string icon_file;
```

Font icon file. 

### variable icon_size

```cpp
r32 icon_size = 21.f;
```

Font icon size. 

### variable icon_range_begin

```cpp
ui16 icon_range_begin = 0;
```

Font range begin. 

### variable icon_range_end

```cpp
ui16 icon_range_end = 0;
```

Font range end. 

-------------------------------

Updated on 2026-02-01 at 18:13:39 +0000