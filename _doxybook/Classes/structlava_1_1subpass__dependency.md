---
title: lava::subpass_dependency
summary: Subpass dependency. 

---

# lava::subpass_dependency



Subpass dependency. 


`#include <subpass.hpp>`

## Public Types

|                | Name           |
| -------------- | -------------- |
| using std::shared_ptr< [subpass_dependency](/_doxybook/Classes/structlava_1_1subpass__dependency.md) > | **[s_ptr](/_doxybook/Classes/structlava_1_1subpass__dependency.md#using-s-ptr)** <br>Shared pointer to subpass dependency.  |
| using std::vector< [s_ptr](/_doxybook/Classes/structlava_1_1subpass__dependency.md#using-s-ptr) > | **[s_list](/_doxybook/Classes/structlava_1_1subpass__dependency.md#using-s-list)** <br>List of subpass dependencies.  |

## Public Functions

|                | Name           |
| -------------- | -------------- |
| [s_ptr](/_doxybook/Classes/structlava_1_1subpass__dependency.md#using-s-ptr) | **[make](/_doxybook/Classes/structlava_1_1subpass__dependency.md#function-make)**([ui32](/_doxybook/Namespaces/namespacelava.md#using-ui32) src_subpass, [ui32](/_doxybook/Namespaces/namespacelava.md#using-ui32) dst_subpass, VkDependencyFlags dependency_flags =VK_DEPENDENCY_BY_REGION_BIT)<br>Make a new subpass dependency.  |
| | **[subpass_dependency](/_doxybook/Classes/structlava_1_1subpass__dependency.md#function-subpass-dependency)**()<br>Construct a new subpass dependency.  |
| VkSubpassDependency const & | **[get_dependency](/_doxybook/Classes/structlava_1_1subpass__dependency.md#function-get-dependency)**() const<br>Get the dependency.  |
| void | **[set_subpass](/_doxybook/Classes/structlava_1_1subpass__dependency.md#function-set-subpass)**([ui32](/_doxybook/Namespaces/namespacelava.md#using-ui32) src, [ui32](/_doxybook/Namespaces/namespacelava.md#using-ui32) dst)<br>Set the subpass.  |
| void | **[set_src_subpass](/_doxybook/Classes/structlava_1_1subpass__dependency.md#function-set-src-subpass)**([ui32](/_doxybook/Namespaces/namespacelava.md#using-ui32) src)<br>Set the source subpass.  |
| void | **[set_dst_subpass](/_doxybook/Classes/structlava_1_1subpass__dependency.md#function-set-dst-subpass)**([ui32](/_doxybook/Namespaces/namespacelava.md#using-ui32) dst)<br>Set the dst subpass.  |
| void | **[set_stage_mask](/_doxybook/Classes/structlava_1_1subpass__dependency.md#function-set-stage-mask)**(VkPipelineStageFlags src, VkPipelineStageFlags dst)<br>Set the stage mask.  |
| void | **[set_src_stage_mask](/_doxybook/Classes/structlava_1_1subpass__dependency.md#function-set-src-stage-mask)**(VkPipelineStageFlags mask)<br>Set the source stage mask.  |
| void | **[set_dst_stage_mask](/_doxybook/Classes/structlava_1_1subpass__dependency.md#function-set-dst-stage-mask)**(VkPipelineStageFlags mask)<br>Set the destination stage mask.  |
| void | **[set_access_mask](/_doxybook/Classes/structlava_1_1subpass__dependency.md#function-set-access-mask)**(VkAccessFlags src, VkAccessFlags dst)<br>Set the access mask.  |
| void | **[set_src_access_mask](/_doxybook/Classes/structlava_1_1subpass__dependency.md#function-set-src-access-mask)**(VkAccessFlags mask)<br>Set the src access mask.  |
| void | **[set_dst_access_mask](/_doxybook/Classes/structlava_1_1subpass__dependency.md#function-set-dst-access-mask)**(VkAccessFlags mask)<br>Set the dst access mask.  |
| void | **[set_dependency_flags](/_doxybook/Classes/structlava_1_1subpass__dependency.md#function-set-dependency-flags)**(VkDependencyFlags flags)<br>Set the dependency flags.  |

## Public Types Documentation

### using s_ptr

```cpp
using lava::subpass_dependency::s_ptr =  std::shared_ptr<subpass_dependency>;
```

Shared pointer to subpass dependency. 

### using s_list

```cpp
using lava::subpass_dependency::s_list =  std::vector<s_ptr>;
```

List of subpass dependencies. 

## Public Functions Documentation

### function make

```cpp
static inline s_ptr make(
    ui32 src_subpass,
    ui32 dst_subpass,
    VkDependencyFlags dependency_flags =VK_DEPENDENCY_BY_REGION_BIT
)
```

Make a new subpass dependency. 

**Parameters**: 

  * **src_subpass** Source subpass 
  * **dst_subpass** Destination subpass 
  * **dependency_flags** Dependency flags 


**Return**: [s_ptr](/_doxybook/Classes/structlava_1_1subpass__dependency.md#using-s-ptr) Shared pointer to subpass dependency 

### function subpass_dependency

```cpp
explicit subpass_dependency()
```

Construct a new subpass dependency. 

### function get_dependency

```cpp
inline VkSubpassDependency const & get_dependency() const
```

Get the dependency. 

**Return**: VkSubpassDependency const& Vulkan subpass dependency 

### function set_subpass

```cpp
inline void set_subpass(
    ui32 src,
    ui32 dst
)
```

Set the subpass. 

**Parameters**: 

  * **src** Source Subpass 
  * **dst** Destination Subpass 


### function set_src_subpass

```cpp
inline void set_src_subpass(
    ui32 src
)
```

Set the source subpass. 

**Parameters**: 

  * **src** Source Subpass 


### function set_dst_subpass

```cpp
inline void set_dst_subpass(
    ui32 dst
)
```

Set the dst subpass. 

**Parameters**: 

  * **dst** Destination subpass 


### function set_stage_mask

```cpp
inline void set_stage_mask(
    VkPipelineStageFlags src,
    VkPipelineStageFlags dst
)
```

Set the stage mask. 

**Parameters**: 

  * **src** Source pipeline stage flags 
  * **dst** Destination pipeline stage flags 


### function set_src_stage_mask

```cpp
inline void set_src_stage_mask(
    VkPipelineStageFlags mask
)
```

Set the source stage mask. 

**Parameters**: 

  * **mask** Pipeline stage flags 


### function set_dst_stage_mask

```cpp
inline void set_dst_stage_mask(
    VkPipelineStageFlags mask
)
```

Set the destination stage mask. 

**Parameters**: 

  * **mask** Pipeline stage flags 


### function set_access_mask

```cpp
inline void set_access_mask(
    VkAccessFlags src,
    VkAccessFlags dst
)
```

Set the access mask. 

**Parameters**: 

  * **src** Source access flags 
  * **dst** Destination access flags 


### function set_src_access_mask

```cpp
inline void set_src_access_mask(
    VkAccessFlags mask
)
```

Set the src access mask. 

**Parameters**: 

  * **mask** Access flags 


### function set_dst_access_mask

```cpp
inline void set_dst_access_mask(
    VkAccessFlags mask
)
```

Set the dst access mask. 

**Parameters**: 

  * **mask** Access flags 


### function set_dependency_flags

```cpp
inline void set_dependency_flags(
    VkDependencyFlags flags
)
```

Set the dependency flags. 

**Parameters**: 

  * **flags** Dependency flags 


-------------------------------

Updated on 2026-02-01 at 18:13:39 +0000