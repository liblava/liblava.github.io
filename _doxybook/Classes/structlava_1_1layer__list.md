---
title: lava::layer_list
summary: Layer list. 

---

# lava::layer_list



Layer list. 


`#include <layer.hpp>`

## Public Types

|                | Name           |
| -------------- | -------------- |
| using [layer_list](/_doxybook/Classes/structlava_1_1layer__list.md) * | **[ptr](/_doxybook/Classes/structlava_1_1layer__list.md#using-ptr)** <br>Pointer to layer list.  |

## Public Functions

|                | Name           |
| -------------- | -------------- |
| [id](/_doxybook/Classes/structlava_1_1id.md) | **[add](/_doxybook/Classes/structlava_1_1layer__list.md#function-add)**([string_ref](/_doxybook/Namespaces/namespacelava.md#using-string-ref) name, [layer::func](/_doxybook/Classes/structlava_1_1layer.md#using-func) func, bool active =true)<br>Add a new layer.  |
| void | **[add](/_doxybook/Classes/structlava_1_1layer__list.md#function-add)**([layer::s_ptr](/_doxybook/Classes/structlava_1_1layer.md#using-s-ptr) layer)<br>Add a layer.  |
| [id](/_doxybook/Classes/structlava_1_1id.md) | **[add_inactive](/_doxybook/Classes/structlava_1_1layer__list.md#function-add-inactive)**([string_ref](/_doxybook/Namespaces/namespacelava.md#using-string-ref) name, [layer::func](/_doxybook/Classes/structlava_1_1layer.md#using-func) func)<br>Add a new inactive layer.  |
| [layer::s_ptr](/_doxybook/Classes/structlava_1_1layer.md#using-s-ptr) | **[get](/_doxybook/Classes/structlava_1_1layer__list.md#function-get)**([id::ref](/_doxybook/Classes/structlava_1_1id.md#using-ref) layer_id)<br>Get layer in list by id.  |
| bool | **[remove](/_doxybook/Classes/structlava_1_1layer__list.md#function-remove)**([id::ref](/_doxybook/Classes/structlava_1_1id.md#using-ref) layer_id)<br>Remove layer from list.  |
| [layer::list](/_doxybook/Classes/structlava_1_1layer.md#using-list) const & | **[get_all](/_doxybook/Classes/structlava_1_1layer__list.md#function-get-all)**() const<br>Get all layers.  |
| void | **[clear](/_doxybook/Classes/structlava_1_1layer__list.md#function-clear)**()<br>Clear layer list.  |

## Public Types Documentation

### using ptr

```cpp
using lava::layer_list::ptr =  layer_list*;
```

Pointer to layer list. 

## Public Functions Documentation

### function add

```cpp
inline id add(
    string_ref name,
    layer::func func,
    bool active =true
)
```

Add a new layer. 

**Parameters**: 

  * **name** Name of layer 
  * **func** Layer function 
  * **active** Layer active state 


**Return**: id Id of added layer 

### function add

```cpp
inline void add(
    layer::s_ptr layer
)
```

Add a layer. 

**Parameters**: 

  * **layer** Layer to add 


### function add_inactive

```cpp
inline id add_inactive(
    string_ref name,
    layer::func func
)
```

Add a new inactive layer. 

**Parameters**: 

  * **name** Name of layer 
  * **func** Layer function 


**Return**: id Id of added layer 

### function get

```cpp
inline layer::s_ptr get(
    id::ref layer_id
)
```

Get layer in list by id. 

**Parameters**: 

  * **layer_id** Id of layer 


**Return**: layer::ptr Shared pointer to layer 

### function remove

```cpp
inline bool remove(
    id::ref layer_id
)
```

Remove layer from list. 

**Parameters**: 

  * **layer_id** Id of layer to remove 


**Return**: Remove was successful or failed 

### function get_all

```cpp
inline layer::list const & get_all() const
```

Get all layers. 

**Return**: [layer::list](/_doxybook/Classes/structlava_1_1layer.md#using-list) const& List of layers 

### function clear

```cpp
inline void clear()
```

Clear layer list. 

-------------------------------

Updated on 2026-02-01 at 18:13:39 +0000