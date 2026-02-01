---
title: lava::swapchain::callback
summary: Swapchain callback. 

---

# lava::swapchain::callback



Swapchain callback. 


`#include <swapchain.hpp>`

## Public Types

|                | Name           |
| -------------- | -------------- |
| using std::vector< [callback](/_doxybook/Classes/structlava_1_1swapchain_1_1callback.md) * > | **[list](/_doxybook/Classes/structlava_1_1swapchain_1_1callback.md#using-list)** <br>List of callbacks.  |
| using std::function< bool()> | **[created_func](/_doxybook/Classes/structlava_1_1swapchain_1_1callback.md#using-created-func)** <br>Created function.  |
| using std::function< void()> | **[destroyed_func](/_doxybook/Classes/structlava_1_1swapchain_1_1callback.md#using-destroyed-func)** <br>Destroyed function.  |

## Public Attributes

|                | Name           |
| -------------- | -------------- |
| [created_func](/_doxybook/Classes/structlava_1_1swapchain_1_1callback.md#using-created-func) | **[on_created](/_doxybook/Classes/structlava_1_1swapchain_1_1callback.md#variable-on-created)** <br>Called on swapchain created.  |
| [destroyed_func](/_doxybook/Classes/structlava_1_1swapchain_1_1callback.md#using-destroyed-func) | **[on_destroyed](/_doxybook/Classes/structlava_1_1swapchain_1_1callback.md#variable-on-destroyed)** <br>Called on swapchain destroyed.  |

## Public Types Documentation

### using list

```cpp
using lava::swapchain::callback::list =  std::vector<callback*>;
```

List of callbacks. 

### using created_func

```cpp
using lava::swapchain::callback::created_func =  std::function<bool()>;
```

Created function. 

### using destroyed_func

```cpp
using lava::swapchain::callback::destroyed_func =  std::function<void()>;
```

Destroyed function. 

## Public Attributes Documentation

### variable on_created

```cpp
created_func on_created;
```

Called on swapchain created. 

### variable on_destroyed

```cpp
destroyed_func on_destroyed;
```

Called on swapchain destroyed. 

-------------------------------

Updated on 2026-02-01 at 18:13:39 +0000