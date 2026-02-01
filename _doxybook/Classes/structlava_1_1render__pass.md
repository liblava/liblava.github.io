---
title: lava::render_pass
summary: Render pass. 

---

# lava::render_pass



Render pass. 


`#include <render_pass.hpp>`

Inherits from [lava::entity](/_doxybook/Classes/structlava_1_1entity.md), [lava::no_copy_no_move](/_doxybook/Classes/structlava_1_1no__copy__no__move.md), [lava::interface](/_doxybook/Classes/structlava_1_1interface.md)

## Public Types

|                | Name           |
| -------------- | -------------- |
| using std::shared_ptr< [render_pass](/_doxybook/Classes/structlava_1_1render__pass.md) > | **[s_ptr](/_doxybook/Classes/structlava_1_1render__pass.md#using-s-ptr)** <br>Shared pointer to render pass.  |
| using std::vector< [s_ptr](/_doxybook/Classes/structlava_1_1render__pass.md#using-s-ptr) > | **[s_list](/_doxybook/Classes/structlava_1_1render__pass.md#using-s-list)** <br>List of render passes.  |

## Public Functions

|                | Name           |
| -------------- | -------------- |
| [s_ptr](/_doxybook/Classes/structlava_1_1render__pass.md#using-s-ptr) | **[make](/_doxybook/Classes/structlava_1_1render__pass.md#function-make)**([device::ptr](/_doxybook/Classes/structlava_1_1device.md#using-ptr) device)<br>Make a new render pass.  |
| | **[render_pass](/_doxybook/Classes/structlava_1_1render__pass.md#function-render-pass)**([device::ptr](/_doxybook/Classes/structlava_1_1device.md#using-ptr) device)<br>Construct a new render pass.  |
| bool | **[create](/_doxybook/Classes/structlava_1_1render__pass.md#function-create)**([VkAttachmentsRef](/_doxybook/Namespaces/namespacelava.md#using-vkattachmentsref) target_attachments, [rect::ref](/_doxybook/Classes/structlava_1_1rect.md#using-ref) area)<br>Create a new render pass.  |
| void | **[destroy](/_doxybook/Classes/structlava_1_1render__pass.md#function-destroy)**()<br>Destroy the render pass.  |
| void | **[process](/_doxybook/Classes/structlava_1_1render__pass.md#function-process)**(VkCommandBuffer cmd_buf, [index](/_doxybook/Namespaces/namespacelava.md#using-index) frame)<br>Process the render pass.  |
| [device::ptr](/_doxybook/Classes/structlava_1_1device.md#using-ptr) | **[get_device](/_doxybook/Classes/structlava_1_1render__pass.md#function-get-device)**()<br>Get the device.  |
| VkRenderPass | **[get](/_doxybook/Classes/structlava_1_1render__pass.md#function-get)**() const<br>Get the render pass.  |
| [ui32](/_doxybook/Namespaces/namespacelava.md#using-ui32) | **[get_subpass_count](/_doxybook/Classes/structlava_1_1render__pass.md#function-get-subpass-count)**() const<br>Get the subpass count.  |
| bool | **[exists_subpass](/_doxybook/Classes/structlava_1_1render__pass.md#function-exists-subpass)**([index](/_doxybook/Namespaces/namespacelava.md#using-index) index =0) const<br>Check if subpass exists.  |
| [subpass](/_doxybook/Classes/structlava_1_1subpass.md) * | **[get_subpass](/_doxybook/Classes/structlava_1_1render__pass.md#function-get-subpass)**([index](/_doxybook/Namespaces/namespacelava.md#using-index) index =0)<br>Get the subpass.  |
| [subpass::s_list](/_doxybook/Classes/structlava_1_1subpass.md#using-s-list) const & | **[get_subpasses](/_doxybook/Classes/structlava_1_1render__pass.md#function-get-subpasses)**() const<br>Get the subpasses.  |
| void | **[add](/_doxybook/Classes/structlava_1_1render__pass.md#function-add)**([attachment::s_ptr](/_doxybook/Classes/structlava_1_1attachment.md#using-s-ptr) const & attachment)<br>Add an attachment.  |
| void | **[add](/_doxybook/Classes/structlava_1_1render__pass.md#function-add)**([subpass_dependency::s_ptr](/_doxybook/Classes/structlava_1_1subpass__dependency.md#using-s-ptr) const & dependency)<br>Add a subpass dependency.  |
| void | **[add](/_doxybook/Classes/structlava_1_1render__pass.md#function-add)**([subpass::s_ptr](/_doxybook/Classes/structlava_1_1subpass.md#using-s-ptr) const & subpass)<br>Add a subpass.  |
| void | **[set_clear_values](/_doxybook/Classes/structlava_1_1render__pass.md#function-set-clear-values)**([VkClearValues](/_doxybook/Namespaces/namespacelava.md#using-vkclearvalues) const & values)<br>Set the clear values.  |
| [VkClearValues](/_doxybook/Namespaces/namespacelava.md#using-vkclearvalues) const & | **[get_clear_values](/_doxybook/Classes/structlava_1_1render__pass.md#function-get-clear-values)**() const<br>Get the clear values.  |
| void | **[set_clear_color](/_doxybook/Classes/structlava_1_1render__pass.md#function-set-clear-color)**([v3](/_doxybook/Namespaces/namespacelava.md#using-v3) value ={})<br>Set the clear color.  |
| [v3](/_doxybook/Namespaces/namespacelava.md#using-v3) | **[get_clear_color](/_doxybook/Classes/structlava_1_1render__pass.md#function-get-clear-color)**() const<br>Get the clear color.  |
| void | **[add](/_doxybook/Classes/structlava_1_1render__pass.md#function-add)**([render_pipeline::s_ptr](/_doxybook/Classes/structlava_1_1render__pipeline.md#using-s-ptr) pipeline, [index](/_doxybook/Namespaces/namespacelava.md#using-index) subpass =0)<br>Add a render pipeline to the back of subpass.  |
| void | **[add_front](/_doxybook/Classes/structlava_1_1render__pass.md#function-add-front)**([render_pipeline::s_ptr](/_doxybook/Classes/structlava_1_1render__pipeline.md#using-s-ptr) pipeline, [index](/_doxybook/Namespaces/namespacelava.md#using-index) subpass =0)<br>Add a render pipeline to the front of subpass.  |
| void | **[remove](/_doxybook/Classes/structlava_1_1render__pass.md#function-remove)**([render_pipeline::s_ptr](/_doxybook/Classes/structlava_1_1render__pipeline.md#using-s-ptr) pipeline, [index](/_doxybook/Namespaces/namespacelava.md#using-index) subpass =0)<br>Remove a render pipeline from the subpass.  |
| [target_callback](/_doxybook/Classes/structlava_1_1target__callback.md) const & | **[get_target_callback](/_doxybook/Classes/structlava_1_1render__pass.md#function-get-target-callback)**() const<br>Get the target callback.  |

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
using lava::render_pass::s_ptr =  std::shared_ptr<render_pass>;
```

Shared pointer to render pass. 

### using s_list

```cpp
using lava::render_pass::s_list =  std::vector<s_ptr>;
```

List of render passes. 

## Public Functions Documentation

### function make

```cpp
static inline s_ptr make(
    device::ptr device
)
```

Make a new render pass. 

**Parameters**: 

  * **device** Vulkan device 


**Return**: [s_ptr](/_doxybook/Classes/structlava_1_1render__pass.md#using-s-ptr) Shared pointer to render pass 

### function render_pass

```cpp
explicit render_pass(
    device::ptr device
)
```

Construct a new render pass. 

**Parameters**: 

  * **device** Vulkan device 


### function create

```cpp
bool create(
    VkAttachmentsRef target_attachments,
    rect::ref area
)
```

Create a new render pass. 

**Parameters**: 

  * **target_attachments** List of target attachments 
  * **area** Rectangle area 


**Return**: Create was successful or failed 

### function destroy

```cpp
void destroy()
```

Destroy the render pass. 

### function process

```cpp
void process(
    VkCommandBuffer cmd_buf,
    index frame
)
```

Process the render pass. 

**Parameters**: 

  * **cmd_buf** Command buffer 
  * **frame** Frame index 


### function get_device

```cpp
inline device::ptr get_device()
```

Get the device. 

**Return**: [device::ptr](/_doxybook/Classes/structlava_1_1device.md#using-ptr) Vulkan device 

### function get

```cpp
inline VkRenderPass get() const
```

Get the render pass. 

**Return**: VkRenderPass Vulkan render pass 

### function get_subpass_count

```cpp
inline ui32 get_subpass_count() const
```

Get the subpass count. 

**Return**: [ui32](/_doxybook/Namespaces/namespacelava.md#using-ui32) Number of subpasses 

### function exists_subpass

```cpp
inline bool exists_subpass(
    index index =0
) const
```

Check if subpass exists. 

**Parameters**: 

  * **index** Index to check 


**Return**: Subpass exists or not 

### function get_subpass

```cpp
inline subpass * get_subpass(
    index index =0
)
```

Get the subpass. 

**Parameters**: 

  * **index** Index of subpass 


**Return**: subpass* Subpass 

### function get_subpasses

```cpp
inline subpass::s_list const & get_subpasses() const
```

Get the subpasses. 

**Return**: [subpass::s_list](/_doxybook/Classes/structlava_1_1subpass.md#using-s-list) const& List of subpasses 

### function add

```cpp
inline void add(
    attachment::s_ptr const & attachment
)
```

Add an attachment. 

**Parameters**: 

  * **attachment** Attachment 


### function add

```cpp
inline void add(
    subpass_dependency::s_ptr const & dependency
)
```

Add a subpass dependency. 

**Parameters**: 

  * **dependency** Subpass dependency 


### function add

```cpp
inline void add(
    subpass::s_ptr const & subpass
)
```

Add a subpass. 

**Parameters**: 

  * **subpass** Subpass 


### function set_clear_values

```cpp
inline void set_clear_values(
    VkClearValues const & values
)
```

Set the clear values. 

**Parameters**: 

  * **values** List of clear values 


### function get_clear_values

```cpp
inline VkClearValues const & get_clear_values() const
```

Get the clear values. 

**Return**: [VkClearValues](/_doxybook/Namespaces/namespacelava.md#using-vkclearvalues) const& List of clear values 

### function set_clear_color

```cpp
void set_clear_color(
    v3 value ={}
)
```

Set the clear color. 

**Parameters**: 

  * **value** Clear color 


### function get_clear_color

```cpp
v3 get_clear_color() const
```

Get the clear color. 

**Return**: [v3](/_doxybook/Namespaces/namespacelava.md#using-v3) Clear color 

### function add

```cpp
inline void add(
    render_pipeline::s_ptr pipeline,
    index subpass =0
)
```

Add a render pipeline to the back of subpass. 

**Parameters**: 

  * **pipeline** Render pipeline 
  * **subpass** Subpass 


### function add_front

```cpp
inline void add_front(
    render_pipeline::s_ptr pipeline,
    index subpass =0
)
```

Add a render pipeline to the front of subpass. 

**Parameters**: 

  * **pipeline** Render pipeline 
  * **subpass** Subpass 


### function remove

```cpp
inline void remove(
    render_pipeline::s_ptr pipeline,
    index subpass =0
)
```

Remove a render pipeline from the subpass. 

**Parameters**: 

  * **pipeline** Render pipeline 
  * **subpass** Subpass 


### function get_target_callback

```cpp
inline target_callback const & get_target_callback() const
```

Get the target callback. 

**Return**: [target_callback](/_doxybook/Classes/structlava_1_1target__callback.md) const& Target callback 

-------------------------------

Updated on 2026-02-01 at 18:13:39 +0000