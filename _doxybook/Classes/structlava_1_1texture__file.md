---
title: lava::texture_file
summary: Texture file path with format. 

---

# lava::texture_file



Texture file path with format. 


`#include <texture.hpp>`

## Public Types

|                | Name           |
| -------------- | -------------- |
| using std::vector< [texture_file](/_doxybook/Classes/structlava_1_1texture__file.md) > | **[list](/_doxybook/Classes/structlava_1_1texture__file.md#using-list)** <br>List of texture files.  |

## Public Attributes

|                | Name           |
| -------------- | -------------- |
| [string](/_doxybook/Namespaces/namespacelava.md#using-string) | **[path](/_doxybook/Classes/structlava_1_1texture__file.md#variable-path)** <br>File path.  |
| VkFormat | **[format](/_doxybook/Classes/structlava_1_1texture__file.md#variable-format)** <br>File format.  |

## Public Types Documentation

### using list

```cpp
using lava::texture_file::list =  std::vector<texture_file>;
```

List of texture files. 

## Public Attributes Documentation

### variable path

```cpp
string path;
```

File path. 

### variable format

```cpp
VkFormat format = VK_FORMAT_UNDEFINED;
```

File format. 

-------------------------------

Updated on 2026-02-01 at 18:13:39 +0000