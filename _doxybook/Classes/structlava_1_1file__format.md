---
title: lava::file_format
summary: File format. 

---

# lava::file_format



File format. 


`#include <texture.hpp>`

## Public Types

|                | Name           |
| -------------- | -------------- |
| using std::vector< [file_format](/_doxybook/Classes/structlava_1_1file__format.md) > | **[list](/_doxybook/Classes/structlava_1_1file__format.md#using-list)** <br>List of file formats.  |

## Public Attributes

|                | Name           |
| -------------- | -------------- |
| [string](/_doxybook/Namespaces/namespacelava.md#using-string) | **[path](/_doxybook/Classes/structlava_1_1file__format.md#variable-path)** <br>File path.  |
| VkFormat | **[format](/_doxybook/Classes/structlava_1_1file__format.md#variable-format)** <br>File format.  |

## Public Types Documentation

### using list

```cpp
using lava::file_format::list =  std::vector<file_format>;
```

List of file formats. 

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

Updated on 2022-11-30 at 01:16:03 +0000