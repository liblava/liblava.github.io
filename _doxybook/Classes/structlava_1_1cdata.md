---
title: lava::cdata
summary: Const data wrapper. 

---

# lava::cdata



Const data wrapper. 


`#include <data.hpp>`

## Public Types

|                | Name           |
| -------------- | -------------- |
| using [cdata](/_doxybook/Classes/structlava_1_1cdata.md) const  & | **[ref](/_doxybook/Classes/structlava_1_1cdata.md#using-ref)** <br>Reference to const data wrapper.  |

## Public Functions

|                | Name           |
| -------------- | -------------- |
| | **[cdata](/_doxybook/Classes/structlava_1_1cdata.md#function-cdata)**() =default<br>Construct a new const data.  |
| | **[cdata](/_doxybook/Classes/structlava_1_1cdata.md#function-cdata)**(void const * ptr, [size_t](/_doxybook/Namespaces/namespacelava.md#using-size-t) length)<br>Construct a new const data.  |
| | **[cdata](/_doxybook/Classes/structlava_1_1cdata.md#function-cdata)**([data::ref](/_doxybook/Classes/structlava_1_1data.md#using-ref) data)<br>Construct a new const data from other data.  |

## Public Attributes

|                | Name           |
| -------------- | -------------- |
| [data_cptr](/_doxybook/Namespaces/namespacelava.md#using-data-cptr) | **[ptr](/_doxybook/Classes/structlava_1_1cdata.md#variable-ptr)** <br>Const data pointer.  |
| [size_t](/_doxybook/Namespaces/namespacelava.md#using-size-t) | **[size](/_doxybook/Classes/structlava_1_1cdata.md#variable-size)** <br>Size of data.  |

## Public Types Documentation

### using ref

```cpp
using lava::cdata::ref =  cdata const&;
```

Reference to const data wrapper. 

## Public Functions Documentation

### function cdata

```cpp
cdata() =default
```

Construct a new const data. 

### function cdata

```cpp
inline cdata(
    void const * ptr,
    size_t length
)
```

Construct a new const data. 

**Parameters**: 

  * **ptr** Pointer to data 
  * **length** Length of data 


### function cdata

```cpp
inline cdata(
    data::ref data
)
```

Construct a new const data from other data. 

**Parameters**: 

  * **data** Source data 


## Public Attributes Documentation

### variable ptr

```cpp
data_cptr ptr = nullptr;
```

Const data pointer. 

### variable size

```cpp
size_t size = 0;
```

Size of data. 

-------------------------------

Updated on 2022-11-30 at 01:16:03 +0000