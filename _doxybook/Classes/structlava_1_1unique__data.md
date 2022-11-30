---
title: lava::unique_data
summary: Unique data wrapper. 

---

# lava::unique_data



Unique data wrapper. 


`#include <data.hpp>`

Inherits from [lava::data](/_doxybook/Classes/structlava_1_1data.md)

Inherited by [lava::file_data](/_doxybook/Classes/structlava_1_1file__data.md)

## Public Types

|                | Name           |
| -------------- | -------------- |
| using [unique_data](/_doxybook/Classes/structlava_1_1unique__data.md) const  & | **[ref](/_doxybook/Classes/structlava_1_1unique__data.md#using-ref)** <br>Reference to unique data wrapper.  |

## Public Functions

|                | Name           |
| -------------- | -------------- |
| | **[unique_data](/_doxybook/Classes/structlava_1_1unique__data.md#function-unique-data)**([size_t](/_doxybook/Namespaces/namespacelava.md#using-size-t) length =0, [data_mode](/_doxybook/Namespaces/namespacelava.md#enum-data-mode) mode =data_mode::alloc)<br>Construct a new unique data.  |
| | **[unique_data](/_doxybook/Classes/structlava_1_1unique__data.md#function-unique-data)**([data::ref](/_doxybook/Classes/structlava_1_1data.md#using-ref) data)<br>Construct a new unique data from another data.  |
| | **[~unique_data](/_doxybook/Classes/structlava_1_1unique__data.md#function-~unique-data)**()<br>Destroy the unique data.  |

## Additional inherited members

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
using lava::unique_data::ref =  unique_data const&;
```

Reference to unique data wrapper. 

## Public Functions Documentation

### function unique_data

```cpp
inline unique_data(
    size_t length =0,
    data_mode mode =data_mode::alloc
)
```

Construct a new unique data. 

**Parameters**: 

  * **length** Length of data 
  * **mode** Data mode 


### function unique_data

```cpp
inline explicit unique_data(
    data::ref data
)
```

Construct a new unique data from another data. 

**Parameters**: 

  * **data** Source data 


### function ~unique_data

```cpp
inline ~unique_data()
```

Destroy the unique data. 

-------------------------------

Updated on 2022-11-30 at 01:16:04 +0000