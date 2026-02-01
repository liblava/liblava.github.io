---
title: lava::entity
summary: Entity. 

---

# lava::entity



Entity. 


`#include <id.hpp>`

Inherits from [lava::no_copy_no_move](/_doxybook/Classes/structlava_1_1no__copy__no__move.md), [lava::interface](/_doxybook/Classes/structlava_1_1interface.md)

Inherited by [lava::mesh_template< vertex >](/_doxybook/Classes/structlava_1_1mesh__template.md), [lava::block](/_doxybook/Classes/structlava_1_1block.md), [lava::buffer](/_doxybook/Classes/structlava_1_1buffer.md), [lava::camera](/_doxybook/Classes/structlava_1_1camera.md), [lava::command](/_doxybook/Classes/structlava_1_1command.md), [lava::descriptor](/_doxybook/Classes/structlava_1_1descriptor.md), [lava::descriptor::pool](/_doxybook/Classes/structlava_1_1descriptor_1_1pool.md), [lava::device](/_doxybook/Classes/structlava_1_1device.md), [lava::image](/_doxybook/Classes/structlava_1_1image.md), [lava::layer](/_doxybook/Classes/structlava_1_1layer.md), [lava::mesh_template< T >](/_doxybook/Classes/structlava_1_1mesh__template.md), [lava::physical_device](/_doxybook/Classes/structlava_1_1physical__device.md), [lava::pipeline](/_doxybook/Classes/structlava_1_1pipeline.md), [lava::pipeline_layout](/_doxybook/Classes/structlava_1_1pipeline__layout.md), [lava::render_pass](/_doxybook/Classes/structlava_1_1render__pass.md), [lava::render_target](/_doxybook/Classes/structlava_1_1render__target.md), [lava::renderer](/_doxybook/Classes/structlava_1_1renderer.md), [lava::subpass](/_doxybook/Classes/structlava_1_1subpass.md), [lava::swapchain](/_doxybook/Classes/structlava_1_1swapchain.md), [lava::texture](/_doxybook/Classes/structlava_1_1texture.md), [lava::window](/_doxybook/Classes/structlava_1_1window.md)

## Public Functions

|                | Name           |
| -------------- | -------------- |
| | **[entity](/_doxybook/Classes/structlava_1_1entity.md#function-entity)**()<br>Construct a new entity.  |
| [id::ref](/_doxybook/Classes/structlava_1_1id.md#using-ref) | **[get_id](/_doxybook/Classes/structlava_1_1entity.md#function-get-id)**() const<br>Get the id of entity.  |

## Additional inherited members

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


## Public Functions Documentation

### function entity

```cpp
inline entity()
```

Construct a new entity. 

### function get_id

```cpp
inline id::ref get_id() const
```

Get the id of entity. 

**Return**: [id::ref](/_doxybook/Classes/structlava_1_1id.md#using-ref) Entity id 

-------------------------------

Updated on 2026-02-01 at 18:13:39 +0000