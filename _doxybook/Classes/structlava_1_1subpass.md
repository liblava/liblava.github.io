---
title: lava::subpass
summary: Subpass. 

---

# lava::subpass



Subpass. 


`#include <subpass.hpp>`

Inherits from [lava::entity](/_doxybook/Classes/structlava_1_1entity.md), [lava::no_copy_no_move](/_doxybook/Classes/structlava_1_1no__copy__no__move.md), [lava::interface](/_doxybook/Classes/structlava_1_1interface.md)

## Public Types

|                | Name           |
| -------------- | -------------- |
| using std::shared_ptr< [subpass](/_doxybook/Classes/structlava_1_1subpass.md) > | **[s_ptr](/_doxybook/Classes/structlava_1_1subpass.md#using-s-ptr)** <br>Shared pointer to subpass.  |
| using std::vector< [s_ptr](/_doxybook/Classes/structlava_1_1subpass.md#using-s-ptr) > | **[s_list](/_doxybook/Classes/structlava_1_1subpass.md#using-s-list)** <br>List of subpasses.  |

## Public Functions

|                | Name           |
| -------------- | -------------- |
| [s_ptr](/_doxybook/Classes/structlava_1_1subpass.md#using-s-ptr) | **[make](/_doxybook/Classes/structlava_1_1subpass.md#function-make)**(VkPipelineBindPoint pipeline_bind_point =VK_PIPELINE_BIND_POINT_GRAPHICS)<br>Make a new subpass.  |
| | **[subpass](/_doxybook/Classes/structlava_1_1subpass.md#function-subpass)**()<br>Construct a new subpass.  |
| void | **[destroy](/_doxybook/Classes/structlava_1_1subpass.md#function-destroy)**()<br>Destroy the subpass.  |
| void | **[add](/_doxybook/Classes/structlava_1_1subpass.md#function-add)**([render_pipeline::s_ptr](/_doxybook/Classes/structlava_1_1render__pipeline.md#using-s-ptr) const & pipeline)<br>Add a render pipeline to the back of the subpass.  |
| void | **[add_front](/_doxybook/Classes/structlava_1_1subpass.md#function-add-front)**([render_pipeline::s_ptr](/_doxybook/Classes/structlava_1_1render__pipeline.md#using-s-ptr) const & pipeline)<br>Add a render pipeline to the fronst of the subpass.  |
| void | **[remove](/_doxybook/Classes/structlava_1_1subpass.md#function-remove)**([render_pipeline::s_ptr](/_doxybook/Classes/structlava_1_1render__pipeline.md#using-s-ptr) pipeline)<br>Remove the render pipeline.  |
| void | **[clear_pipelines](/_doxybook/Classes/structlava_1_1subpass.md#function-clear-pipelines)**()<br>Clear all pipelines.  |
| void | **[process](/_doxybook/Classes/structlava_1_1subpass.md#function-process)**(VkCommandBuffer cmd_buf, [uv2](/_doxybook/Namespaces/namespacelava.md#using-uv2) size)<br>Process the subpass.  |
| VkSubpassDescription const & | **[get_description](/_doxybook/Classes/structlava_1_1subpass.md#function-get-description)**() const<br>Get the description.  |
| void | **[set](/_doxybook/Classes/structlava_1_1subpass.md#function-set)**(VkPipelineBindPoint pipeline_bind_point)<br>Set pipeline bind point.  |
| void | **[set_color_attachment](/_doxybook/Classes/structlava_1_1subpass.md#function-set-color-attachment)**([index](/_doxybook/Namespaces/namespacelava.md#using-index) attachment, VkImageLayout layout)<br>Set the color attachment.  |
| void | **[set_color_attachment](/_doxybook/Classes/structlava_1_1subpass.md#function-set-color-attachment)**(VkAttachmentReference attachment)<br>Set the color attachment.  |
| void | **[set_color_attachments](/_doxybook/Classes/structlava_1_1subpass.md#function-set-color-attachments)**([VkAttachmentReferences](/_doxybook/Namespaces/namespacelava.md#using-vkattachmentreferences) const & attachments)<br>Set the color attachments.  |
| void | **[set_depth_stencil_attachment](/_doxybook/Classes/structlava_1_1subpass.md#function-set-depth-stencil-attachment)**([index](/_doxybook/Namespaces/namespacelava.md#using-index) attachment, VkImageLayout layout)<br>Set the depth stencil attachment.  |
| void | **[set_depth_stencil_attachment](/_doxybook/Classes/structlava_1_1subpass.md#function-set-depth-stencil-attachment)**(VkAttachmentReference attachment)<br>Set the depth stencil attachment.  |
| void | **[set_input_attachment](/_doxybook/Classes/structlava_1_1subpass.md#function-set-input-attachment)**([index](/_doxybook/Namespaces/namespacelava.md#using-index) attachment, VkImageLayout layout)<br>Set the input attachment.  |
| void | **[set_input_attachment](/_doxybook/Classes/structlava_1_1subpass.md#function-set-input-attachment)**(VkAttachmentReference attachment)<br>Set the input attachment.  |
| void | **[set_input_attachments](/_doxybook/Classes/structlava_1_1subpass.md#function-set-input-attachments)**([VkAttachmentReferences](/_doxybook/Namespaces/namespacelava.md#using-vkattachmentreferences) const & attachments)<br>Set the input attachments.  |
| void | **[set_resolve_attachment](/_doxybook/Classes/structlava_1_1subpass.md#function-set-resolve-attachment)**([index](/_doxybook/Namespaces/namespacelava.md#using-index) attachment, VkImageLayout layout)<br>Set the resolve attachment.  |
| void | **[set_resolve_attachment](/_doxybook/Classes/structlava_1_1subpass.md#function-set-resolve-attachment)**(VkAttachmentReference attachment)<br>Set the resolve attachment.  |
| void | **[set_resolve_attachments](/_doxybook/Classes/structlava_1_1subpass.md#function-set-resolve-attachments)**([VkAttachmentReferences](/_doxybook/Namespaces/namespacelava.md#using-vkattachmentreferences) const & attachments)<br>Set the resolve attachments.  |
| void | **[add_preserve_attachment](/_doxybook/Classes/structlava_1_1subpass.md#function-add-preserve-attachment)**([index](/_doxybook/Namespaces/namespacelava.md#using-index) attachment)<br>Add preserve attachment.  |
| void | **[set_preserve_attachments](/_doxybook/Classes/structlava_1_1subpass.md#function-set-preserve-attachments)**([index_list](/_doxybook/Namespaces/namespacelava.md#using-index-list) const & attachments)<br>Set the preserve attachments.  |
| void | **[set_active](/_doxybook/Classes/structlava_1_1subpass.md#function-set-active)**(bool value =true)<br>Activate or deactivate the subpass.  |
| bool | **[activated](/_doxybook/Classes/structlava_1_1subpass.md#function-activated)**() const<br>Check if subpass is active.  |

## Additional inherited members

**Public Functions inherited from [lava::entity](/_doxybook/Classes/structlava_1_1entity.md)**

|                | Name           |
| -------------- | -------------- |
| | **[entity](/_doxybook/Classes/structlava_1_1entity.md#function-entity)**()<br>Construct a new entity.  |
| [id::ref](/_doxybook/Classes/structlava_1_1id.md#using-ref) | **[get_id](/_doxybook/Classes/structlava_1_1entity.md#function-get-id)**() const<br>Get the id of entity.  |

**Public Functions inherited from [lava::no_copy_no_move](/_doxybook/Classes/structlava_1_1no__copy__no__move.md)**

|                | Name           |
| -------------- | -------------- |
| | **[no_copy_no_move](/_doxybook/Classes/structlava_1_1no__copy__no__move.md#function-no-copy-no-move)**() =default<br>Construct a new object.  |
| | **[no_copy_no_move](/_doxybook/Classes/structlava_1_1no__copy__no__move.md#function-no-copy-no-move)**([no_copy_no_move](/_doxybook/Classes/structlava_1_1no__copy__no__move.md) const & ) =delete<br>No copy.  |
| void | **[operator=](/_doxybook/Classes/structlava_1_1no__copy__no__move.md#function-operator=)**([no_copy_no_move](/_doxybook/Classes/structlava_1_1no__copy__no__move.md) const & ) =delete<br>No move.  |

**Public Functions inherited from [lava::interface](/_doxybook/Classes/structlava_1_1interface.md)**

|                | Name           |
| -------------- | -------------- |
| virtual | **[~interface](/_doxybook/Classes/structlava_1_1interface.md#function-~interface)**() =default<br>Destroy the interface.  |


## Public Types Documentation

### using s_ptr

```cpp
using lava::subpass::s_ptr =  std::shared_ptr<subpass>;
```

Shared pointer to subpass. 

### using s_list

```cpp
using lava::subpass::s_list =  std::vector<s_ptr>;
```

List of subpasses. 

## Public Functions Documentation

### function make

```cpp
static inline s_ptr make(
    VkPipelineBindPoint pipeline_bind_point =VK_PIPELINE_BIND_POINT_GRAPHICS
)
```

Make a new subpass. 

**Parameters**: 

  * **pipeline_bind_point** Pipeline bind point 


**Return**: [s_ptr](/_doxybook/Classes/structlava_1_1subpass.md#using-s-ptr) Shared pointer to subpass 

### function subpass

```cpp
explicit subpass()
```

Construct a new subpass. 

### function destroy

```cpp
void destroy()
```

Destroy the subpass. 

### function add

```cpp
inline void add(
    render_pipeline::s_ptr const & pipeline
)
```

Add a render pipeline to the back of the subpass. 

**Parameters**: 

  * **pipeline** Render pipeline 


### function add_front

```cpp
inline void add_front(
    render_pipeline::s_ptr const & pipeline
)
```

Add a render pipeline to the fronst of the subpass. 

**Parameters**: 

  * **pipeline** Render pipeline 


### function remove

```cpp
void remove(
    render_pipeline::s_ptr pipeline
)
```

Remove the render pipeline. 

**Parameters**: 

  * **pipeline** Render pipeline 


### function clear_pipelines

```cpp
void clear_pipelines()
```

Clear all pipelines. 

### function process

```cpp
void process(
    VkCommandBuffer cmd_buf,
    uv2 size
)
```

Process the subpass. 

**Parameters**: 

  * **cmd_buf** Command buffer 
  * **size** Size of render pass 


### function get_description

```cpp
inline VkSubpassDescription const & get_description() const
```

Get the description. 

**Return**: VkSubpassDescription const& Subpass description 

### function set

```cpp
inline void set(
    VkPipelineBindPoint pipeline_bind_point
)
```

Set pipeline bind point. 

**Parameters**: 

  * **pipeline_bind_point** Pipeline bind point 


### function set_color_attachment

```cpp
void set_color_attachment(
    index attachment,
    VkImageLayout layout
)
```

Set the color attachment. 

**Parameters**: 

  * **attachment** Index of attachment 
  * **layout** Image layout 


### function set_color_attachment

```cpp
void set_color_attachment(
    VkAttachmentReference attachment
)
```

Set the color attachment. 

**Parameters**: 

  * **attachment** Attachment reference 


### function set_color_attachments

```cpp
void set_color_attachments(
    VkAttachmentReferences const & attachments
)
```

Set the color attachments. 

**Parameters**: 

  * **attachments** List of attachment references 


### function set_depth_stencil_attachment

```cpp
void set_depth_stencil_attachment(
    index attachment,
    VkImageLayout layout
)
```

Set the depth stencil attachment. 

**Parameters**: 

  * **attachment** Index of attachment 
  * **layout** Image layout 


### function set_depth_stencil_attachment

```cpp
void set_depth_stencil_attachment(
    VkAttachmentReference attachment
)
```

Set the depth stencil attachment. 

**Parameters**: 

  * **attachment** Attachment reference 


### function set_input_attachment

```cpp
void set_input_attachment(
    index attachment,
    VkImageLayout layout
)
```

Set the input attachment. 

**Parameters**: 

  * **attachment** Index of attachment 
  * **layout** Image layout 


### function set_input_attachment

```cpp
void set_input_attachment(
    VkAttachmentReference attachment
)
```

Set the input attachment. 

**Parameters**: 

  * **attachment** Attachment reference 


### function set_input_attachments

```cpp
void set_input_attachments(
    VkAttachmentReferences const & attachments
)
```

Set the input attachments. 

**Parameters**: 

  * **attachments** List of attachment references 


### function set_resolve_attachment

```cpp
void set_resolve_attachment(
    index attachment,
    VkImageLayout layout
)
```

Set the resolve attachment. 

**Parameters**: 

  * **attachment** Index of attachment 
  * **layout** Image layout 


### function set_resolve_attachment

```cpp
void set_resolve_attachment(
    VkAttachmentReference attachment
)
```

Set the resolve attachment. 

**Parameters**: 

  * **attachment** Attachment reference 


### function set_resolve_attachments

```cpp
void set_resolve_attachments(
    VkAttachmentReferences const & attachments
)
```

Set the resolve attachments. 

**Parameters**: 

  * **attachments** List of attachment references 


### function add_preserve_attachment

```cpp
void add_preserve_attachment(
    index attachment
)
```

Add preserve attachment. 

**Parameters**: 

  * **attachment** Index of attachment 


### function set_preserve_attachments

```cpp
void set_preserve_attachments(
    index_list const & attachments
)
```

Set the preserve attachments. 

**Parameters**: 

  * **attachments** List of indices 


### function set_active

```cpp
inline void set_active(
    bool value =true
)
```

Activate or deactivate the subpass. 

**Parameters**: 

  * **value** Enable state 


### function activated

```cpp
inline bool activated() const
```

Check if subpass is active. 

**Return**: Subpass is active or not 

-------------------------------

Updated on 2026-02-01 at 18:13:39 +0000