---
title: lava::texture
summary: Texture. 

---

# lava::texture



Texture. 


`#include <texture.hpp>`

Inherits from [lava::entity](/_doxybook/Classes/structlava_1_1entity.md), [lava::no_copy_no_move](/_doxybook/Classes/structlava_1_1no__copy__no__move.md), [lava::interface](/_doxybook/Classes/structlava_1_1interface.md)

## Public Classes

|                | Name           |
| -------------- | -------------- |
| struct | **[layer](/_doxybook/Classes/structlava_1_1texture_1_1layer.md)** <br>Texture layer.  |
| struct | **[mip_level](/_doxybook/Classes/structlava_1_1texture_1_1mip__level.md)** <br>Texture mip level.  |

## Public Types

|                | Name           |
| -------------- | -------------- |
| using std::shared_ptr< [texture](/_doxybook/Classes/structlava_1_1texture.md) > | **[ptr](/_doxybook/Classes/structlava_1_1texture.md#using-ptr)** <br>Shared pointer to texture.  |
| using std::map< [id](/_doxybook/Classes/structlava_1_1id.md), [ptr](/_doxybook/Classes/structlava_1_1texture.md#using-ptr) > | **[map](/_doxybook/Classes/structlava_1_1texture.md#using-map)** <br>Map of textures.  |
| using std::vector< [ptr](/_doxybook/Classes/structlava_1_1texture.md#using-ptr) > | **[list](/_doxybook/Classes/structlava_1_1texture.md#using-list)** <br>List of textures.  |

## Public Functions

|                | Name           |
| -------------- | -------------- |
| [ptr](/_doxybook/Classes/structlava_1_1texture.md#using-ptr) | **[make](/_doxybook/Classes/structlava_1_1texture.md#function-make)**()<br>Make a new texture.  |
| | **[~texture](/_doxybook/Classes/structlava_1_1texture.md#function-~texture)**()<br>Destroy the texture.  |
| [bool](/_doxybook/Classes/structlava_1_1texture.md#using-map) | **[create](/_doxybook/Classes/structlava_1_1texture.md#function-create)**([device_p](/_doxybook/Namespaces/namespacelava.md#using-device-p) device, [uv2](/_doxybook/Namespaces/namespacelava.md#using-uv2) size, [VkFormat](/_doxybook/Classes/structlava_1_1texture.md#using-map) format, [layer::list](/_doxybook/Classes/structlava_1_1texture_1_1layer.md#using-list)[const](/_doxybook/Classes/structlava_1_1texture.md#using-map) & layers ={}, [texture_type](/_doxybook/Namespaces/namespacelava.md#enum-texture-type) type =texture_type::tex_2d)<br>Create a new texture.  |
| [void](/_doxybook/Classes/structlava_1_1texture.md#using-map) | **[destroy](/_doxybook/Classes/structlava_1_1texture.md#function-destroy)**()<br>Destroy the texture.  |
| [bool](/_doxybook/Classes/structlava_1_1texture.md#using-map) | **[upload](/_doxybook/Classes/structlava_1_1texture.md#function-upload)**([void](/_doxybook/Classes/structlava_1_1texture.md#using-map)[const](/_doxybook/Classes/structlava_1_1texture.md#using-map) * data, [size_t](/_doxybook/Namespaces/namespacelava.md#using-size-t) data_size)<br>Upload data to texture.  |
| [bool](/_doxybook/Classes/structlava_1_1texture.md#using-map) | **[stage](/_doxybook/Classes/structlava_1_1texture.md#function-stage)**([VkCommandBuffer](/_doxybook/Classes/structlava_1_1texture.md#using-map) cmd_buffer)<br>Stage the texture.  |
| [void](/_doxybook/Classes/structlava_1_1texture.md#using-map) | **[destroy_upload_buffer](/_doxybook/Classes/structlava_1_1texture.md#function-destroy-upload-buffer)**()<br>Destroy the upload buffer.  |
| [VkDescriptorImageInfo](/_doxybook/Classes/structlava_1_1texture.md#using-map)[const](/_doxybook/Classes/structlava_1_1texture.md#using-map) * | **[get_descriptor_info](/_doxybook/Classes/structlava_1_1texture.md#function-get-descriptor-info)**() const<br>Get the descriptor information.  |
| [image::ptr](/_doxybook/Classes/structlava_1_1image.md#using-ptr) | **[get_image](/_doxybook/Classes/structlava_1_1texture.md#function-get-image)**()<br>Get the image of the texture.  |
| [uv2](/_doxybook/Namespaces/namespacelava.md#using-uv2) | **[get_size](/_doxybook/Classes/structlava_1_1texture.md#function-get-size)**() const<br>Get the size of the texture.  |
| [texture_type](/_doxybook/Namespaces/namespacelava.md#enum-texture-type) | **[get_type](/_doxybook/Classes/structlava_1_1texture.md#function-get-type)**() const<br>Get the type of the texture.  |
| [VkFormat](/_doxybook/Classes/structlava_1_1texture.md#using-map) | **[get_format](/_doxybook/Classes/structlava_1_1texture.md#function-get-format)**() const<br>Get the format of the texture.  |

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

### using ptr

```cpp
using lava::texture::ptr =  std::shared_ptr<texture>;
```

Shared pointer to texture. 

### using map

```cpp
using lava::texture::map =  std::map<id, ptr>;
```

Map of textures. 

### using list

```cpp
using lava::texture::list =  std::vector<ptr>;
```

List of textures. 

## Public Functions Documentation

### function make

```cpp
static inline ptr make()
```

Make a new texture. 

**Return**: ptr Shared pointer to texture 

### function ~texture

```cpp
inline ~texture()
```

Destroy the texture. 

### function create

```cpp
bool create(
    device_p device,
    uv2 size,
    VkFormat format,
    layer::listconst & layers ={},
    texture_type type =texture_type::tex_2d
)
```

Create a new texture. 

**Parameters**: 

  * **device** Vulkan device 
  * **size** Texture size 
  * **format** Texture format 
  * **layers** List of layers 
  * **type** Texture type 


**Return**: Create was successful or failed 

### function destroy

```cpp
void destroy()
```

Destroy the texture. 

### function upload

```cpp
bool upload(
    voidconst * data,
    size_t data_size
)
```

Upload data to texture. 

**Parameters**: 

  * **data** Data to upload 
  * **data_size** Size of data 


**Return**: Upload was successful or failed 

### function stage

```cpp
bool stage(
    VkCommandBuffer cmd_buffer
)
```

Stage the texture. 

**Parameters**: 

  * **cmd_buffer** Command buffer 


**Return**: Stage was successful or failed 

### function destroy_upload_buffer

```cpp
void destroy_upload_buffer()
```

Destroy the upload buffer. 

### function get_descriptor_info

```cpp
inline VkDescriptorImageInfoconst * get_descriptor_info() const
```

Get the descriptor information. 

**Return**: VkDescriptorImageInfo const* Descriptor image information 

### function get_image

```cpp
inline image::ptr get_image()
```

Get the image of the texture. 

**Return**: [image::ptr](/_doxybook/Classes/structlava_1_1image.md#using-ptr) Shared pointer to image 

### function get_size

```cpp
inline uv2 get_size() const
```

Get the size of the texture. 

**Return**: uv2 Texture size 

### function get_type

```cpp
inline texture_type get_type() const
```

Get the type of the texture. 

**Return**: texture_type Texture type 

### function get_format

```cpp
inline VkFormat get_format() const
```

Get the format of the texture. 

**Return**: VkFormat Texture format 

-------------------------------

Updated on 2024-03-22 at 21:51:38 +0000