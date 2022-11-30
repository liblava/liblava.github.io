---
title: lava::producer
summary: Producer. 

---

# lava::producer



Producer. 


`#include <producer.hpp>`

## Public Types

|                | Name           |
| -------------- | -------------- |
| enum [index](/_doxybook/Namespaces/namespacelava.md#using-index) | **[shader_optimization](/_doxybook/Classes/structlava_1_1producer.md#enum-shader-optimization)** { none = 0, size, performance}<br>Shader optimization level.  |
| enum [index](/_doxybook/Namespaces/namespacelava.md#using-index) | **[shader_language](/_doxybook/Classes/structlava_1_1producer.md#enum-shader-language)** { glsl = 0, hlsl}<br>Shader source language.  |

## Public Functions

|                | Name           |
| -------------- | -------------- |
| [mesh::ptr](/_doxybook/Classes/structlava_1_1mesh__template.md#using-ptr) | **[create_mesh](/_doxybook/Classes/structlava_1_1producer.md#function-create-mesh)**([mesh_type](/_doxybook/Namespaces/namespacelava.md#enum-mesh-type) mesh_type)<br>Create a mesh product.  |
| [mesh::ptr](/_doxybook/Classes/structlava_1_1mesh__template.md#using-ptr) | **[get_mesh](/_doxybook/Classes/structlava_1_1producer.md#function-get-mesh)**([string_ref](/_doxybook/Namespaces/namespacelava.md#using-string-ref) name)<br>Get mesh by prop name.  |
| bool | **[add_mesh](/_doxybook/Classes/structlava_1_1producer.md#function-add-mesh)**([mesh::ptr](/_doxybook/Classes/structlava_1_1mesh__template.md#using-ptr) mesh)<br>Add mesh to products.  |
| [texture::ptr](/_doxybook/Classes/structlava_1_1texture.md#using-ptr) | **[create_texture](/_doxybook/Classes/structlava_1_1producer.md#function-create-texture)**([uv2](/_doxybook/Namespaces/namespacelava.md#using-uv2) size)<br>Create a texture product.  |
| [texture::ptr](/_doxybook/Classes/structlava_1_1texture.md#using-ptr) | **[get_texture](/_doxybook/Classes/structlava_1_1producer.md#function-get-texture)**([string_ref](/_doxybook/Namespaces/namespacelava.md#using-string-ref) name)<br>Get texture by prop name.  |
| bool | **[add_texture](/_doxybook/Classes/structlava_1_1producer.md#function-add-texture)**([texture::ptr](/_doxybook/Classes/structlava_1_1texture.md#using-ptr) product)<br>Add texture to products.  |
| [cdata](/_doxybook/Classes/structlava_1_1cdata.md) | **[get_shader](/_doxybook/Classes/structlava_1_1producer.md#function-get-shader)**([string_ref](/_doxybook/Namespaces/namespacelava.md#using-string-ref) name, bool reload =false)<br>Generate shader by prop name.  |
| [cdata](/_doxybook/Classes/structlava_1_1cdata.md) | **[reload_shader](/_doxybook/Classes/structlava_1_1producer.md#function-reload-shader)**([string_ref](/_doxybook/Namespaces/namespacelava.md#using-string-ref) name)<br>Regenerate shader by prop name.  |
| [data](/_doxybook/Classes/structlava_1_1data.md) | **[compile_shader](/_doxybook/Classes/structlava_1_1producer.md#function-compile-shader)**([cdata](/_doxybook/Classes/structlava_1_1cdata.md) product, [string_ref](/_doxybook/Namespaces/namespacelava.md#using-string-ref) name, [string_ref](/_doxybook/Namespaces/namespacelava.md#using-string-ref) filename) const<br>Compile shader.  |
| void | **[destroy](/_doxybook/Classes/structlava_1_1producer.md#function-destroy)**()<br>Destroy all products.  |
| void | **[clear](/_doxybook/Classes/structlava_1_1producer.md#function-clear)**()<br>Clear all products.  |

## Public Attributes

|                | Name           |
| -------------- | -------------- |
| [engine](/_doxybook/Classes/structlava_1_1engine.md) * | **[context](/_doxybook/Classes/structlava_1_1producer.md#variable-context)** <br>Engine.  |
| [id_registry](/_doxybook/Classes/structlava_1_1id__registry.md)< [mesh](/_doxybook/Namespaces/namespacelava.md#using-mesh), [string](/_doxybook/Namespaces/namespacelava.md#using-string) > | **[meshes](/_doxybook/Classes/structlava_1_1producer.md#variable-meshes)** <br>Mesh products.  |
| [id_registry](/_doxybook/Classes/structlava_1_1id__registry.md)< [texture](/_doxybook/Classes/structlava_1_1texture.md), [string](/_doxybook/Namespaces/namespacelava.md#using-string) > | **[textures](/_doxybook/Classes/structlava_1_1producer.md#variable-textures)** <br>Texture products.  |
| [shader_optimization](/_doxybook/Classes/structlava_1_1producer.md#enum-shader-optimization) | **[shader_opt](/_doxybook/Classes/structlava_1_1producer.md#variable-shader-opt)** <br>Shader optimization level.  |
| [shader_language](/_doxybook/Classes/structlava_1_1producer.md#enum-shader-language) | **[shader_lang](/_doxybook/Classes/structlava_1_1producer.md#variable-shader-lang)** <br>Shader source language.  |
| bool | **[shader_debug](/_doxybook/Classes/structlava_1_1producer.md#variable-shader-debug)** <br>Shader debug information.  |

## Public Types Documentation

### enum shader_optimization

| Enumerator | Value | Description |
| ---------- | ----- | ----------- |
| none | 0|   |
| size | |   |
| performance | |   |



Shader optimization level. 

### enum shader_language

| Enumerator | Value | Description |
| ---------- | ----- | ----------- |
| glsl | 0|   |
| hlsl | |   |



Shader source language. 

## Public Functions Documentation

### function create_mesh

```cpp
mesh::ptr create_mesh(
    mesh_type mesh_type
)
```

Create a mesh product. 

**Parameters**: 

  * **mesh_type** Type of mesh 


**Return**: [mesh::ptr](/_doxybook/Classes/structlava_1_1mesh__template.md#using-ptr) Mesh 

### function get_mesh

```cpp
mesh::ptr get_mesh(
    string_ref name
)
```

Get mesh by prop name. 

**Parameters**: 

  * **name** Name of prop 


**Return**: [mesh::ptr](/_doxybook/Classes/structlava_1_1mesh__template.md#using-ptr) Mesh 

### function add_mesh

```cpp
bool add_mesh(
    mesh::ptr mesh
)
```

Add mesh to products. 

**Parameters**: 

  * **mesh** Mesh 


**Return**: Added to products or already exists 

### function create_texture

```cpp
texture::ptr create_texture(
    uv2 size
)
```

Create a texture product. 

**Parameters**: 

  * **size** Size of texture 


**Return**: [texture::ptr](/_doxybook/Classes/structlava_1_1texture.md#using-ptr) Default texture 

### function get_texture

```cpp
texture::ptr get_texture(
    string_ref name
)
```

Get texture by prop name. 

**Parameters**: 

  * **name** Name of prop 


**Return**: [texture::ptr](/_doxybook/Classes/structlava_1_1texture.md#using-ptr) Texture 

### function add_texture

```cpp
bool add_texture(
    texture::ptr product
)
```

Add texture to products. 

**Parameters**: 

  * **product** Texture 


**Return**: Added to products or already exists 

### function get_shader

```cpp
cdata get_shader(
    string_ref name,
    bool reload =false
)
```

Generate shader by prop name. 

**Parameters**: 

  * **name** Name of shader 
  * **reload** Reload shader 


**Return**: cdata Shader data 

### function reload_shader

```cpp
inline cdata reload_shader(
    string_ref name
)
```

Regenerate shader by prop name. 

**Parameters**: 

  * **name** Name of shader 


**Return**: cdata Shader data 

### function compile_shader

```cpp
data compile_shader(
    cdata product,
    string_ref name,
    string_ref filename
) const
```

Compile shader. 

**Parameters**: 

  * **product** Shader data 
  * **name** Shader name 
  * **filename** Shader filename 


**Return**: data Compiled shader data 

### function destroy

```cpp
void destroy()
```

Destroy all products. 

### function clear

```cpp
void clear()
```

Clear all products. 

## Public Attributes Documentation

### variable context

```cpp
engine * context = nullptr;
```

Engine. 

### variable meshes

```cpp
id_registry< mesh, string > meshes;
```

Mesh products. 

### variable textures

```cpp
id_registry< texture, string > textures;
```

Texture products. 

### variable shader_opt

```cpp
shader_optimization shader_opt = shader_optimization::performance;
```

Shader optimization level. 

### variable shader_lang

```cpp
shader_language shader_lang = shader_language::glsl;
```

Shader source language. 

### variable shader_debug

```cpp
bool shader_debug = false;
```

Shader debug information. 

-------------------------------

Updated on 2022-11-30 at 01:16:04 +0000