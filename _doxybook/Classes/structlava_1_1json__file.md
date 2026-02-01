---
title: lava::json_file
summary: Json file. 

---

# lava::json_file



Json file. 


`#include <json_file.hpp>`

## Public Classes

|                | Name           |
| -------------- | -------------- |
| struct | **[callback](/_doxybook/Classes/structlava_1_1json__file_1_1callback.md)** <br>Json file callback.  |

## Public Functions

|                | Name           |
| -------------- | -------------- |
| | **[json_file](/_doxybook/Classes/structlava_1_1json__file.md#function-json-file)**([string_ref](/_doxybook/Namespaces/namespacelava.md#using-string-ref) path ="config.json")<br>Construct a new json file.  |
| void | **[add](/_doxybook/Classes/structlava_1_1json__file.md#function-add)**([callback](/_doxybook/Classes/structlava_1_1json__file_1_1callback.md) * callback)<br>Add callback to json file.  |
| void | **[remove](/_doxybook/Classes/structlava_1_1json__file.md#function-remove)**([callback](/_doxybook/Classes/structlava_1_1json__file_1_1callback.md) * callback)<br>Remove callback from json file.  |
| void | **[clear](/_doxybook/Classes/structlava_1_1json__file.md#function-clear)**()<br>Clear all callbacks.  |
| void | **[set](/_doxybook/Classes/structlava_1_1json__file.md#function-set)**([string_ref](/_doxybook/Namespaces/namespacelava.md#using-string-ref) value)<br>Set path of the json file.  |
| [string_ref](/_doxybook/Namespaces/namespacelava.md#using-string-ref) | **[get](/_doxybook/Classes/structlava_1_1json__file.md#function-get)**() const<br>Get path of the json file.  |
| bool | **[load](/_doxybook/Classes/structlava_1_1json__file.md#function-load)**()<br>Load the json file.  |
| bool | **[save](/_doxybook/Classes/structlava_1_1json__file.md#function-save)**()<br>Save the json file.  |

## Public Functions Documentation

### function json_file

```cpp
explicit json_file(
    string_ref path ="config.json"
)
```

Construct a new json file. 

**Parameters**: 

  * **path** Name of file 


### function add

```cpp
void add(
    callback * callback
)
```

Add callback to json file. 

**Parameters**: 

  * **callback** Callback to add 


### function remove

```cpp
void remove(
    callback * callback
)
```

Remove callback from json file. 

**Parameters**: 

  * **callback** Callback to remove 


### function clear

```cpp
inline void clear()
```

Clear all callbacks. 

### function set

```cpp
inline void set(
    string_ref value
)
```

Set path of the json file. 

**Parameters**: 

  * **value** Name of file 


### function get

```cpp
inline string_ref get() const
```

Get path of the json file. 

**Return**: name Name of file 

### function load

```cpp
bool load()
```

Load the json file. 

**Return**: Load was successful or failed 

### function save

```cpp
bool save()
```

Save the json file. 

**Return**: Save was successful or failed 

-------------------------------

Updated on 2026-02-01 at 18:13:39 +0000