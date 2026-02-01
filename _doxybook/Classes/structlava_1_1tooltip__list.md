---
title: lava::tooltip_list
summary: Tooltip list. 

---

# lava::tooltip_list



Tooltip list. 


`#include <input.hpp>`

## Public Functions

|                | Name           |
| -------------- | -------------- |
| void | **[add](/_doxybook/Classes/structlava_1_1tooltip__list.md#function-add)**([string_ref](/_doxybook/Namespaces/namespacelava.md#using-string-ref) name, [key](/_doxybook/Namespaces/namespacelava.md#enum-key) key, [mod](/_doxybook/Namespaces/namespacelava.md#enum-mod) mod =mod::none)<br>Add a tooltip.  |
| void | **[clear](/_doxybook/Classes/structlava_1_1tooltip__list.md#function-clear)**()<br>Clear tooltips.  |
| [tooltip::list](/_doxybook/Classes/structlava_1_1tooltip.md#using-list) const & | **[get_list](/_doxybook/Classes/structlava_1_1tooltip__list.md#function-get-list)**() const<br>Get tooltips.  |
| void | **[set](/_doxybook/Classes/structlava_1_1tooltip__list.md#function-set)**([tooltip::list](/_doxybook/Classes/structlava_1_1tooltip.md#using-list) const & list)<br>Set a new tooltip list.  |
| [string](/_doxybook/Namespaces/namespacelava.md#using-string) | **[format_string](/_doxybook/Classes/structlava_1_1tooltip__list.md#function-format-string)**() const<br>Convert tooltips to string.  |

## Public Functions Documentation

### function add

```cpp
inline void add(
    string_ref name,
    key key,
    mod mod =mod::none
)
```

Add a tooltip. 

**Parameters**: 

  * **name** Name of tooltip 
  * **key** Input key 
  * **mod** Input mod (default: none) 


### function clear

```cpp
inline void clear()
```

Clear tooltips. 

### function get_list

```cpp
inline tooltip::list const & get_list() const
```

Get tooltips. 

**Return**: [tooltip::list](/_doxybook/Classes/structlava_1_1tooltip.md#using-list) List of tooltips 

### function set

```cpp
inline void set(
    tooltip::list const & list
)
```

Set a new tooltip list. 

**Parameters**: 

  * **list** List of tooltips 


### function format_string

```cpp
string format_string() const
```

Convert tooltips to string. 

**Return**: string String representation 

-------------------------------

Updated on 2026-02-01 at 18:13:39 +0000