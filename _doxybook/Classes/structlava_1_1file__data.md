---
title: lava::file_data
summary: File data. 

---

# lava::file_data



File data. 


`#include <file_utils.hpp>`

Inherits from [lava::unique_data](/_doxybook/Classes/structlava_1_1unique__data.md), [lava::data](/_doxybook/Classes/structlava_1_1data.md)

## Public Types

|                | Name           |
| -------------- | -------------- |
| using [file_data](/_doxybook/Classes/structlava_1_1file__data.md) const  & | **[ref](/_doxybook/Classes/structlava_1_1file__data.md#using-ref)** <br>Reference to file data.  |

## Public Functions

|                | Name           |
| -------------- | -------------- |
| | **[file_data](/_doxybook/Classes/structlava_1_1file__data.md#function-file-data)**([string_ref](/_doxybook/Namespaces/namespacelava.md#using-string-ref) filename)<br>Construct a new file data.  |
| | **[unique_data](/_doxybook/Classes/structlava_1_1file__data.md#function-unique-data)**([size_t](/_doxybook/Namespaces/namespacelava.md#using-size-t) length =0, [data_mode](/_doxybook/Namespaces/namespacelava.md#enum-data-mode) mode =data_mode::alloc)<br>Unique data constructors.  |
| | **[unique_data](/_doxybook/Classes/structlava_1_1file__data.md#function-unique-data)**([data::ref](/_doxybook/Classes/structlava_1_1data.md#using-ref) data)<br>Unique data constructors.  |

## Public Attributes

|                | Name           |
| -------------- | -------------- |
| [string](/_doxybook/Namespaces/namespacelava.md#using-string) | **[filename](/_doxybook/Classes/structlava_1_1file__data.md#variable-filename)** <br>Name of file.  |

## Additional inherited members

**Public Functions inherited from [lava::unique_data](/_doxybook/Classes/structlava_1_1unique__data.md)**

|                | Name           |
| -------------- | -------------- |
| | **[~unique_data](/_doxybook/Classes/structlava_1_1unique__data.md#function-~unique-data)**()<br>Destroy the unique data.  |

**Public Functions inherited from [lava::data](/_doxybook/Classes/structlava_1_1data.md)**

|                | Name           |
| -------------- | -------------- |
| | **[data](/_doxybook/Classes/structlava_1_1data.md#function-data)**() =default<br>Construct a new data.  |
| | **[data](/_doxybook/Classes/structlava_1_1data.md#function-data)**(auto * ptr, [size_t](/_doxybook/Namespaces/namespacelava.md#using-size-t) size)<br>Construct a new data.  |
| void | **[set](/_doxybook/Classes/structlava_1_1data.md#function-set)**([size_t](/_doxybook/Namespaces/namespacelava.md#using-size-t) length, [data_mode](/_doxybook/Namespaces/namespacelava.md#enum-data-mode) mode =data_mode::alloc)<br>Set and allocate data by length.  |
| bool | **[allocate](/_doxybook/Classes/structlava_1_1data.md#function-allocate)**()<br>Allocate data.  |
| void | **[free](/_doxybook/Classes/structlava_1_1data.md#function-free)**()<br>Free data.  |
| [data_ptr](/_doxybook/Namespaces/namespacelava.md#using-data-ptr) | **[end](/_doxybook/Classes/structlava_1_1data.md#function-end)**() const<br>Pointer to end of data.  |

**Public Attributes inherited from [lava::data](/_doxybook/Classes/structlava_1_1data.md)**

|                | Name           |
| -------------- | -------------- |
| [data_ptr](/_doxybook/Namespaces/namespacelava.md#using-data-ptr) | **[ptr](/_doxybook/Classes/structlava_1_1data.md#variable-ptr)** <br>Pointer to data.  |
| [size_t](/_doxybook/Namespaces/namespacelava.md#using-size-t) | **[size](/_doxybook/Classes/structlava_1_1data.md#variable-size)** <br>Size of data.  |
| [size_t](/_doxybook/Namespaces/namespacelava.md#using-size-t) | **[alignment](/_doxybook/Classes/structlava_1_1data.md#variable-alignment)** <br>Data alignment.  |


## Public Types Documentation

### using ref

```cpp
using lava::file_data::ref =  file_data const&;
```

Reference to file data. 

## Public Functions Documentation

### function file_data

```cpp
inline explicit file_data(
    string_ref filename
)
```

Construct a new file data. 

**Parameters**: 

  * **filename** Name of file 


### function unique_data

```cpp
inline unique_data(
    size_t length =0,
    data_mode mode =data_mode::alloc
)
```

Unique data constructors. 

### function unique_data

```cpp
inline explicit unique_data(
    data::ref data
)
```

Unique data constructors. 

## Public Attributes Documentation

### variable filename

```cpp
string filename;
```

Name of file. 

-------------------------------

Updated on 2022-11-30 at 01:16:03 +0000