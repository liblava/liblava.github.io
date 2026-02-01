---
title: lava::file_delete
summary: File delete guard. 

---

# lava::file_delete



File delete guard. 


`#include <file_utils.hpp>`

Inherits from [lava::no_copy_no_move](/_doxybook/Classes/structlava_1_1no__copy__no__move.md)

## Public Functions

|                | Name           |
| -------------- | -------------- |
| | **[file_delete](/_doxybook/Classes/structlava_1_1file__delete.md#function-file-delete)**([string](/_doxybook/Namespaces/namespacelava.md#using-string) filename ="")<br>Construct a new file delete.  |
| | **[~file_delete](/_doxybook/Classes/structlava_1_1file__delete.md#function-~file-delete)**()<br>Destroy the file delete.  |

## Public Attributes

|                | Name           |
| -------------- | -------------- |
| [string](/_doxybook/Namespaces/namespacelava.md#using-string) | **[filename](/_doxybook/Classes/structlava_1_1file__delete.md#variable-filename)** <br>Name of file.  |
| bool | **[active](/_doxybook/Classes/structlava_1_1file__delete.md#variable-active)** <br>Active state.  |

## Additional inherited members

**Public Functions inherited from [lava::no_copy_no_move](/_doxybook/Classes/structlava_1_1no__copy__no__move.md)**

|                | Name           |
| -------------- | -------------- |
| | **[no_copy_no_move](/_doxybook/Classes/structlava_1_1no__copy__no__move.md#function-no-copy-no-move)**() =default<br>Construct a new object.  |
| | **[no_copy_no_move](/_doxybook/Classes/structlava_1_1no__copy__no__move.md#function-no-copy-no-move)**([no_copy_no_move](/_doxybook/Classes/structlava_1_1no__copy__no__move.md) const & ) =delete<br>No copy.  |
| void | **[operator=](/_doxybook/Classes/structlava_1_1no__copy__no__move.md#function-operator=)**([no_copy_no_move](/_doxybook/Classes/structlava_1_1no__copy__no__move.md) const & ) =delete<br>No move.  |


## Public Functions Documentation

### function file_delete

```cpp
inline explicit file_delete(
    string filename =""
)
```

Construct a new file delete. 

**Parameters**: 

  * **filename** Name of file 


### function ~file_delete

```cpp
~file_delete()
```

Destroy the file delete. 

## Public Attributes Documentation

### variable filename

```cpp
string filename;
```

Name of file. 

### variable active

```cpp
bool active = true;
```

Active state. 

-------------------------------

Updated on 2026-02-01 at 18:13:39 +0000