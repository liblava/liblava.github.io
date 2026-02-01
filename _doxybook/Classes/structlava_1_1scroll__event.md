---
title: lava::scroll_event
summary: Scroll event. 

---

# lava::scroll_event



Scroll event. 


`#include <input.hpp>`

## Public Types

|                | Name           |
| -------------- | -------------- |
| using [scroll_event](/_doxybook/Classes/structlava_1_1scroll__event.md) const  & | **[ref](/_doxybook/Classes/structlava_1_1scroll__event.md#using-ref)** <br>Reference to scroll event.  |
| using std::function< bool([ref](/_doxybook/Classes/structlava_1_1scroll__event.md#using-ref))> | **[func](/_doxybook/Classes/structlava_1_1scroll__event.md#using-func)** <br>Scroll event function.  |
| using std::map< [id](/_doxybook/Classes/structlava_1_1id.md), [func](/_doxybook/Classes/structlava_1_1scroll__event.md#using-func) > | **[listeners](/_doxybook/Classes/structlava_1_1scroll__event.md#using-listeners)** <br>List of scroll event listeners.  |
| using std::vector< [scroll_event](/_doxybook/Classes/structlava_1_1scroll__event.md) > | **[list](/_doxybook/Classes/structlava_1_1scroll__event.md#using-list)** <br>List of scroll events.  |

## Public Attributes

|                | Name           |
| -------------- | -------------- |
| [id](/_doxybook/Classes/structlava_1_1id.md) | **[sender](/_doxybook/Classes/structlava_1_1scroll__event.md#variable-sender)** <br>Sender id.  |
| [scroll_offset](/_doxybook/Classes/structlava_1_1scroll__offset.md) | **[offset](/_doxybook/Classes/structlava_1_1scroll__event.md#variable-offset)** <br>Input scroll offset.  |

## Public Types Documentation

### using ref

```cpp
using lava::scroll_event::ref =  scroll_event const&;
```

Reference to scroll event. 

### using func

```cpp
using lava::scroll_event::func =  std::function<bool(ref)>;
```

Scroll event function. 

### using listeners

```cpp
using lava::scroll_event::listeners =  std::map<id, func>;
```

List of scroll event listeners. 

### using list

```cpp
using lava::scroll_event::list =  std::vector<scroll_event>;
```

List of scroll events. 

## Public Attributes Documentation

### variable sender

```cpp
id sender;
```

Sender id. 

### variable offset

```cpp
scroll_offset offset;
```

Input scroll offset. 

-------------------------------

Updated on 2026-02-01 at 18:13:39 +0000