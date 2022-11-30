---
title: lava::pseudo_random_generator
summary: Pseudo random generator. 

---

# lava::pseudo_random_generator



Pseudo random generator. 


`#include <random.hpp>`

## Public Functions

|                | Name           |
| -------------- | -------------- |
| | **[pseudo_random_generator](/_doxybook/Classes/structlava_1_1pseudo__random__generator.md#function-pseudo-random-generator)**([ui32](/_doxybook/Namespaces/namespacelava.md#using-ui32) seed)<br>Construct a new pseudo random generator.  |
| void | **[set_seed](/_doxybook/Classes/structlava_1_1pseudo__random__generator.md#function-set-seed)**([ui32](/_doxybook/Namespaces/namespacelava.md#using-ui32) value)<br>Set the seed.  |
| [ui32](/_doxybook/Namespaces/namespacelava.md#using-ui32) | **[get](/_doxybook/Classes/structlava_1_1pseudo__random__generator.md#function-get)**()<br>Get next pseudo random number.  |

## Public Functions Documentation

### function pseudo_random_generator

```cpp
inline explicit pseudo_random_generator(
    ui32 seed
)
```

Construct a new pseudo random generator. 

**Parameters**: 

  * **seed** Seed for generator 


### function set_seed

```cpp
inline void set_seed(
    ui32 value
)
```

Set the seed. 

**Parameters**: 

  * **value** Generator seed 


### function get

```cpp
inline ui32 get()
```

Get next pseudo random number. 

**Return**: ui32 Random number 

-------------------------------

Updated on 2022-11-30 at 01:16:04 +0000