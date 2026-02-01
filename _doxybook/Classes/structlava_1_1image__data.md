---
title: lava::image_data
summary: Image data. 

---

# lava::image_data



Image data. 


`#include <image.hpp>`

## Public Types

|                | Name           |
| -------------- | -------------- |
| using std::shared_ptr< [image_data](/_doxybook/Classes/structlava_1_1image__data.md) > | **[s_ptr](/_doxybook/Classes/structlava_1_1image__data.md#using-s-ptr)** <br>Shared pointer to image data.  |

## Public Functions

|                | Name           |
| -------------- | -------------- |
| bool | **[ready](/_doxybook/Classes/structlava_1_1image__data.md#function-ready)**() const<br>Check if image data is ready.  |
| [data::ptr](/_doxybook/Classes/structlava_1_1data.md#using-ptr) | **[get_data](/_doxybook/Classes/structlava_1_1image__data.md#function-get-data)**()<br>Get image data.  |
| void | **[set_data](/_doxybook/Classes/structlava_1_1image__data.md#function-set-data)**([data::ptr](/_doxybook/Classes/structlava_1_1data.md#using-ptr) data)<br>Set image data.  |
| [size_t](/_doxybook/Namespaces/namespacelava.md#using-size-t) | **[size](/_doxybook/Classes/structlava_1_1image__data.md#function-size)**() const<br>Get image data size.  |
| | **[~image_data](/_doxybook/Classes/structlava_1_1image__data.md#function-~image-data)**()<br>Destroy the image data.  |

## Public Attributes

|                | Name           |
| -------------- | -------------- |
| [uv2](/_doxybook/Namespaces/namespacelava.md#using-uv2) | **[dimensions](/_doxybook/Classes/structlava_1_1image__data.md#variable-dimensions)** <br>Dimensions.  |
| [ui32](/_doxybook/Namespaces/namespacelava.md#using-ui32) | **[channels](/_doxybook/Classes/structlava_1_1image__data.md#variable-channels)** <br>Number of channels.  |

## Public Types Documentation

### using s_ptr

```cpp
using lava::image_data::s_ptr =  std::shared_ptr<image_data>;
```

Shared pointer to image data. 

## Public Functions Documentation

### function ready

```cpp
inline bool ready() const
```

Check if image data is ready. 

**Return**: Image data is ready or not 

### function get_data

```cpp
inline data::ptr get_data()
```

Get image data. 

**Return**: [data::ptr](/_doxybook/Classes/structlava_1_1data.md#using-ptr) Pointer to image data 

### function set_data

```cpp
inline void set_data(
    data::ptr data
)
```

Set image data. 

**Parameters**: 

  * **data** Pointer to image data 


### function size

```cpp
inline size_t size() const
```

Get image data size. 

**Return**: [size_t](/_doxybook/Namespaces/namespacelava.md#using-size-t) Image data size 

### function ~image_data

```cpp
~image_data()
```

Destroy the image data. 

## Public Attributes Documentation

### variable dimensions

```cpp
uv2 dimensions = uv2(0, 0);
```

Dimensions. 

### variable channels

```cpp
ui32 channels = 0;
```

Number of channels. 

-------------------------------

Updated on 2026-02-01 at 18:13:39 +0000