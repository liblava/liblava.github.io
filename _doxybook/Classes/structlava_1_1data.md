---
title: lava::data
summary: Data wrapper. 

---

# lava::data



Data wrapper. 


`#include <data.hpp>`

Inherited by [lava::u_data](/_doxybook/Classes/structlava_1_1u__data.md)

## Public Types

|                | Name           |
| -------------- | -------------- |
| enum class [index](/_doxybook/Namespaces/namespacelava.md#using-index) | **[mode](/_doxybook/Classes/structlava_1_1data.md#enum-mode)** { alloc = 0, no_alloc}<br>Data modes.  |
| using [data](/_doxybook/Classes/structlava_1_1data.md) const  & | **[ref](/_doxybook/Classes/structlava_1_1data.md#using-ref)** <br>Reference to data wrapper.  |
| using char * | **[ptr](/_doxybook/Classes/structlava_1_1data.md#using-ptr)** <br>Data pointer.  |
| using char const  * | **[c_ptr](/_doxybook/Classes/structlava_1_1data.md#using-c-ptr)** <br>Const data pointer.  |

## Public Functions

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

## Public Attributes

|                | Name           |
| -------------- | -------------- |
| [ptr](/_doxybook/Classes/structlava_1_1data.md#using-ptr) | **[addr](/_doxybook/Classes/structlava_1_1data.md#variable-addr)** <br>Pointer address.  |
| [size_t](/_doxybook/Namespaces/namespacelava.md#using-size-t) | **[size](/_doxybook/Classes/structlava_1_1data.md#variable-size)** <br>Size of data.  |
| [size_t](/_doxybook/Namespaces/namespacelava.md#using-size-t) | **[alignment](/_doxybook/Classes/structlava_1_1data.md#variable-alignment)** <br>Data alignment.  |

## Public Types Documentation

### enum mode

| Enumerator | Value | Description |
| ---------- | ----- | ----------- |
| alloc | 0|   |
| no_alloc | |   |



Data modes. 

### using ref

```cpp
using lava::data::ref =  data const&;
```

Reference to data wrapper. 

### using ptr

```cpp
using lava::data::ptr =  char*;
```

Data pointer. 

### using c_ptr

```cpp
using lava::data::c_ptr =  char const*;
```

Const data pointer. 

## Public Functions Documentation

### function as_ptr

```cpp
static inline ptr as_ptr(
    auto * value
)
```

Cast to data pointer. 

**Parameters**: 

  * **value** Value to cast 


**Return**: ptr Data pointer 

### function as_c_ptr

```cpp
static inline c_ptr as_c_ptr(
    auto * value
)
```

Cast to const data pointer. 

**Parameters**: 

  * **value** Value to cast 


**Return**: [c_ptr](/_doxybook/Classes/structlava_1_1data.md#using-c-ptr) Const data pointer 

### function data

```cpp
data() =default
```

Construct a new data. 

### function data

```cpp
inline data(
    auto * addr,
    size_t size
)
```

Construct a new data. 

**Parameters**: 

  * **addr** Data pointer 
  * **size** Size of data 


### function set

```cpp
inline bool set(
    size_t length,
    mode mode =mode::alloc
)
```

Set and allocate data by length. 

**Parameters**: 

  * **length** Length of data 
  * **mode** Data mode 


**Return**: Allocate was successful or failed (mode: alloc) 

### function allocate

```cpp
inline bool allocate()
```

Allocate data. 

**Return**: Allocate was successful or failed 

### function deallocate

```cpp
inline void deallocate()
```

Deallocate data. 

### function end

```cpp
inline ptr end() const
```

Pointer to end of data. 

**Return**: ptr Pointer to end 

## Public Attributes Documentation

### variable addr

```cpp
ptr addr = nullptr;
```

Pointer address. 

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

Updated on 2026-02-01 at 18:13:39 +0000