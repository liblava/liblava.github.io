---
title: lava::json_file::callback
summary: Json file callback. 

---

# lava::json_file::callback



Json file callback. 


`#include <json_file.hpp>`

## Public Types

|                | Name           |
| -------------- | -------------- |
| using std::vector< [callback](/_doxybook/Classes/structlava_1_1json__file_1_1callback.md) * > | **[list](/_doxybook/Classes/structlava_1_1json__file_1_1callback.md#using-list)** <br>List of callbacks.  |
| using std::function< void(json_ref)> | **[load_func](/_doxybook/Classes/structlava_1_1json__file_1_1callback.md#using-load-func)** <br>Load function.  |
| using std::function< json()> | **[save_func](/_doxybook/Classes/structlava_1_1json__file_1_1callback.md#using-save-func)** <br>Save function.  |

## Public Attributes

|                | Name           |
| -------------- | -------------- |
| [load_func](/_doxybook/Classes/structlava_1_1json__file_1_1callback.md#using-load-func) | **[on_load](/_doxybook/Classes/structlava_1_1json__file_1_1callback.md#variable-on-load)** <br>Called on load.  |
| [save_func](/_doxybook/Classes/structlava_1_1json__file_1_1callback.md#using-save-func) | **[on_save](/_doxybook/Classes/structlava_1_1json__file_1_1callback.md#variable-on-save)** <br>Called on save.  |

## Public Types Documentation

### using list

```cpp
using lava::json_file::callback::list =  std::vector<callback*>;
```

List of callbacks. 

### using load_func

```cpp
using lava::json_file::callback::load_func =  std::function<void(json_ref)>;
```

Load function. 

### using save_func

```cpp
using lava::json_file::callback::save_func =  std::function<json()>;
```

Save function. 

## Public Attributes Documentation

### variable on_load

```cpp
load_func on_load;
```

Called on load. 

### variable on_save

```cpp
save_func on_save;
```

Called on save. 

-------------------------------

Updated on 2026-02-01 at 18:13:39 +0000