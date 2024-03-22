---
title: lava::layer
summary: Layer. 

---

# lava::layer



Layer. 


`#include <layer.hpp>`

Inherits from [lava::entity](/_doxybook/Classes/structlava_1_1entity.md), [lava::no_copy_no_move](/_doxybook/Classes/structlava_1_1no__copy__no__move.md), [lava::interface](/_doxybook/Classes/structlava_1_1interface.md)

## Public Types

|                | Name           |
| -------------- | -------------- |
| using std::shared_ptr< [layer](/_doxybook/Classes/structlava_1_1layer.md) > | **[ptr](/_doxybook/Classes/structlava_1_1layer.md#using-ptr)** <br>Shared pointer to layer.  |
| using std::map< [id](/_doxybook/Classes/structlava_1_1id.md), [ptr](/_doxybook/Classes/structlava_1_1layer.md#using-ptr) > | **[map](/_doxybook/Classes/structlava_1_1layer.md#using-map)** <br>Map of layers.  |
| using std::vector< [ptr](/_doxybook/Classes/structlava_1_1layer.md#using-ptr) > | **[list](/_doxybook/Classes/structlava_1_1layer.md#using-list)** <br>List of layers.  |
| using std::function< [void](/_doxybook/Classes/structlava_1_1layer.md#using-map)()> | **[func](/_doxybook/Classes/structlava_1_1layer.md#using-func)** <br>Layer function.  |

## Public Functions

|                | Name           |
| -------------- | -------------- |
| [ptr](/_doxybook/Classes/structlava_1_1layer.md#using-ptr) | **[make](/_doxybook/Classes/structlava_1_1layer.md#function-make)**([string_ref](/_doxybook/Namespaces/namespacelava.md#using-string-ref) name)<br>Make a new layer.  |
| | **[layer](/_doxybook/Classes/structlava_1_1layer.md#function-layer)**([string_ref](/_doxybook/Namespaces/namespacelava.md#using-string-ref) name)<br>Construct a new layer.  |

## Public Attributes

|                | Name           |
| -------------- | -------------- |
| [func](/_doxybook/Classes/structlava_1_1layer.md#using-func) | **[on_func](/_doxybook/Classes/structlava_1_1layer.md#variable-on-func)** <br>Called by layering.  |
| [bool](/_doxybook/Classes/structlava_1_1layer.md#using-map) | **[active](/_doxybook/Classes/structlava_1_1layer.md#variable-active)** <br>Active state.  |
| [string](/_doxybook/Namespaces/namespacelava.md#using-string) | **[name](/_doxybook/Classes/structlava_1_1layer.md#variable-name)** <br>Name of layer.  |

## Additional inherited members

**Public Functions inherited from [lava::entity](/_doxybook/Classes/structlava_1_1entity.md)**

|                | Name           |
| -------------- | -------------- |
| | **[entity](/_doxybook/Classes/structlava_1_1entity.md#function-entity)**()<br>Construct a new entity.  |
| [id::ref](/_doxybook/Classes/structlava_1_1id.md#using-ref) | **[get_id](/_doxybook/Classes/structlava_1_1entity.md#function-get-id)**() const<br>Get the id of entity.  |

**Public Functions inherited from [lava::no_copy_no_move](/_doxybook/Classes/structlava_1_1no__copy__no__move.md)**

|                | Name           |
| -------------- | -------------- |
| | **[no_copy_no_move](/_doxybook/Classes/structlava_1_1no__copy__no__move.md#function-no-copy-no-move)**() =default<br>Construct a new object.  |
| | **[no_copy_no_move](/_doxybook/Classes/structlava_1_1no__copy__no__move.md#function-no-copy-no-move)**([no_copy_no_move](/_doxybook/Classes/structlava_1_1no__copy__no__move.md) const & ) =delete<br>No copy.  |
| void | **[operator=](/_doxybook/Classes/structlava_1_1no__copy__no__move.md#function-operator=)**([no_copy_no_move](/_doxybook/Classes/structlava_1_1no__copy__no__move.md) const & ) =delete<br>No move.  |

**Public Functions inherited from [lava::interface](/_doxybook/Classes/structlava_1_1interface.md)**

|                | Name           |
| -------------- | -------------- |
| virtual | **[~interface](/_doxybook/Classes/structlava_1_1interface.md#function-~interface)**() =default<br>Destroy the interface.  |


## Public Types Documentation

### using ptr

```cpp
using lava::layer::ptr =  std::shared_ptr<layer>;
```

Shared pointer to layer. 

### using map

```cpp
using lava::layer::map =  std::map<id, ptr>;
```

Map of layers. 

### using list

```cpp
using lava::layer::list =  std::vector<ptr>;
```

List of layers. 

### using func

```cpp
using lava::layer::func =  std::function<void()>;
```

Layer function. 

## Public Functions Documentation

### function make

```cpp
static inline ptr make(
    string_ref name
)
```

Make a new layer. 

**Parameters**: 

  * **name** Name of layer 


**Return**: ptr Shared pointer to layer 

### function layer

```cpp
inline layer(
    string_ref name
)
```

Construct a new layer. 

**Parameters**: 

  * **name** Name of layer 


## Public Attributes Documentation

### variable on_func

```cpp
func on_func;
```

Called by layering. 

### variable active

```cpp
bool active = true;
```

Active state. 

### variable name

```cpp
string name;
```

Name of layer. 

-------------------------------

Updated on 2024-03-22 at 21:51:37 +0000