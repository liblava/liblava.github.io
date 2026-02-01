---
title: lava::file_data
summary: File data. 

---

# lava::file_data



File data. 


`#include <file_utils.hpp>`

Inherits from [lava::u_data](/_doxybook/Classes/structlava_1_1u__data.md), [lava::data](/_doxybook/Classes/structlava_1_1data.md)

## Public Types

|                | Name           |
| -------------- | -------------- |
| using [file_data](/_doxybook/Classes/structlava_1_1file__data.md) const  & | **[ref](/_doxybook/Classes/structlava_1_1file__data.md#using-ref)** <br>Reference to file data.  |

## Public Functions

|                | Name           |
| -------------- | -------------- |
| | **[file_data](/_doxybook/Classes/structlava_1_1file__data.md#function-file-data)**([string_ref](/_doxybook/Namespaces/namespacelava.md#using-string-ref) filename)<br>Construct a new file data.  |
| | **[u_data](/_doxybook/Classes/structlava_1_1file__data.md#function-u-data)**([size_t](/_doxybook/Namespaces/namespacelava.md#using-size-t) length =0, [data::mode](/_doxybook/Classes/structlava_1_1data.md#enum-mode) mode =data::mode::alloc)<br>Unique data constructors.  |
| | **[u_data](/_doxybook/Classes/structlava_1_1file__data.md#function-u-data)**([data::ref](/_doxybook/Classes/structlava_1_1data.md#using-ref) data)<br>Unique data constructors.  |

## Public Attributes

|                | Name           |
| -------------- | -------------- |
| [string](/_doxybook/Namespaces/namespacelava.md#using-string) | **[filename](/_doxybook/Classes/structlava_1_1file__data.md#variable-filename)** <br>Name of file.  |

## Additional inherited members

**Public Functions inherited from [lava::u_data](/_doxybook/Classes/structlava_1_1u__data.md)**

|                | Name           |
| -------------- | -------------- |
| | **[~u_data](/_doxybook/Classes/structlava_1_1u__data.md#function-~u-data)**()<br>Destroy the unique data.  |

**Public Types inherited from [lava::data](/_doxybook/Classes/structlava_1_1data.md)**

|                | Name           |
| -------------- | -------------- |
| enum class [index](/_doxybook/Namespaces/namespacelava.md#using-index) | **[mode](/_doxybook/Classes/structlava_1_1data.md#enum-mode)** { alloc, no_alloc}<br>Data modes.  |
| using char * | **[ptr](/_doxybook/Classes/structlava_1_1data.md#using-ptr)** <br>Data pointer.  |
| using char const  * | **[c_ptr](/_doxybook/Classes/structlava_1_1data.md#using-c-ptr)** <br>Const data pointer.  |

**Public Functions inherited from [lava::data](/_doxybook/Classes/structlava_1_1data.md)**

|                | Name           |
| -------------- | -------------- |
| [ptr](/_doxybook/Classes/structlava_1_1data.md#using-ptr) | **[as_ptr](/_doxybook/Classes/structlava_1_1data.md#function-as-ptr)**(auto * value)<br>Cast to data pointer.  |
| [c_ptr](/_doxybook/Classes/structlava_1_1data.md#using-c-ptr) | **[as_c_ptr](/_doxybook/Classes/structlava_1_1data.md#function-as-c-ptr)**(auto * value)<br>Cast to const data pointer.  |
| | **[data](/_doxybook/Classes/structlava_1_1data.md#function-data)**() =default<br>Construct a new data.  |
| | **[data](/_doxybook/Classes/structlava_1_1data.md#function-data)**(auto * addr, [size_t](/_doxybook/Namespaces/namespacelava.md#using-size-t) size)<br>Construct a new data.  |
| bool | **[set](/_doxybook/Classes/structlava_1_1data.md#function-set)**([size_t](/_doxybook/Namespaces/namespacelava.md#using-size-t) length, [mode](/_doxybook/Classes/structlava_1_1data.md#enum-mode) mode =mode::alloc)<br>Set and allocate data by length.  |
| bool | **[allocate](/_doxybook/Classes/structlava_1_1data.md#function-allocate)**()<br>Allocate data.  |
| void | **[deallocate](/_doxybook/Classes/structlava_1_1data.md#function-deallocate)**()<br>Deallocate data.  |
| [ptr](/_doxybook/Classes/structlava_1_1data.md#using-ptr) | **[end](/_doxybook/Classes/structlava_1_1data.md#function-end)**() const<br>Pointer to end of data.  |

**Public Attributes inherited from [lava::data](/_doxybook/Classes/structlava_1_1data.md)**

|                | Name           |
| -------------- | -------------- |
| [ptr](/_doxybook/Classes/structlava_1_1data.md#using-ptr) | **[addr](/_doxybook/Classes/structlava_1_1data.md#variable-addr)** <br>Pointer address.  |
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


### function u_data

```cpp
inline u_data(
    size_t length =0,
    data::mode mode =data::mode::alloc
)
```

Unique data constructors. 

### function u_data

```cpp
inline explicit u_data(
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

Updated on 2026-02-01 at 18:13:39 +0000