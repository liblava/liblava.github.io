---
title: lava::no_copy_no_move
summary: No copy and no move object. 

---

# lava::no_copy_no_move



No copy and no move object. 


`#include <types.hpp>`

Inherited by [lava::entity](/_doxybook/Classes/structlava_1_1entity.md), [lava::file](/_doxybook/Classes/structlava_1_1file.md), [lava::file_delete](/_doxybook/Classes/structlava_1_1file__delete.md), [lava::file_system](/_doxybook/Classes/structlava_1_1file__system.md), [lava::frame](/_doxybook/Classes/structlava_1_1frame.md), [lava::instance](/_doxybook/Classes/structlava_1_1instance.md), [lava::memory](/_doxybook/Classes/structlava_1_1memory.md)

## Public Functions

|                | Name           |
| -------------- | -------------- |
| | **[no_copy_no_move](/_doxybook/Classes/structlava_1_1no__copy__no__move.md#function-no-copy-no-move)**() =default<br>Construct a new object.  |
| | **[no_copy_no_move](/_doxybook/Classes/structlava_1_1no__copy__no__move.md#function-no-copy-no-move)**([no_copy_no_move](/_doxybook/Classes/structlava_1_1no__copy__no__move.md) const & ) =delete<br>No copy.  |
| void | **[operator=](/_doxybook/Classes/structlava_1_1no__copy__no__move.md#function-operator=)**([no_copy_no_move](/_doxybook/Classes/structlava_1_1no__copy__no__move.md) const & ) =delete<br>No move.  |

## Public Functions Documentation

### function no_copy_no_move

```cpp
no_copy_no_move() =default
```

Construct a new object. 

### function no_copy_no_move

```cpp
no_copy_no_move(
    no_copy_no_move const & 
) =delete
```

No copy. 

### function operator=

```cpp
void operator=(
    no_copy_no_move const & 
) =delete
```

No move. 

-------------------------------

Updated on 2026-02-01 at 18:13:39 +0000