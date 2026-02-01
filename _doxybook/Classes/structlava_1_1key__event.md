---
title: lava::key_event
summary: Key event. 

---

# lava::key_event



Key event. 


`#include <input.hpp>`

## Public Types

|                | Name           |
| -------------- | -------------- |
| using [key_event](/_doxybook/Classes/structlava_1_1key__event.md) const  & | **[ref](/_doxybook/Classes/structlava_1_1key__event.md#using-ref)** <br>Reference to key event.  |
| using std::function< bool([ref](/_doxybook/Classes/structlava_1_1key__event.md#using-ref))> | **[func](/_doxybook/Classes/structlava_1_1key__event.md#using-func)** <br>Key event function.  |
| using std::map< [id](/_doxybook/Classes/structlava_1_1id.md), [func](/_doxybook/Classes/structlava_1_1key__event.md#using-func) > | **[listeners](/_doxybook/Classes/structlava_1_1key__event.md#using-listeners)** <br>List of key event listeners.  |
| using std::vector< [key_event](/_doxybook/Classes/structlava_1_1key__event.md) > | **[list](/_doxybook/Classes/structlava_1_1key__event.md#using-list)** <br>List of key events.  |

## Public Functions

|                | Name           |
| -------------- | -------------- |
| bool | **[pressed](/_doxybook/Classes/structlava_1_1key__event.md#function-pressed)**([key_ref](/_doxybook/Namespaces/namespacelava.md#using-key-ref) k) const<br>Check if key is pressed.  |
| bool | **[released](/_doxybook/Classes/structlava_1_1key__event.md#function-released)**([key_ref](/_doxybook/Namespaces/namespacelava.md#using-key-ref) k) const<br>Check if key is released.  |
| bool | **[repeated](/_doxybook/Classes/structlava_1_1key__event.md#function-repeated)**([key_ref](/_doxybook/Namespaces/namespacelava.md#using-key-ref) k) const<br>Check if key is repeated.  |
| bool | **[active](/_doxybook/Classes/structlava_1_1key__event.md#function-active)**() const<br>Check if key is active.  |
| bool | **[pressed](/_doxybook/Classes/structlava_1_1key__event.md#function-pressed)**([key_ref](/_doxybook/Namespaces/namespacelava.md#using-key-ref) k, [mod_ref](/_doxybook/Namespaces/namespacelava.md#using-mod-ref) m) const<br>Check if key is pressed with mod.  |

## Public Attributes

|                | Name           |
| -------------- | -------------- |
| [id](/_doxybook/Classes/structlava_1_1id.md) | **[sender](/_doxybook/Classes/structlava_1_1key__event.md#variable-sender)** <br>Sender id.  |
| [lava::key](/_doxybook/Namespaces/namespacelava.md#enum-key) | **[key](/_doxybook/Classes/structlava_1_1key__event.md#variable-key)** <br>Input key.  |
| [lava::action](/_doxybook/Namespaces/namespacelava.md#enum-action) | **[action](/_doxybook/Classes/structlava_1_1key__event.md#variable-action)** <br>Input action.  |
| [lava::mod](/_doxybook/Namespaces/namespacelava.md#enum-mod) | **[mod](/_doxybook/Classes/structlava_1_1key__event.md#variable-mod)** <br>Input mod.  |
| [i32](/_doxybook/Namespaces/namespacelava.md#using-i32) | **[scancode](/_doxybook/Classes/structlava_1_1key__event.md#variable-scancode)** <br>Input scan code.  |

## Public Types Documentation

### using ref

```cpp
using lava::key_event::ref =  key_event const&;
```

Reference to key event. 

### using func

```cpp
using lava::key_event::func =  std::function<bool(ref)>;
```

Key event function. 

### using listeners

```cpp
using lava::key_event::listeners =  std::map<id, func>;
```

List of key event listeners. 

### using list

```cpp
using lava::key_event::list =  std::vector<key_event>;
```

List of key events. 

## Public Functions Documentation

### function pressed

```cpp
inline bool pressed(
    key_ref k
) const
```

Check if key is pressed. 

**Parameters**: 

  * **k** Key to check 


**Return**: Key is pressed or not 

### function released

```cpp
inline bool released(
    key_ref k
) const
```

Check if key is released. 

**Parameters**: 

  * **k** Key to check 


**Return**: Key is released or not 

### function repeated

```cpp
inline bool repeated(
    key_ref k
) const
```

Check if key is repeated. 

**Parameters**: 

  * **k** Key to check 


**Return**: Key is repeated or not 

### function active

```cpp
inline bool active() const
```

Check if key is active. 

**Return**: Key is pressed (and repeated) or not active 

### function pressed

```cpp
inline bool pressed(
    key_ref k,
    mod_ref m
) const
```

Check if key is pressed with mod. 

**Parameters**: 

  * **k** Key to check 
  * **m** Mods to check 


**Return**: Key is pressed with mod or not 

## Public Attributes Documentation

### variable sender

```cpp
id sender;
```

Sender id. 

### variable key

```cpp
lava::key key;
```

Input key. 

### variable action

```cpp
lava::action action;
```

Input action. 

### variable mod

```cpp
lava::mod mod;
```

Input mod. 

### variable scancode

```cpp
i32 scancode = 0;
```

Input scan code. 

-------------------------------

Updated on 2026-02-01 at 18:13:39 +0000