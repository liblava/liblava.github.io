---
title: lava::mesh_template
summary: Temporary templated mesh. 

---

# lava::mesh_template



Temporary templated mesh.  [More...](#detailed-description)


`#include <mesh.hpp>`

Inherits from [lava::entity](/_doxybook/Classes/structlava_1_1entity.md), [lava::no_copy_no_move](/_doxybook/Classes/structlava_1_1no__copy__no__move.md), [lava::interface](/_doxybook/Classes/structlava_1_1interface.md)

## Public Types

|                | Name           |
| -------------- | -------------- |
| using std::shared_ptr< [mesh_template](/_doxybook/Classes/structlava_1_1mesh__template.md)< T > > | **[ptr](/_doxybook/Classes/structlava_1_1mesh__template.md#using-ptr)** <br>Shared pointer to mesh.  |
| using std::map< [id](/_doxybook/Classes/structlava_1_1id.md), [ptr](/_doxybook/Classes/structlava_1_1mesh__template.md#using-ptr) > | **[map](/_doxybook/Classes/structlava_1_1mesh__template.md#using-map)** <br>Map of meshes.  |
| using std::vector< [ptr](/_doxybook/Classes/structlava_1_1mesh__template.md#using-ptr) > | **[list](/_doxybook/Classes/structlava_1_1mesh__template.md#using-list)** <br>List of meshes.  |
| using std::vector< T > | **[vertex_list](/_doxybook/Classes/structlava_1_1mesh__template.md#using-vertex-list)** <br>List of vertices.  |

## Public Functions

|                | Name           |
| -------------- | -------------- |
| [ptr](/_doxybook/Classes/structlava_1_1mesh__template.md#using-ptr) | **[make](/_doxybook/Classes/structlava_1_1mesh__template.md#function-make)**()<br>Make a new mesh.  |
| | **[~mesh_template](/_doxybook/Classes/structlava_1_1mesh__template.md#function-~mesh-template)**()<br>Destroy the mesh.  |
| [bool](/_doxybook/Classes/structlava_1_1mesh__template.md#using-map) | **[create](/_doxybook/Classes/structlava_1_1mesh__template.md#function-create)**([device_p](/_doxybook/Namespaces/namespacelava.md#using-device-p) device, [bool](/_doxybook/Classes/structlava_1_1mesh__template.md#using-map) mapped =[false](/_doxybook/Classes/structlava_1_1mesh__template.md#using-map), [VmaMemoryUsage](/_doxybook/Classes/structlava_1_1mesh__template.md#using-map) memory_usage =[VMA_MEMORY_USAGE_CPU_TO_GPU](/_doxybook/Classes/structlava_1_1mesh__template.md#using-map))<br>Create a new mesh.  |
| [void](/_doxybook/Classes/structlava_1_1mesh__template.md#using-map) | **[destroy](/_doxybook/Classes/structlava_1_1mesh__template.md#function-destroy)**()<br>Destroy the mesh.  |
| [void](/_doxybook/Classes/structlava_1_1mesh__template.md#using-map) | **[bind](/_doxybook/Classes/structlava_1_1mesh__template.md#function-bind)**([VkCommandBuffer](/_doxybook/Classes/structlava_1_1mesh__template.md#using-map) cmd_buf) const<br>Bind the mesh.  |
| [void](/_doxybook/Classes/structlava_1_1mesh__template.md#using-map) | **[draw](/_doxybook/Classes/structlava_1_1mesh__template.md#function-draw)**([VkCommandBuffer](/_doxybook/Classes/structlava_1_1mesh__template.md#using-map) cmd_buf) const<br>Draw the mesh.  |
| [void](/_doxybook/Classes/structlava_1_1mesh__template.md#using-map) | **[bind_draw](/_doxybook/Classes/structlava_1_1mesh__template.md#function-bind-draw)**([VkCommandBuffer](/_doxybook/Classes/structlava_1_1mesh__template.md#using-map) cmd_buf) const<br>Bind and draw the mesh.  |
| [bool](/_doxybook/Classes/structlava_1_1mesh__template.md#using-map) | **[empty](/_doxybook/Classes/structlava_1_1mesh__template.md#function-empty)**() const<br>Check if mesh is empty.  |
| [void](/_doxybook/Classes/structlava_1_1mesh__template.md#using-map) | **[set_data](/_doxybook/Classes/structlava_1_1mesh__template.md#function-set-data)**([mesh_template_data](/_doxybook/Classes/structlava_1_1mesh__template__data.md)< T > [const](/_doxybook/Classes/structlava_1_1mesh__template.md#using-map) & value)<br>Set the mesh data.  |
| [mesh_template_data](/_doxybook/Classes/structlava_1_1mesh__template__data.md)< T > & | **[get_data](/_doxybook/Classes/structlava_1_1mesh__template.md#function-get-data)**()<br>Get the mesh data.  |
| [void](/_doxybook/Classes/structlava_1_1mesh__template.md#using-map) | **[add_data](/_doxybook/Classes/structlava_1_1mesh__template.md#function-add-data)**([mesh_template_data](/_doxybook/Classes/structlava_1_1mesh__template__data.md)< T > [const](/_doxybook/Classes/structlava_1_1mesh__template.md#using-map) & value)<br>Add mesh data to existing data.  |
| [vertex_list](/_doxybook/Classes/structlava_1_1mesh__template.md#using-vertex-list) & | **[get_vertices](/_doxybook/Classes/structlava_1_1mesh__template.md#function-get-vertices)**()<br>Get the vertices of the mesh.  |
| [vertex_list](/_doxybook/Classes/structlava_1_1mesh__template.md#using-vertex-list)[const](/_doxybook/Classes/structlava_1_1mesh__template.md#using-map) & | **[get_vertices](/_doxybook/Classes/structlava_1_1mesh__template.md#function-get-vertices)**() const<br>Get the const vertices of the mesh.  |
| [ui32](/_doxybook/Namespaces/namespacelava.md#using-ui32) | **[get_vertices_count](/_doxybook/Classes/structlava_1_1mesh__template.md#function-get-vertices-count)**() const<br>Get the vertices count of the mesh.  |
| [index_list](/_doxybook/Namespaces/namespacelava.md#using-index-list) & | **[get_indices](/_doxybook/Classes/structlava_1_1mesh__template.md#function-get-indices)**()<br>Get the indices of the mesh.  |
| [index_list](/_doxybook/Namespaces/namespacelava.md#using-index-list)[const](/_doxybook/Classes/structlava_1_1mesh__template.md#using-map) & | **[get_indices](/_doxybook/Classes/structlava_1_1mesh__template.md#function-get-indices)**() const<br>Get the const indices of the mesh.  |
| [ui32](/_doxybook/Namespaces/namespacelava.md#using-ui32) | **[get_indices_count](/_doxybook/Classes/structlava_1_1mesh__template.md#function-get-indices-count)**() const<br>Get the indices count of the mesh.  |
| [bool](/_doxybook/Classes/structlava_1_1mesh__template.md#using-map) | **[reload](/_doxybook/Classes/structlava_1_1mesh__template.md#function-reload)**()<br>Reload the mesh data.  |
| [buffer::ptr](/_doxybook/Classes/structlava_1_1buffer.md#using-ptr) | **[get_vertex_buffer](/_doxybook/Classes/structlava_1_1mesh__template.md#function-get-vertex-buffer)**()<br>Get the vertex buffer of the mesh.  |
| [buffer::ptr](/_doxybook/Classes/structlava_1_1buffer.md#using-ptr) | **[get_index_buffer](/_doxybook/Classes/structlava_1_1mesh__template.md#function-get-index-buffer)**()<br>Get the index buffer of the mesh.  |

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


## Detailed Description

```cpp
template <typename T  =vertex>
struct lava::mesh_template;
```

Temporary templated mesh. 

**Template Parameters**: 

  * **T** Vertex struct typename 

## Public Types Documentation

### using ptr

```cpp
using lava::mesh_template< T >::ptr =  std::shared_ptr<mesh_template<T>>;
```

Shared pointer to mesh. 

### using map

```cpp
using lava::mesh_template< T >::map =  std::map<id, ptr>;
```

Map of meshes. 

### using list

```cpp
using lava::mesh_template< T >::list =  std::vector<ptr>;
```

List of meshes. 

### using vertex_list

```cpp
using lava::mesh_template< T >::vertex_list =  std::vector<T>;
```

List of vertices. 

## Public Functions Documentation

### function make

```cpp
static inline ptr make()
```

Make a new mesh. 

**Return**: ptr Shared pointer to mesh 

### function ~mesh_template

```cpp
inline ~mesh_template()
```

Destroy the mesh. 

### function create

```cpp
bool create(
    device_p device,
    bool mapped =false,
    VmaMemoryUsage memory_usage =VMA_MEMORY_USAGE_CPU_TO_GPU
)
```

Create a new mesh. 

**Parameters**: 

  * **device** Vulkan device 
  * **mapped** Map mesh data 
  * **memory_usage** Memory usage 


**Return**: Create was successful or failed 

### function destroy

```cpp
void destroy()
```

Destroy the mesh. 

### function bind

```cpp
void bind(
    VkCommandBuffer cmd_buf
) const
```

Bind the mesh. 

**Parameters**: 

  * **cmd_buf** Command buffer 


### function draw

```cpp
void draw(
    VkCommandBuffer cmd_buf
) const
```

Draw the mesh. 

**Parameters**: 

  * **cmd_buf** Command buffer 


### function bind_draw

```cpp
inline void bind_draw(
    VkCommandBuffer cmd_buf
) const
```

Bind and draw the mesh. 

**Parameters**: 

  * **cmd_buf** Command buffer 


### function empty

```cpp
inline bool empty() const
```

Check if mesh is empty. 

**Return**: Mesh is empty or not 

### function set_data

```cpp
inline void set_data(
    mesh_template_data< T > const & value
)
```

Set the mesh data. 

**Parameters**: 

  * **value** Mesh data 


### function get_data

```cpp
inline mesh_template_data< T > & get_data()
```

Get the mesh data. 

**Return**: mesh_data& Mesh data 

### function add_data

```cpp
inline void add_data(
    mesh_template_data< T > const & value
)
```

Add mesh data to existing data. 

**Parameters**: 

  * **value** Mesh data to add 


### function get_vertices

```cpp
inline vertex_list & get_vertices()
```

Get the vertices of the mesh. 

**Return**: [vertex::list](/_doxybook/Classes/structlava_1_1vertex.md#using-list)& List of vertices 

### function get_vertices

```cpp
inline vertex_listconst & get_vertices() const
```

Get the const vertices of the mesh. 

**Return**: [vertex::list](/_doxybook/Classes/structlava_1_1vertex.md#using-list) const& List of vertices 

### function get_vertices_count

```cpp
inline ui32 get_vertices_count() const
```

Get the vertices count of the mesh. 

**Return**: ui32 Number of vertices 

### function get_indices

```cpp
inline index_list & get_indices()
```

Get the indices of the mesh. 

**Return**: index_list& List of indices 

### function get_indices

```cpp
inline index_listconst & get_indices() const
```

Get the const indices of the mesh. 

**Return**: index_list const& List of indices 

### function get_indices_count

```cpp
inline ui32 get_indices_count() const
```

Get the indices count of the mesh. 

**Return**: ui32 Number of indices 

### function reload

```cpp
bool reload()
```

Reload the mesh data. 

**Return**: Reload was successful or failed 

### function get_vertex_buffer

```cpp
inline buffer::ptr get_vertex_buffer()
```

Get the vertex buffer of the mesh. 

**Return**: [buffer::ptr](/_doxybook/Classes/structlava_1_1buffer.md#using-ptr) Shared pointer to buffer 

### function get_index_buffer

```cpp
inline buffer::ptr get_index_buffer()
```

Get the index buffer of the mesh. 

**Return**: [buffer::ptr](/_doxybook/Classes/structlava_1_1buffer.md#using-ptr) Shared pointer to buffer 

-------------------------------

Updated on 2024-03-22 at 21:51:38 +0000