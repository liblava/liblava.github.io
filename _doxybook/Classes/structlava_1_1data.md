---
title: lava::data
summary: Data wrapper. 

---

# lava::data



Data wrapper. 


`#include <data.hpp>`

Inherited by [lava::unique_data](/_doxybook/Classes/structlava_1_1unique__data.md)

## Public Types

|                | Name           |
| -------------- | -------------- |
| using [data](/_doxybook/Classes/structlava_1_1data.md) const  & | **[ref](/_doxybook/Classes/structlava_1_1data.md#using-ref)** <br>Reference to data wrapper.  |

## Public Functions

|                | Name           |
| -------------- | -------------- |
| | **[data](/_doxybook/Classes/structlava_1_1data.md#function-data)**() =default<br>Construct a new data.  |
| | **[data](/_doxybook/Classes/structlava_1_1data.md#function-data)**(auto * ptr, [size_t](/_doxybook/Namespaces/namespacelava.md#using-size-t) size)<br>Construct a new data.  |
| void | **[set](/_doxybook/Classes/structlava_1_1data.md#function-set)**([size_t](/_doxybook/Namespaces/namespacelava.md#using-size-t) length, [data_mode](/_doxybook/Namespaces/namespacelava.md#enum-data-mode) mode =data_mode::alloc)<br>Set and allocate data by length.  |
| bool | **[allocate](/_doxybook/Classes/structlava_1_1data.md#function-allocate)**()<br>Allocate data.  |
| void | **[free](/_doxybook/Classes/structlava_1_1data.md#function-free)**()<br>Free data.  |
| [data_ptr](/_doxybook/Namespaces/namespacelava.md#using-data-ptr) | **[end](/_doxybook/Classes/structlava_1_1data.md#function-end)**() const<br>Pointer to end of data.  |

## Public Attributes

|                | Name           |
| -------------- | -------------- |
| [data_ptr](/_doxybook/Namespaces/namespacelava.md#using-data-ptr) | **[ptr](/_doxybook/Classes/structlava_1_1data.md#variable-ptr)** <br>Pointer to data.  |
| [size_t](/_doxybook/Namespaces/namespacelava.md#using-size-t) | **[size](/_doxybook/Classes/structlava_1_1data.md#variable-size)** <br>Size of data.  |
| [size_t](/_doxybook/Namespaces/namespacelava.md#using-size-t) | **[alignment](/_doxybook/Classes/structlava_1_1data.md#variable-alignment)** <br>Data alignment.  |

## Public Types Documentation

### using ref

```cpp
using lava::data::ref =  data const&;
```

Reference to data wrapper. 

## Public Functions Documentation

### function data

```cpp
data() =default
```

Construct a new data. 

### function data

```cpp
inline data(
    auto * ptr,
    size_t size
)
```

Construct a new data. 

**Parameters**: 

  * **ptr** Data pointer 
  * **size** Size of data 


### function set

```cpp
inline void set(
    size_t length,
    data_mode mode =data_mode::alloc
)
```

Set and allocate data by length. 

**Parameters**: 

  * **length** Length of data 
  * **mode** Data mode 


### function allocate

```cpp
inline bool allocate()
```

Allocate data. 

**Return**: Allocate was successful or failed 

### function free

```cpp
inline void free()
```

Free data. 

### function end

```cpp
inline data_ptr end() const
```

Pointer to end of data. 

**Return**: data_ptr Pointer to end 

## Public Attributes Documentation

### variable ptr

```cpp
data_ptr ptr = nullptr;
```

Pointer to data. 

### variable size

```cpp
size_t size = 0;
```

Size of data. 

### variable alignment

```cpp
size_t alignment = 0;
```

Data alignment. 

-------------------------------

Updated on 2022-11-30 at 01:16:03 +0000