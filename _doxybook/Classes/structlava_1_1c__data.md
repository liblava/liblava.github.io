---
title: lava::c_data
summary: Const data wrapper. 

---

# lava::c_data



Const data wrapper. 


`#include <data.hpp>`

## Public Types

|                | Name           |
| -------------- | -------------- |
| using [c_data](/_doxybook/Classes/structlava_1_1c__data.md) const  & | **[ref](/_doxybook/Classes/structlava_1_1c__data.md#using-ref)** <br>Reference to const data wrapper.  |

## Public Functions

|                | Name           |
| -------------- | -------------- |
| | **[c_data](/_doxybook/Classes/structlava_1_1c__data.md#function-c-data)**() =default<br>Construct a new const data.  |
| | **[c_data](/_doxybook/Classes/structlava_1_1c__data.md#function-c-data)**(void const * addr, [size_t](/_doxybook/Namespaces/namespacelava.md#using-size-t) length)<br>Construct a new const data.  |
| | **[c_data](/_doxybook/Classes/structlava_1_1c__data.md#function-c-data)**([data::ref](/_doxybook/Classes/structlava_1_1data.md#using-ref) data)<br>Construct a new const data from other data.  |

## Public Attributes

|                | Name           |
| -------------- | -------------- |
| [data::c_ptr](/_doxybook/Classes/structlava_1_1data.md#using-c-ptr) | **[addr](/_doxybook/Classes/structlava_1_1c__data.md#variable-addr)** <br>Const data pointer.  |
| [size_t](/_doxybook/Namespaces/namespacelava.md#using-size-t) | **[size](/_doxybook/Classes/structlava_1_1c__data.md#variable-size)** <br>Size of data.  |

## Public Types Documentation

### using ref

```cpp
using lava::c_data::ref =  c_data const&;
```

Reference to const data wrapper. 

## Public Functions Documentation

### function c_data

```cpp
c_data() =default
```

Construct a new const data. 

### function c_data

```cpp
inline c_data(
    void const * addr,
    size_t length
)
```

Construct a new const data. 

**Parameters**: 

  * **addr** Pointer to data 
  * **length** Length of data 


### function c_data

```cpp
inline c_data(
    data::ref data
)
```

Construct a new const data from other data. 

**Parameters**: 

  * **data** Source data 


## Public Attributes Documentation

### variable addr

```cpp
data::c_ptr addr = nullptr;
```

Const data pointer. 

### variable size

```cpp
size_t size = 0;
```

Size of data. 

-------------------------------

Updated on 2026-02-01 at 18:13:39 +0000