---
title: lava::allocator
summary: Vulkan allocator. 

---

# lava::allocator



Vulkan allocator. 


`#include <memory.hpp>`

## Public Types

|                | Name           |
| -------------- | -------------- |
| using std::shared_ptr< [allocator](/_doxybook/Classes/structlava_1_1allocator.md) > | **[ptr](/_doxybook/Classes/structlava_1_1allocator.md#using-ptr)** <br>Shared pointer to a allocator.  |

## Public Functions

|                | Name           |
| -------------- | -------------- |
| [ptr](/_doxybook/Classes/structlava_1_1allocator.md#using-ptr) | **[make](/_doxybook/Classes/structlava_1_1allocator.md#function-make)**()<br>Make a new allocator.  |
| | **[allocator](/_doxybook/Classes/structlava_1_1allocator.md#function-allocator)**() =default<br>Construct a new allocator.  |
| | **[allocator](/_doxybook/Classes/structlava_1_1allocator.md#function-allocator)**(VmaAllocator allocator)<br>Construct a new allocator.  |
| bool | **[create](/_doxybook/Classes/structlava_1_1allocator.md#function-create)**([device_cptr](/_doxybook/Namespaces/namespacelava.md#using-device-cptr) device, VmaAllocatorCreateFlags flags =0)<br>Create a new allocator.  |
| void | **[destroy](/_doxybook/Classes/structlava_1_1allocator.md#function-destroy)**()<br>Destroy the allocator.  |
| bool | **[valid](/_doxybook/Classes/structlava_1_1allocator.md#function-valid)**() const<br>Check if allocator is valid.  |
| VmaAllocator | **[get](/_doxybook/Classes/structlava_1_1allocator.md#function-get)**() const<br>Get the VMA allocator.  |

## Public Types Documentation

### using ptr

```cpp
using lava::allocator::ptr =  std::shared_ptr<allocator>;
```

Shared pointer to a allocator. 

## Public Functions Documentation

### function make

```cpp
static inline ptr make()
```

Make a new allocator. 

**Return**: ptr Shared pointer to allocator 

### function allocator

```cpp
allocator() =default
```

Construct a new allocator. 

### function allocator

```cpp
inline explicit allocator(
    VmaAllocator allocator
)
```

Construct a new allocator. 

**Parameters**: 

  * **allocator** VMA allocator 


### function create

```cpp
bool create(
    device_cptr device,
    VmaAllocatorCreateFlags flags =0
)
```

Create a new allocator. 

**Parameters**: 

  * **device** Vulkan device 
  * **flags** VMA allocator create flags 


**Return**: Create was successful or failed 

### function destroy

```cpp
void destroy()
```

Destroy the allocator. 

### function valid

```cpp
inline bool valid() const
```

Check if allocator is valid. 

**Return**: Allocator is valid or not 

### function get

```cpp
inline VmaAllocator get() const
```

Get the VMA allocator. 

**Return**: VmaAllocator VMA allocator 

-------------------------------

Updated on 2024-03-22 at 21:51:37 +0000