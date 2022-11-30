---
title: liblava/file/json.hpp

---

# liblava/file/json.hpp



## Namespaces

| Name           |
| -------------- |
| **[lava](/_doxybook/Namespaces/namespacelava.md)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| struct | **[lava::configurable](/_doxybook/Classes/structlava_1_1configurable.md)** <br>Configurable interface.  |




## Source code

```cpp

#pragma once

#include <liblava/core/types.hpp>
#include <nlohmann/json.hpp>

namespace lava {

using json = nlohmann::json;

using json_ref = json const&;

struct configurable : interface {
    virtual void set_config(json_ref j) = 0;

    virtual json get_config() const = 0;
};

} // namespace lava
```


-------------------------------

Updated on 2022-11-30 at 01:16:04 +0000
