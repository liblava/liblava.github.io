---
title: lava::path_drop_event
summary: Path drop event. 

---

# lava::path_drop_event



Path drop event. 


`#include <input.hpp>`

## Public Types

|                | Name           |
| -------------- | -------------- |
| using [path_drop_event](/_doxybook/Classes/structlava_1_1path__drop__event.md) const  & | **[ref](/_doxybook/Classes/structlava_1_1path__drop__event.md#using-ref)** <br>Reference to path drop event.  |
| using std::function< bool([ref](/_doxybook/Classes/structlava_1_1path__drop__event.md#using-ref))> | **[func](/_doxybook/Classes/structlava_1_1path__drop__event.md#using-func)** <br>Path drop event function.  |
| using std::map< [id](/_doxybook/Classes/structlava_1_1id.md), [func](/_doxybook/Classes/structlava_1_1path__drop__event.md#using-func) > | **[listeners](/_doxybook/Classes/structlava_1_1path__drop__event.md#using-listeners)** <br>List of path drop event listeners.  |
| using std::vector< [path_drop_event](/_doxybook/Classes/structlava_1_1path__drop__event.md) > | **[list](/_doxybook/Classes/structlava_1_1path__drop__event.md#using-list)** <br>List of path drop events.  |

## Public Attributes

|                | Name           |
| -------------- | -------------- |
| [id](/_doxybook/Classes/structlava_1_1id.md) | **[sender](/_doxybook/Classes/structlava_1_1path__drop__event.md#variable-sender)** <br>Sender id.  |
| [string_list](/_doxybook/Namespaces/namespacelava.md#using-string-list) | **[files](/_doxybook/Classes/structlava_1_1path__drop__event.md#variable-files)** <br>List of files.  |

## Public Types Documentation

### using ref

```cpp
using lava::path_drop_event::ref =  path_drop_event const&;
```

Reference to path drop event. 

### using func

```cpp
using lava::path_drop_event::func =  std::function<bool(ref)>;
```

Path drop event function. 

### using listeners

```cpp
using lava::path_drop_event::listeners =  std::map<id, func>;
```

List of path drop event listeners. 

### using list

```cpp
using lava::path_drop_event::list =  std::vector<path_drop_event>;
```

List of path drop events. 

## Public Attributes Documentation

### variable sender

```cpp
id sender;
```

Sender id. 

### variable files

```cpp
string_list files;
```

List of files. 

-------------------------------

Updated on 2026-02-01 at 18:13:39 +0000