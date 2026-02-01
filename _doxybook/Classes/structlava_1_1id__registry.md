---
title: lava::id_registry
summary: Id registry. 

---

# lava::id_registry



Id registry.  [More...](#detailed-description)


`#include <id.hpp>`

## Public Types

|                | Name           |
| -------------- | -------------- |
| using std::shared_ptr< T > | **[s_ptr](/_doxybook/Classes/structlava_1_1id__registry.md#using-s-ptr)** <br>Shared pointer to id registry.  |
| using std::map< [id](/_doxybook/Classes/structlava_1_1id.md), [s_ptr](/_doxybook/Classes/structlava_1_1id__registry.md#using-s-ptr) > | **[s_map](/_doxybook/Classes/structlava_1_1id__registry.md#using-s-map)** <br>Map of id registries.  |
| using std::map< [id](/_doxybook/Classes/structlava_1_1id.md), Meta > | **[meta_map](/_doxybook/Classes/structlava_1_1id__registry.md#using-meta-map)** <br>Map of ids with meta.  |

## Public Functions

|                | Name           |
| -------------- | -------------- |
| [id](/_doxybook/Classes/structlava_1_1id.md) | **[create](/_doxybook/Classes/structlava_1_1id__registry.md#function-create)**(Meta info ={})<br>Create a new object in registry.  |
| void | **[add](/_doxybook/Classes/structlava_1_1id__registry.md#function-add)**([s_ptr](/_doxybook/Classes/structlava_1_1id__registry.md#using-s-ptr) object, Meta info ={})<br>Add a object with meta to registry.  |
| bool | **[exists](/_doxybook/Classes/structlava_1_1id__registry.md#function-exists)**([id::ref](/_doxybook/Classes/structlava_1_1id.md#using-ref) object_id) const<br>Check if object exists in registry.  |
| [s_ptr](/_doxybook/Classes/structlava_1_1id__registry.md#using-s-ptr) | **[get](/_doxybook/Classes/structlava_1_1id__registry.md#function-get)**([id::ref](/_doxybook/Classes/structlava_1_1id.md#using-ref) object_id) const<br>Get the object by id.  |
| Meta const & | **[get_meta](/_doxybook/Classes/structlava_1_1id__registry.md#function-get-meta)**([id::ref](/_doxybook/Classes/structlava_1_1id.md#using-ref) object_id) const<br>Get the meta by id.  |
| [s_map](/_doxybook/Classes/structlava_1_1id__registry.md#using-s-map) const & | **[get_all](/_doxybook/Classes/structlava_1_1id__registry.md#function-get-all)**() const<br>Get all objects.  |
| [meta_map](/_doxybook/Classes/structlava_1_1id__registry.md#using-meta-map) const & | **[get_all_meta](/_doxybook/Classes/structlava_1_1id__registry.md#function-get-all-meta)**() const<br>Get all meta objects.  |
| bool | **[update](/_doxybook/Classes/structlava_1_1id__registry.md#function-update)**([id::ref](/_doxybook/Classes/structlava_1_1id.md#using-ref) object_id, Meta const & meta)<br>Update meta of object.  |
| void | **[remove](/_doxybook/Classes/structlava_1_1id__registry.md#function-remove)**([id::ref](/_doxybook/Classes/structlava_1_1id.md#using-ref) object_id)<br>Remove object from registry.  |
| void | **[clear](/_doxybook/Classes/structlava_1_1id__registry.md#function-clear)**()<br>Clear the registry.  |

## Detailed Description

```cpp
template <typename T ,
typename Meta >
struct lava::id_registry;
```

Id registry. 

**Template Parameters**: 

  * **T** Type of objects hold in registry 
  * **Meta** Meta type for object 

## Public Types Documentation

### using s_ptr

```cpp
using lava::id_registry< T, Meta >::s_ptr =  std::shared_ptr<T>;
```

Shared pointer to id registry. 

### using s_map

```cpp
using lava::id_registry< T, Meta >::s_map =  std::map<id, s_ptr>;
```

Map of id registries. 

### using meta_map

```cpp
using lava::id_registry< T, Meta >::meta_map =  std::map<id, Meta>;
```

Map of ids with meta. 

## Public Functions Documentation

### function create

```cpp
inline id create(
    Meta info ={}
)
```

Create a new object in registry. 

**Parameters**: 

  * **info** Meta information 


**Return**: id Object id 

### function add

```cpp
inline void add(
    s_ptr object,
    Meta info ={}
)
```

Add a object with meta to registry. 

**Parameters**: 

  * **object** Object to add 
  * **info** Meta of object 


### function exists

```cpp
inline bool exists(
    id::ref object_id
) const
```

Check if object exists in registry. 

**Parameters**: 

  * **object_id** Object to check 


**Return**: Object exists or not 

### function get

```cpp
inline s_ptr get(
    id::ref object_id
) const
```

Get the object by id. 

**Parameters**: 

  * **object_id** Object id 


**Return**: [s_ptr](/_doxybook/Classes/structlava_1_1id__registry.md#using-s-ptr) Shared pointer to object 

### function get_meta

```cpp
inline Meta const & get_meta(
    id::ref object_id
) const
```

Get the meta by id. 

**Parameters**: 

  * **object_id** Object id 


**Return**: Meta Meta object 

### function get_all

```cpp
inline s_map const & get_all() const
```

Get all objects. 

**Return**: [s_map](/_doxybook/Classes/structlava_1_1id__registry.md#using-s-map) const& Map with objects 

### function get_all_meta

```cpp
inline meta_map const & get_all_meta() const
```

Get all meta objects. 

**Return**: [meta_map](/_doxybook/Classes/structlava_1_1id__registry.md#using-meta-map) const& Map with metas 

### function update

```cpp
inline bool update(
    id::ref object_id,
    Meta const & meta
)
```

Update meta of object. 

**Parameters**: 

  * **object_id** Object id 
  * **meta** Meta to update 


**Return**: Meta updated or not 

### function remove

```cpp
inline void remove(
    id::ref object_id
)
```

Remove object from registry. 

**Parameters**: 

  * **object_id** Object id 


### function clear

```cpp
inline void clear()
```

Clear the registry. 

-------------------------------

Updated on 2026-02-01 at 18:13:39 +0000