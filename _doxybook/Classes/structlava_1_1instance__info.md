---
title: lava::instance_info
summary: Vulkan instance information. 

---

# lava::instance_info



Vulkan instance information. 


`#include <instance.hpp>`

## Public Types

|                | Name           |
| -------------- | -------------- |
| using [instance_info](/_doxybook/Classes/structlava_1_1instance__info.md) const  & | **[ref](/_doxybook/Classes/structlava_1_1instance__info.md#using-ref)** <br>Reference to a instance.  |

## Public Attributes

|                | Name           |
| -------------- | -------------- |
| [name](/_doxybook/Namespaces/namespacelava.md#using-name) | **[app_name](/_doxybook/Classes/structlava_1_1instance__info.md#variable-app-name)** <br>Name of application.  |
| [name](/_doxybook/Namespaces/namespacelava.md#using-name) | **[engine_name](/_doxybook/Classes/structlava_1_1instance__info.md#variable-engine-name)** <br>Name of engine.  |
| [sem_version](/_doxybook/Namespaces/namespacelava.md#using-sem-version) | **[app_version](/_doxybook/Classes/structlava_1_1instance__info.md#variable-app-version)** <br>Version of application.  |
| [sem_version](/_doxybook/Namespaces/namespacelava.md#using-sem-version) | **[engine_version](/_doxybook/Classes/structlava_1_1instance__info.md#variable-engine-version)** <br>Version of engine.  |
| [api_version](/_doxybook/Namespaces/namespacelava.md#enum-api-version) | **[req_api_version](/_doxybook/Classes/structlava_1_1instance__info.md#variable-req-api-version)** <br>Required Vulkan API version.  |

## Public Types Documentation

### using ref

```cpp
using lava::instance_info::ref =  instance_info const&;
```

Reference to a instance. 

## Public Attributes Documentation

### variable app_name

```cpp
name app_name = _lava_;
```

Name of application. 

### variable engine_name

```cpp
name engine_name = _liblava_;
```

Name of engine. 

### variable app_version

```cpp
sem_version app_version;
```

Version of application. 

### variable engine_version

```cpp
sem_version engine_version;
```

Version of engine. 

### variable req_api_version

```cpp
api_version req_api_version = api_version::v1_0;
```

Required Vulkan API version. 

-------------------------------

Updated on 2026-02-01 at 18:13:39 +0000