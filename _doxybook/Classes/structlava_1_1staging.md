---
title: lava::staging
summary: Texture staging. 

---

# lava::staging



Texture staging. 


`#include <texture.hpp>`

## Public Functions

|                | Name           |
| -------------- | -------------- |
| void | **[add](/_doxybook/Classes/structlava_1_1staging.md#function-add)**([texture::ptr](/_doxybook/Classes/structlava_1_1texture.md#using-ptr) texture)<br>Add texture for staging.  |
| bool | **[stage](/_doxybook/Classes/structlava_1_1staging.md#function-stage)**(VkCommandBuffer cmd_buf, [index](/_doxybook/Namespaces/namespacelava.md#using-index) frame)<br>Stage textures.  |
| void | **[clear](/_doxybook/Classes/structlava_1_1staging.md#function-clear)**()<br>Clear staging.  |
| bool | **[busy](/_doxybook/Classes/structlava_1_1staging.md#function-busy)**() const<br>Check if staging is busy.  |

## Public Functions Documentation

### function add

```cpp
inline void add(
    texture::ptr texture
)
```

Add texture for staging. 

**Parameters**: 

  * **texture** Texture to stage 


### function stage

```cpp
bool stage(
    VkCommandBuffer cmd_buf,
    index frame
)
```

Stage textures. 

**Parameters**: 

  * **cmd_buf** Command buffer 
  * **frame** Frame index 


**Return**: Stage was successful or failed 

### function clear

```cpp
inline void clear()
```

Clear staging. 

### function busy

```cpp
inline bool busy() const
```

Check if staging is busy. 

**Return**: Staging is busy or not 

-------------------------------

Updated on 2022-11-30 at 01:16:04 +0000