---
title: lava::pseudorandom_generator
summary: Pseudorandom generator. 

---

# lava::pseudorandom_generator



Pseudorandom generator. 


`#include <random.hpp>`

## Public Functions

|                | Name           |
| -------------- | -------------- |
| | **[pseudorandom_generator](/_doxybook/Classes/structlava_1_1pseudorandom__generator.md#function-pseudorandom-generator)**([ui32](/_doxybook/Namespaces/namespacelava.md#using-ui32) seed)<br>Construct a new pseudorandom generator.  |
| void | **[set_seed](/_doxybook/Classes/structlava_1_1pseudorandom__generator.md#function-set-seed)**([ui32](/_doxybook/Namespaces/namespacelava.md#using-ui32) value)<br>Set the seed.  |
| [ui32](/_doxybook/Namespaces/namespacelava.md#using-ui32) | **[get](/_doxybook/Classes/structlava_1_1pseudorandom__generator.md#function-get)**()<br>Get next pseudorandom number.  |

## Public Functions Documentation

### function pseudorandom_generator

```cpp
inline explicit pseudorandom_generator(
    ui32 seed
)
```

Construct a new pseudorandom generator. 

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

Get next pseudorandom number. 

**Return**: [ui32](/_doxybook/Namespaces/namespacelava.md#using-ui32) Random number 

-------------------------------

Updated on 2026-02-01 at 18:13:39 +0000