---
title: lava::attachment
summary: Attachment description. 

---

# lava::attachment



Attachment description. 


`#include <attachment.hpp>`

## Public Types

|                | Name           |
| -------------- | -------------- |
| using std::shared_ptr< [attachment](/_doxybook/Classes/structlava_1_1attachment.md) > | **[s_ptr](/_doxybook/Classes/structlava_1_1attachment.md#using-s-ptr)** <br>Shared pointer to attachment.  |
| using std::vector< [s_ptr](/_doxybook/Classes/structlava_1_1attachment.md#using-s-ptr) > | **[s_list](/_doxybook/Classes/structlava_1_1attachment.md#using-s-list)** <br>List of attachments.  |

## Public Functions

|                | Name           |
| -------------- | -------------- |
| [s_ptr](/_doxybook/Classes/structlava_1_1attachment.md#using-s-ptr) | **[make](/_doxybook/Classes/structlava_1_1attachment.md#function-make)**(VkFormat format =VK_FORMAT_UNDEFINED, VkSampleCountFlagBits samples =VK_SAMPLE_COUNT_1_BIT)<br>Make a new attachment.  |
| | **[attachment](/_doxybook/Classes/structlava_1_1attachment.md#function-attachment)**(VkFormat format =VK_FORMAT_UNDEFINED, VkSampleCountFlagBits samples =VK_SAMPLE_COUNT_1_BIT)<br>Construct a new attachment.  |
| VkAttachmentDescription const & | **[get_description](/_doxybook/Classes/structlava_1_1attachment.md#function-get-description)**() const<br>Get the description.  |
| void | **[set_format](/_doxybook/Classes/structlava_1_1attachment.md#function-set-format)**(VkFormat format)<br>Set the format.  |
| void | **[set_samples](/_doxybook/Classes/structlava_1_1attachment.md#function-set-samples)**(VkSampleCountFlagBits samples)<br>Set the samples.  |
| void | **[set_op](/_doxybook/Classes/structlava_1_1attachment.md#function-set-op)**(VkAttachmentLoadOp load_op, VkAttachmentStoreOp store_op)<br>Set the op.  |
| void | **[set_load_op](/_doxybook/Classes/structlava_1_1attachment.md#function-set-load-op)**(VkAttachmentLoadOp load_op)<br>Set the load op.  |
| void | **[set_store_op](/_doxybook/Classes/structlava_1_1attachment.md#function-set-store-op)**(VkAttachmentStoreOp store_op)<br>Set the store op.  |
| void | **[set_stencil_op](/_doxybook/Classes/structlava_1_1attachment.md#function-set-stencil-op)**(VkAttachmentLoadOp load_op, VkAttachmentStoreOp store_op)<br>Set the stencil op.  |
| void | **[set_stencil_load_op](/_doxybook/Classes/structlava_1_1attachment.md#function-set-stencil-load-op)**(VkAttachmentLoadOp load_op)<br>Set the stencil load op.  |
| void | **[set_stencil_store_op](/_doxybook/Classes/structlava_1_1attachment.md#function-set-stencil-store-op)**(VkAttachmentStoreOp store_op)<br>Set the stencil store op.  |
| void | **[set_layouts](/_doxybook/Classes/structlava_1_1attachment.md#function-set-layouts)**(VkImageLayout initial, VkImageLayout final)<br>Set the layouts.  |
| void | **[set_initial_layout](/_doxybook/Classes/structlava_1_1attachment.md#function-set-initial-layout)**(VkImageLayout layout)<br>Set the initial layout.  |
| void | **[set_final_layout](/_doxybook/Classes/structlava_1_1attachment.md#function-set-final-layout)**(VkImageLayout layout)<br>Set the final layout.  |

## Public Types Documentation

### using s_ptr

```cpp
using lava::attachment::s_ptr =  std::shared_ptr<attachment>;
```

Shared pointer to attachment. 

### using s_list

```cpp
using lava::attachment::s_list =  std::vector<s_ptr>;
```

List of attachments. 

## Public Functions Documentation

### function make

```cpp
static inline s_ptr make(
    VkFormat format =VK_FORMAT_UNDEFINED,
    VkSampleCountFlagBits samples =VK_SAMPLE_COUNT_1_BIT
)
```

Make a new attachment. 

**Parameters**: 

  * **format** Attachment format 
  * **samples** Sample count flag bits 


**Return**: [s_ptr](/_doxybook/Classes/structlava_1_1attachment.md#using-s-ptr) Shared pointer to attachment 

### function attachment

```cpp
inline explicit attachment(
    VkFormat format =VK_FORMAT_UNDEFINED,
    VkSampleCountFlagBits samples =VK_SAMPLE_COUNT_1_BIT
)
```

Construct a new attachment. 

**Parameters**: 

  * **format** Attachment format 
  * **samples** Sample count flag bits 


### function get_description

```cpp
inline VkAttachmentDescription const & get_description() const
```

Get the description. 

**Return**: VkAttachmentDescription const& Attachment description 

### function set_format

```cpp
inline void set_format(
    VkFormat format
)
```

Set the format. 

**Parameters**: 

  * **format** Attachment format 


### function set_samples

```cpp
inline void set_samples(
    VkSampleCountFlagBits samples
)
```

Set the samples. 

**Parameters**: 

  * **samples** Attachment sample count flag bits 


### function set_op

```cpp
inline void set_op(
    VkAttachmentLoadOp load_op,
    VkAttachmentStoreOp store_op
)
```

Set the op. 

**Parameters**: 

  * **load_op** Attachment load op 
  * **store_op** Attachment store op 


### function set_load_op

```cpp
inline void set_load_op(
    VkAttachmentLoadOp load_op
)
```

Set the load op. 

**Parameters**: 

  * **load_op** Attachment load op 


### function set_store_op

```cpp
inline void set_store_op(
    VkAttachmentStoreOp store_op
)
```

Set the store op. 

**Parameters**: 

  * **store_op** Attachment store op 


### function set_stencil_op

```cpp
inline void set_stencil_op(
    VkAttachmentLoadOp load_op,
    VkAttachmentStoreOp store_op
)
```

Set the stencil op. 

**Parameters**: 

  * **load_op** Attachment load op 
  * **store_op** Attachment store op 


### function set_stencil_load_op

```cpp
inline void set_stencil_load_op(
    VkAttachmentLoadOp load_op
)
```

Set the stencil load op. 

**Parameters**: 

  * **load_op** Attachment load op 


### function set_stencil_store_op

```cpp
inline void set_stencil_store_op(
    VkAttachmentStoreOp store_op
)
```

Set the stencil store op. 

**Parameters**: 

  * **store_op** Attachment store op 


### function set_layouts

```cpp
inline void set_layouts(
    VkImageLayout initial,
    VkImageLayout final
)
```

Set the layouts. 

**Parameters**: 

  * **initial** Initial image layout 
  * **final** Final image layout 


### function set_initial_layout

```cpp
inline void set_initial_layout(
    VkImageLayout layout
)
```

Set the initial layout. 

**Parameters**: 

  * **layout** Image layout 


### function set_final_layout

```cpp
inline void set_final_layout(
    VkImageLayout layout
)
```

Set the final layout. 

**Parameters**: 

  * **layout** Image layout 


-------------------------------

Updated on 2026-02-01 at 18:13:39 +0000