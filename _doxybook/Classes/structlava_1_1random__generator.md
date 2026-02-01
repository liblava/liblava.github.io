---
title: lava::random_generator
summary: Random generator. 

---

# lava::random_generator



Random generator. 


`#include <random.hpp>`

## Public Functions

|                | Name           |
| -------------- | -------------- |
| | **[random_generator](/_doxybook/Classes/structlava_1_1random__generator.md#function-random-generator)**()<br>Construct a new random generator.  |
| [i32](/_doxybook/Namespaces/namespacelava.md#using-i32) | **[get](/_doxybook/Classes/structlava_1_1random__generator.md#function-get)**([i32](/_doxybook/Namespaces/namespacelava.md#using-i32) low, [i32](/_doxybook/Namespaces/namespacelava.md#using-i32) high)<br>Get next random number.  |
| template <typename T  =real\> <br>T | **[get](/_doxybook/Classes/structlava_1_1random__generator.md#function-get)**(T low, T high)<br>Get next real random number.  |

## Public Functions Documentation

### function random_generator

```cpp
inline random_generator()
```

Construct a new random generator. 

### function get

```cpp
inline i32 get(
    i32 low,
    i32 high
)
```

Get next random number. 

**Parameters**: 

  * **low** Lowest number 
  * **high** Highest number 


**Return**: [i32](/_doxybook/Namespaces/namespacelava.md#using-i32) Random number 

### function get

```cpp
template <typename T  =real>
inline T get(
    T low,
    T high
)
```

Get next real random number. 

**Parameters**: 

  * **low** Lowest number 
  * **high** Highest number 


**Template Parameters**: 

  * **T** Type of number 


**Return**: T Random number 

-------------------------------

Updated on 2026-02-01 at 18:13:39 +0000