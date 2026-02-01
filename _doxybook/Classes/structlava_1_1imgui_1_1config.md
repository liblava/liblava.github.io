---
title: lava::imgui::config
summary: ImGui configuration. 

---

# lava::imgui::config



ImGui configuration. 


`#include <imgui.hpp>`

## Public Attributes

|                | Name           |
| -------------- | -------------- |
| [data](/_doxybook/Classes/structlava_1_1data.md) | **[font_data](/_doxybook/Classes/structlava_1_1imgui_1_1config.md#variable-font-data)** <br>Font data.  |
| [r32](/_doxybook/Namespaces/namespacelava.md#using-r32) | **[font_size](/_doxybook/Classes/structlava_1_1imgui_1_1config.md#variable-font-size)** <br>Font size.  |
| std::shared_ptr< ImGuiStyle > | **[style](/_doxybook/Classes/structlava_1_1imgui_1_1config.md#variable-style)** <br>Font style.  |
| [icon_font](/_doxybook/Classes/structlava_1_1imgui_1_1icon__font.md) | **[icon](/_doxybook/Classes/structlava_1_1imgui_1_1config.md#variable-icon)** <br>Font icon settings.  |
| std::filesystem::path | **[ini_file_dir](/_doxybook/Classes/structlava_1_1imgui_1_1config.md#variable-ini-file-dir)** <br>ImGui state file path.  |
| [i32](/_doxybook/Namespaces/namespacelava.md#using-i32) | **[flags](/_doxybook/Classes/structlava_1_1imgui_1_1config.md#variable-flags)** <br>ImGuiConfigFlags.  |

## Public Attributes Documentation

### variable font_data

```cpp
data font_data;
```

Font data. 

### variable font_size

```cpp
r32 font_size = default_imgui_font_size;
```

Font size. 

### variable style

```cpp
std::shared_ptr< ImGuiStyle > style;
```

Font style. 

### variable icon

```cpp
icon_font icon;
```

Font icon settings. 

### variable ini_file_dir

```cpp
std::filesystem::path ini_file_dir;
```

ImGui state file path. 

### variable flags

```cpp
i32 flags = 0;
```

ImGuiConfigFlags. 

-------------------------------

Updated on 2026-02-01 at 18:13:39 +0000