---
title: lava::vk_result
summary: Vulkan result. 

---

# lava::vk_result



Vulkan result. 


`#include <base.hpp>`

## Public Functions

|                | Name           |
| -------------- | -------------- |
| | **[operator bool](/_doxybook/Classes/structlava_1_1vk__result.md#function-operator-bool)**()<br>Check result.  |

## Public Attributes

|                | Name           |
| -------------- | -------------- |
| bool | **[state](/_doxybook/Classes/structlava_1_1vk__result.md#variable-state)** <br>State of result.  |
| VkResult | **[value](/_doxybook/Classes/structlava_1_1vk__result.md#variable-value)** <br>Value of result.  |

## Public Functions Documentation

### function operator bool

```cpp
inline operator bool()
```

Check result. 

**Return**: Okay or error 

## Public Attributes Documentation

### variable state

```cpp
bool state = false;
```

State of result. 

### variable value

```cpp
VkResult value = VK_NOT_READY;
```

Value of result. 

-------------------------------

Updated on 2026-02-01 at 18:13:39 +0000