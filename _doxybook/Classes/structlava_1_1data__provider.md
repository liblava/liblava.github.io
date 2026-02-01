---
title: lava::data_provider
summary: Data provider. 

---

# lava::data_provider



Data provider. 


`#include <data.hpp>`

## Public Types

|                | Name           |
| -------------- | -------------- |
| using std::function< [data::ptr](/_doxybook/Classes/structlava_1_1data.md#using-ptr)([size_t](/_doxybook/Namespaces/namespacelava.md#using-size-t), [size_t](/_doxybook/Namespaces/namespacelava.md#using-size-t))> | **[alloc_func](/_doxybook/Classes/structlava_1_1data__provider.md#using-alloc-func)** <br>Allocation function.  |
| using std::function< void()> | **[free_func](/_doxybook/Classes/structlava_1_1data__provider.md#using-free-func)** <br>Free function.  |
| using std::function< [data::ptr](/_doxybook/Classes/structlava_1_1data.md#using-ptr)([data::ptr](/_doxybook/Classes/structlava_1_1data.md#using-ptr), [size_t](/_doxybook/Namespaces/namespacelava.md#using-size-t), [size_t](/_doxybook/Namespaces/namespacelava.md#using-size-t))> | **[realloc_func](/_doxybook/Classes/structlava_1_1data__provider.md#using-realloc-func)** <br>Reallocation function.  |

## Public Attributes

|                | Name           |
| -------------- | -------------- |
| [alloc_func](/_doxybook/Classes/structlava_1_1data__provider.md#using-alloc-func) | **[on_alloc](/_doxybook/Classes/structlava_1_1data__provider.md#variable-on-alloc)** <br>Called on allocation.  |
| [free_func](/_doxybook/Classes/structlava_1_1data__provider.md#using-free-func) | **[on_free](/_doxybook/Classes/structlava_1_1data__provider.md#variable-on-free)** <br>Called on free.  |
| [realloc_func](/_doxybook/Classes/structlava_1_1data__provider.md#using-realloc-func) | **[on_realloc](/_doxybook/Classes/structlava_1_1data__provider.md#variable-on-realloc)** <br>Called on reallocation.  |

## Public Types Documentation

### using alloc_func

```cpp
using lava::data_provider::alloc_func =  std::function<data::ptr(size_t, size_t)>;
```

Allocation function. 

### using free_func

```cpp
using lava::data_provider::free_func =  std::function<void()>;
```

Free function. 

### using realloc_func

```cpp
using lava::data_provider::realloc_func =  std::function<data::ptr(data::ptr, size_t, size_t)>;
```

Reallocation function. 

## Public Attributes Documentation

### variable on_alloc

```cpp
alloc_func on_alloc;
```

Called on allocation. 

### variable on_free

```cpp
free_func on_free;
```

Called on free. 

### variable on_realloc

```cpp
realloc_func on_realloc;
```

Called on reallocation. 

-------------------------------

Updated on 2026-02-01 at 18:13:39 +0000