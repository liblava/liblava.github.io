---
title: lava::image_loader
summary: Load image data from file and memory. 

---

# lava::image_loader



Load image data from file and memory. 


`#include <image_loader.hpp>`

## Public Functions

|                | Name           |
| -------------- | -------------- |
| | **[image_loader](/_doxybook/Classes/structlava_1_1image__loader.md#function-image-loader)**([string_ref](/_doxybook/Namespaces/namespacelava.md#using-string-ref) filename)<br>Construct a new image data from file.  |
| | **[image_loader](/_doxybook/Classes/structlava_1_1image__loader.md#function-image-loader)**([cdata::ref](/_doxybook/Classes/structlava_1_1cdata.md#using-ref) image)<br>Construct a new image data from memory.  |
| | **[~image_loader](/_doxybook/Classes/structlava_1_1image__loader.md#function-~image-loader)**()<br>Destroy the image data.  |
| bool | **[ready](/_doxybook/Classes/structlava_1_1image__loader.md#function-ready)**() const<br>Check if data is ready.  |
| [data_cptr](/_doxybook/Namespaces/namespacelava.md#using-data-cptr) | **[get](/_doxybook/Classes/structlava_1_1image__loader.md#function-get)**() const<br>Get image data.  |
| [size_t](/_doxybook/Namespaces/namespacelava.md#using-size-t) | **[size](/_doxybook/Classes/structlava_1_1image__loader.md#function-size)**() const<br>Get image data size.  |
| [uv2](/_doxybook/Namespaces/namespacelava.md#using-uv2) | **[get_dimensions](/_doxybook/Classes/structlava_1_1image__loader.md#function-get-dimensions)**() const<br>Get image dimensions.  |
| [ui32](/_doxybook/Namespaces/namespacelava.md#using-ui32) | **[get_channels](/_doxybook/Classes/structlava_1_1image__loader.md#function-get-channels)**() const<br>Get image channel count.  |

## Public Functions Documentation

### function image_loader

```cpp
explicit image_loader(
    string_ref filename
)
```

Construct a new image data from file. 

**Parameters**: 

  * **filename** File data to load 


### function image_loader

```cpp
explicit image_loader(
    cdata::ref image
)
```

Construct a new image data from memory. 

**Parameters**: 

  * **image** Memory data to load 


### function ~image_loader

```cpp
~image_loader()
```

Destroy the image data. 

### function ready

```cpp
inline bool ready() const
```

Check if data is ready. 

**Return**: Data is ready or not 

### function get

```cpp
inline data_cptr get() const
```

Get image data. 

**Return**: data_ptr Image data pointer 

### function size

```cpp
inline size_t size() const
```

Get image data size. 

**Return**: size_t Image data size 

### function get_dimensions

```cpp
inline uv2 get_dimensions() const
```

Get image dimensions. 

**Return**: uv2 Image dimensions 

### function get_channels

```cpp
inline ui32 get_channels() const
```

Get image channel count. 

**Return**: ui32 Channel count 

-------------------------------

Updated on 2024-03-22 at 21:51:37 +0000