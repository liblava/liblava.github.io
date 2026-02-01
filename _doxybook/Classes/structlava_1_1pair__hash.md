---
title: lava::pair_hash
summary: Pair hash. 

---

# lava::pair_hash



Pair hash. 


`#include <types.hpp>`

## Public Functions

|                | Name           |
| -------------- | -------------- |
| template <class T1 ,class T2 \> <br>[size_t](/_doxybook/Namespaces/namespacelava.md#using-size-t) | **[operator()](/_doxybook/Classes/structlava_1_1pair__hash.md#function-operator())**(std::pair< T1, T2 > const & p) const<br>Hash operator.  |

## Public Functions Documentation

### function operator()

```cpp
template <class T1 ,
class T2 >
inline size_t operator()(
    std::pair< T1, T2 > const & p
) const
```

Hash operator. 

**Parameters**: 

  * **p** Hash pair 


**Template Parameters**: 

  * **T1** Type of first 
  * **T2** Type of second 


**Return**: [size_t](/_doxybook/Namespaces/namespacelava.md#using-size-t) Hash value 

-------------------------------

Updated on 2026-02-01 at 18:13:39 +0000