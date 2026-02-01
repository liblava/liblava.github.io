---
title: liblava/frame/driver.hpp
summary: Stage driver. 

---

# liblava/frame/driver.hpp

Stage driver.  [More...](#detailed-description)

## Namespaces

| Name           |
| -------------- |
| **[lava](/_doxybook/Namespaces/namespacelava.md)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| struct | **[lava::stage](/_doxybook/Classes/structlava_1_1stage.md)** <br>Stage.  |
| struct | **[lava::driver](/_doxybook/Classes/structlava_1_1driver.md)** <br>Stage driver.  |
| struct | **[lava::driver::result](/_doxybook/Classes/structlava_1_1driver_1_1result.md)** <br>Driver result.  |

## Defines

|                | Name           |
| -------------- | -------------- |
|  | **[STAGE_OBJ](/_doxybook/Files/driver_8hpp.md#define-stage-obj)** <br>Stage object.  |
|  | **[STAGE_FUNC](/_doxybook/Files/driver_8hpp.md#define-stage-func)** <br>Stage function.  |
|  | **[STR_](/_doxybook/Files/driver_8hpp.md#define-str-)**(n, m) <br>String concatenation.  |
|  | **[STR](/_doxybook/Files/driver_8hpp.md#define-str)**(n, m) <br>String concatenation.  |
|  | **[LAVA_STAGE](/_doxybook/Files/driver_8hpp.md#define-lava-stage)**(ID, NAME) <br>lava stage macro  |

## Detailed Description

Stage driver. 

**Author**: Lava Block OÜ and contributors 

**Copyright**: Copyright (c) 2018-present, MIT License 



## Macros Documentation

### define STAGE_OBJ

```cpp
#define STAGE_OBJ stage_
```

Stage object. 

### define STAGE_FUNC

```cpp
#define STAGE_FUNC _stage
```

Stage function. 

### define STR_

```cpp
#define STR_(
    n,
    m
)
n##m
```

String concatenation. 

### define STR

```cpp
#define STR(
    n,
    m
)
STR_(n, m)
```

String concatenation. 

### define LAVA_STAGE

```cpp
#define LAVA_STAGE(
    ID,
    NAME
)
lava::i32STR(STAGE_FUNC, ID)(argh::parser argh); \
    lava::stageSTR(STAGE_OBJ, ID)(ID, NAME, ::STR(STAGE_FUNC, ID)); \
    lava::i32STR(STAGE_FUNC, ID)(argh::parser argh)
```

lava stage macro 

## Source code

```cpp


#pragma once

#include "liblava/frame/argh.hpp"

namespace lava {

struct stage {
    using map = std::map<index, stage*>;

    using func = std::function<i32(argh::parser)>;

    explicit stage(ui32 id,
                   string_ref name,
                   func func);

    index id = 0;

    string name;

    func on_func;
};

struct driver {
    enum error {
        stages_empty = -1,
        stage_not_found = -2,
        undef_run = -3,
    };

    struct result {
        i32 driver = 0;

        i32 selected = 0;
    };

    static driver& instance() {
        static driver driver;
        return driver;
    }

    void add_stage(stage* stage) {
        assert(!m_stages.count(stage->id) && "stage id already defined.");
        m_stages.emplace(stage->id, stage);
    }

    stage::map const& get_stages() const {
        return m_stages;
    }

    i32 run(argh::parser cmd_line = {});

    using run_func = std::function<result(argh::parser)>;

    run_func on_run;

private:
    driver() = default;

    stage::map m_stages;
};

} // namespace lava

#define STAGE_OBJ stage_

#define STAGE_FUNC _stage

#define STR_(n, m) n##m

#define STR(n, m) STR_(n, m)

#define LAVA_STAGE(ID, NAME) \
    lava::i32 STR(STAGE_FUNC, ID)(argh::parser argh); \
    lava::stage STR(STAGE_OBJ, ID)(ID, NAME, ::STR(STAGE_FUNC, ID)); \
    lava::i32 STR(STAGE_FUNC, ID)(argh::parser argh)
```


-------------------------------

Updated on 2026-02-01 at 18:13:39 +0000
