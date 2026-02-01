---
title: lava::stage
summary: Stage. 

---

# lava::stage



Stage. 


`#include <driver.hpp>`

## Public Types

|                | Name           |
| -------------- | -------------- |
| using std::map< [index](/_doxybook/Namespaces/namespacelava.md#using-index), [stage](/_doxybook/Classes/structlava_1_1stage.md) * > | **[map](/_doxybook/Classes/structlava_1_1stage.md#using-map)** <br>Map of stages.  |
| using std::function< [i32](/_doxybook/Namespaces/namespacelava.md#using-i32)(argh::parser)> | **[func](/_doxybook/Classes/structlava_1_1stage.md#using-func)** <br>Stage function.  |

## Public Functions

|                | Name           |
| -------------- | -------------- |
| | **[stage](/_doxybook/Classes/structlava_1_1stage.md#function-stage)**([ui32](/_doxybook/Namespaces/namespacelava.md#using-ui32) id, [string_ref](/_doxybook/Namespaces/namespacelava.md#using-string-ref) name, [func](/_doxybook/Classes/structlava_1_1stage.md#using-func) func)<br>Construct a new stage.  |

## Public Attributes

|                | Name           |
| -------------- | -------------- |
| [index](/_doxybook/Namespaces/namespacelava.md#using-index) | **[id](/_doxybook/Classes/structlava_1_1stage.md#variable-id)** <br>Stage id.  |
| [string](/_doxybook/Namespaces/namespacelava.md#using-string) | **[name](/_doxybook/Classes/structlava_1_1stage.md#variable-name)** <br>Stage name.  |
| [func](/_doxybook/Classes/structlava_1_1stage.md#using-func) | **[on_func](/_doxybook/Classes/structlava_1_1stage.md#variable-on-func)** <br>Called on stage run.  |

## Public Types Documentation

### using map

```cpp
using lava::stage::map =  std::map<index, stage*>;
```

Map of stages. 

### using func

```cpp
using lava::stage::func =  std::function<i32(argh::parser)>;
```

Stage function. 

## Public Functions Documentation

### function stage

```cpp
explicit stage(
    ui32 id,
    string_ref name,
    func func
)
```

Construct a new stage. 

**Parameters**: 

  * **id** Stage id 
  * **name** Stage name 
  * **func** Stage function 


## Public Attributes Documentation

### variable id

```cpp
index id = 0;
```

Stage id. 

### variable name

```cpp
string name;
```

Stage name. 

### variable on_func

```cpp
func on_func;
```

Called on stage run. 

-------------------------------

Updated on 2026-02-01 at 18:13:39 +0000