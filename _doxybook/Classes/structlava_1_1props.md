---
title: lava::props
summary: Props. 

---

# lava::props



Props. 


`#include <props.hpp>`

Inherits from [lava::configurable](/_doxybook/Classes/structlava_1_1configurable.md), [lava::interface](/_doxybook/Classes/structlava_1_1interface.md)

## Public Classes

|                | Name           |
| -------------- | -------------- |
| struct | **[item](/_doxybook/Classes/structlava_1_1props_1_1item.md)** <br>Prop item.  |

## Public Functions

|                | Name           |
| -------------- | -------------- |
| void | **[add](/_doxybook/Classes/structlava_1_1props.md#function-add)**([string_ref](/_doxybook/Namespaces/namespacelava.md#using-string-ref) name, [string_ref](/_doxybook/Namespaces/namespacelava.md#using-string-ref) filename)<br>Add a prop.  |
| void | **[remove](/_doxybook/Classes/structlava_1_1props.md#function-remove)**([string_ref](/_doxybook/Namespaces/namespacelava.md#using-string-ref) name)<br>Remove a prop.  |
| bool | **[install](/_doxybook/Classes/structlava_1_1props.md#function-install)**([string_ref](/_doxybook/Namespaces/namespacelava.md#using-string-ref) name, [string_ref](/_doxybook/Namespaces/namespacelava.md#using-string-ref) filename)<br>Install a prop (add + load)  |
| [c_data](/_doxybook/Classes/structlava_1_1c__data.md) | **[operator()](/_doxybook/Classes/structlava_1_1props.md#function-operator())**([string_ref](/_doxybook/Namespaces/namespacelava.md#using-string-ref) name)<br>Get prop data.  |
| [string_ref](/_doxybook/Namespaces/namespacelava.md#using-string-ref) | **[get_filename](/_doxybook/Classes/structlava_1_1props.md#function-get-filename)**([string_ref](/_doxybook/Namespaces/namespacelava.md#using-string-ref) name) const<br>Get file name of prop.  |
| void | **[set_filename](/_doxybook/Classes/structlava_1_1props.md#function-set-filename)**([string_ref](/_doxybook/Namespaces/namespacelava.md#using-string-ref) name, [string_ref](/_doxybook/Namespaces/namespacelava.md#using-string-ref) filename)<br>Set filename of prop.  |
| bool | **[exists](/_doxybook/Classes/structlava_1_1props.md#function-exists)**([string_ref](/_doxybook/Namespaces/namespacelava.md#using-string-ref) name) const<br>Check if prop exists.  |
| bool | **[empty](/_doxybook/Classes/structlava_1_1props.md#function-empty)**([string_ref](/_doxybook/Namespaces/namespacelava.md#using-string-ref) name) const<br>Check if prop data is empty.  |
| bool | **[load](/_doxybook/Classes/structlava_1_1props.md#function-load)**([string_ref](/_doxybook/Namespaces/namespacelava.md#using-string-ref) name)<br>Load prop data (reload if loaded)  |
| void | **[unload](/_doxybook/Classes/structlava_1_1props.md#function-unload)**([string_ref](/_doxybook/Namespaces/namespacelava.md#using-string-ref) name)<br>Unload prop data.  |
| bool | **[load_all](/_doxybook/Classes/structlava_1_1props.md#function-load-all)**()<br>Load all prop data (reload if loaded)  |
| void | **[unload_all](/_doxybook/Classes/structlava_1_1props.md#function-unload-all)**()<br>Unload all prop data.  |
| bool | **[check](/_doxybook/Classes/structlava_1_1props.md#function-check)**()<br>Check whether all props are available.  |
| void | **[parse](/_doxybook/Classes/structlava_1_1props.md#function-parse)**([cmd_line](/_doxybook/Namespaces/namespacelava.md#using-cmd-line) cmd_line)<br>Parse prop overloads.  |
| void | **[clear](/_doxybook/Classes/structlava_1_1props.md#function-clear)**()<br>Clear all props.  |
| [item::map](/_doxybook/Classes/structlava_1_1props_1_1item.md#using-map) const & | **[get_all](/_doxybook/Classes/structlava_1_1props.md#function-get-all)**() const<br>Get all props.  |
| virtual void | **[set_json](/_doxybook/Classes/structlava_1_1props.md#function-set-json)**(json_ref j) override |
| virtual json | **[get_json](/_doxybook/Classes/structlava_1_1props.md#function-get-json)**() const override |

## Public Attributes

|                | Name           |
| -------------- | -------------- |
| [engine](/_doxybook/Classes/structlava_1_1engine.md) * | **[app](/_doxybook/Classes/structlava_1_1props.md#variable-app)** <br>Engine.  |

## Additional inherited members

**Public Functions inherited from [lava::interface](/_doxybook/Classes/structlava_1_1interface.md)**

|                | Name           |
| -------------- | -------------- |
| virtual | **[~interface](/_doxybook/Classes/structlava_1_1interface.md#function-~interface)**() =default<br>Destroy the interface.  |


## Public Functions Documentation

### function add

```cpp
void add(
    string_ref name,
    string_ref filename
)
```

Add a prop. 

**Parameters**: 

  * **name** Name of prop 
  * **filename** File name of prop 


### function remove

```cpp
void remove(
    string_ref name
)
```

Remove a prop. 

**Parameters**: 

  * **name** Name of prop 


### function install

```cpp
bool install(
    string_ref name,
    string_ref filename
)
```

Install a prop (add + load) 

**Parameters**: 

  * **name** Name of prop 
  * **filename** File name of prop 


**Return**: Install was successful or failed 

### function operator()

```cpp
c_data operator()(
    string_ref name
)
```

Get prop data. 

**Parameters**: 

  * **name** Name of prop 


**Return**: [c_data](/_doxybook/Classes/structlava_1_1c__data.md) Prop const data 

### function get_filename

```cpp
inline string_ref get_filename(
    string_ref name
) const
```

Get file name of prop. 

**Parameters**: 

  * **name** Name of prop 


**Return**: [string_ref](/_doxybook/Namespaces/namespacelava.md#using-string-ref) File name 

### function set_filename

```cpp
inline void set_filename(
    string_ref name,
    string_ref filename
)
```

Set filename of prop. 

**Parameters**: 

  * **name** Name of prop 
  * **filename** File name 


### function exists

```cpp
inline bool exists(
    string_ref name
) const
```

Check if prop exists. 

**Parameters**: 

  * **name** Name of prop to check 


**Return**: Prop exists or not 

### function empty

```cpp
inline bool empty(
    string_ref name
) const
```

Check if prop data is empty. 

**Parameters**: 

  * **name** Name of prop 


**Return**: Prop data is empty or not 

### function load

```cpp
bool load(
    string_ref name
)
```

Load prop data (reload if loaded) 

**Parameters**: 

  * **name** Name of prop 


**Return**: Load was successful or failed 

### function unload

```cpp
inline void unload(
    string_ref name
)
```

Unload prop data. 

**Parameters**: 

  * **name** Name of prop 


### function load_all

```cpp
bool load_all()
```

Load all prop data (reload if loaded) 

**Return**: Load was successful or failed 

### function unload_all

```cpp
inline void unload_all()
```

Unload all prop data. 

### function check

```cpp
bool check()
```

Check whether all props are available. 

**Return**: All props are there or are missing (see log) 

### function parse

```cpp
void parse(
    cmd_line cmd_line
)
```

Parse prop overloads. 

**Parameters**: 

  * **[cmd_line](/_doxybook/Namespaces/namespacelava.md#using-cmd-line)** Command line arguments 


### function clear

```cpp
inline void clear()
```

Clear all props. 

### function get_all

```cpp
inline item::map const & get_all() const
```

Get all props. 

**Return**: [item::map](/_doxybook/Classes/structlava_1_1props_1_1item.md#using-map) const& Map of props 

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


## Public Attributes Documentation

### variable app

```cpp
engine * app = nullptr;
```

Engine. 

-------------------------------

Updated on 2026-02-01 at 18:13:39 +0000