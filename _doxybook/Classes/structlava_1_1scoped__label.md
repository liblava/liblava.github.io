---
title: lava::scoped_label
summary: Scoped debug util label. 

---

# lava::scoped_label



Scoped debug util label.  [More...](#detailed-description)


`#include <debug_utils.hpp>`

## Public Functions

|                | Name           |
| -------------- | -------------- |
| | **[scoped_label](/_doxybook/Classes/structlava_1_1scoped__label.md#function-scoped-label)**(T scope, [name](/_doxybook/Namespaces/namespacelava.md#using-name) label, [v4](/_doxybook/Namespaces/namespacelava.md#using-v4) color =[v4](/_doxybook/Namespaces/namespacelava.md#using-v4)(0.f))<br>Construct a new scoped label.  |
| | **[~scoped_label](/_doxybook/Classes/structlava_1_1scoped__label.md#function-~scoped-label)**()<br>Destroy the scoped label.  |

## Detailed Description

```cpp
template <typename T >
struct lava::scoped_label;
```

Scoped debug util label. 

**Template Parameters**: 

  * **T** VkCommandBuffer or VkQueue 

## Public Functions Documentation

### function scoped_label

```cpp
inline scoped_label(
    T scope,
    name label,
    v4 color =v4(0.f)
)
```

Construct a new scoped label. 

**Parameters**: 

  * **scope** Scoped label 
  * **label** Name of label 
  * **color** Color of label 


### function ~scoped_label

```cpp
inline ~scoped_label()
```

Destroy the scoped label. 

-------------------------------

Updated on 2026-02-01 at 18:13:39 +0000