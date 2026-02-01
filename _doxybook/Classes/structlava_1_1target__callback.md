---
title: lava::target_callback
summary: Target callback. 

---

# lava::target_callback



Target callback. 


`#include <base.hpp>`

## Public Types

|                | Name           |
| -------------- | -------------- |
| using [target_callback](/_doxybook/Classes/structlava_1_1target__callback.md) const  * | **[c_ptr](/_doxybook/Classes/structlava_1_1target__callback.md#using-c-ptr)** <br>Const pointer to target callback.  |
| using std::vector< [target_callback](/_doxybook/Classes/structlava_1_1target__callback.md) * > | **[list](/_doxybook/Classes/structlava_1_1target__callback.md#using-list)** <br>List of target callbacks.  |
| using std::vector< [c_ptr](/_doxybook/Classes/structlava_1_1target__callback.md#using-c-ptr) > | **[c_list](/_doxybook/Classes/structlava_1_1target__callback.md#using-c-list)** <br>Const list of target callbacks.  |
| using std::function< bool([VkAttachmentsRef](/_doxybook/Namespaces/namespacelava.md#using-vkattachmentsref), [rect::ref](/_doxybook/Classes/structlava_1_1rect.md#using-ref))> | **[created_func](/_doxybook/Classes/structlava_1_1target__callback.md#using-created-func)** <br>Created function.  |
| using std::function< void()> | **[destroyed_func](/_doxybook/Classes/structlava_1_1target__callback.md#using-destroyed-func)** <br>Destroy function.  |

## Public Attributes

|                | Name           |
| -------------- | -------------- |
| [created_func](/_doxybook/Classes/structlava_1_1target__callback.md#using-created-func) | **[on_created](/_doxybook/Classes/structlava_1_1target__callback.md#variable-on-created)** <br>Called on target created.  |
| [destroyed_func](/_doxybook/Classes/structlava_1_1target__callback.md#using-destroyed-func) | **[on_destroyed](/_doxybook/Classes/structlava_1_1target__callback.md#variable-on-destroyed)** <br>Called on target destroyed.  |

## Public Types Documentation

### using c_ptr

```cpp
using lava::target_callback::c_ptr =  target_callback const*;
```

Const pointer to target callback. 

### using list

```cpp
using lava::target_callback::list =  std::vector<target_callback*>;
```

List of target callbacks. 

### using c_list

```cpp
using lava::target_callback::c_list =  std::vector<c_ptr>;
```

Const list of target callbacks. 

### using created_func

```cpp
using lava::target_callback::created_func =  std::function<bool(VkAttachmentsRef, rect::ref)>;
```

Created function. 

### using destroyed_func

```cpp
using lava::target_callback::destroyed_func =  std::function<void()>;
```

Destroy function. 

## Public Attributes Documentation

### variable on_created

```cpp
created_func on_created;
```

Called on target created. 

### variable on_destroyed

```cpp
destroyed_func on_destroyed;
```

Called on target destroyed. 

-------------------------------

Updated on 2026-02-01 at 18:13:39 +0000