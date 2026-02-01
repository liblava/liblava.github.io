---
title: lava::telegram
summary: Telegram. 

---

# lava::telegram



Telegram. 


`#include <telegram.hpp>`

## Public Types

|                | Name           |
| -------------- | -------------- |
| using [telegram](/_doxybook/Classes/structlava_1_1telegram.md) const  & | **[ref](/_doxybook/Classes/structlava_1_1telegram.md#using-ref)** <br>Reference to telegram.  |
| using std::multiset< [telegram](/_doxybook/Classes/structlava_1_1telegram.md) > | **[set](/_doxybook/Classes/structlava_1_1telegram.md#using-set)** <br>Set of telegrams.  |

## Public Functions

|                | Name           |
| -------------- | -------------- |
| | **[telegram](/_doxybook/Classes/structlava_1_1telegram.md#function-telegram)**([id::ref](/_doxybook/Classes/structlava_1_1id.md#using-ref) sender, [id::ref](/_doxybook/Classes/structlava_1_1id.md#using-ref) receiver, [index](/_doxybook/Namespaces/namespacelava.md#using-index) msg, [ms](/_doxybook/Namespaces/namespacelava.md#using-ms) dispatch_time ={}, [any](/_doxybook/Namespaces/namespacelava.md#using-any) info ={})<br>Construct a new telegram.  |
| bool | **[operator==](/_doxybook/Classes/structlava_1_1telegram.md#function-operator==)**([ref](/_doxybook/Classes/structlava_1_1telegram.md#using-ref) rhs) const<br>Equal operator.  |
| bool | **[operator<](/_doxybook/Classes/structlava_1_1telegram.md#function-operator<)**([ref](/_doxybook/Classes/structlava_1_1telegram.md#using-ref) rhs) const<br>Time order operator.  |

## Public Attributes

|                | Name           |
| -------------- | -------------- |
| [id](/_doxybook/Classes/structlava_1_1id.md) | **[sender](/_doxybook/Classes/structlava_1_1telegram.md#variable-sender)** <br>Sender id.  |
| [id](/_doxybook/Classes/structlava_1_1id.md) | **[receiver](/_doxybook/Classes/structlava_1_1telegram.md#variable-receiver)** <br>Receiver id.  |
| [index](/_doxybook/Namespaces/namespacelava.md#using-index) | **[msg_id](/_doxybook/Classes/structlava_1_1telegram.md#variable-msg-id)** <br>Message id.  |
| [ms](/_doxybook/Namespaces/namespacelava.md#using-ms) | **[dispatch_time](/_doxybook/Classes/structlava_1_1telegram.md#variable-dispatch-time)** <br>Dispatch time.  |
| [any](/_doxybook/Namespaces/namespacelava.md#using-any) | **[info](/_doxybook/Classes/structlava_1_1telegram.md#variable-info)** <br>Telegram information.  |

## Public Types Documentation

### using ref

```cpp
using lava::telegram::ref =  telegram const&;
```

Reference to telegram. 

### using set

```cpp
using lava::telegram::set =  std::multiset<telegram>;
```

Set of telegrams. 

## Public Functions Documentation

### function telegram

```cpp
inline explicit telegram(
    id::ref sender,
    id::ref receiver,
    index msg,
    ms dispatch_time ={},
    any info ={}
)
```

Construct a new telegram. 

**Parameters**: 

  * **sender** Sender id 
  * **receiver** Receiver id 
  * **msg** Message id 
  * **dispatch_time** Dispatch time 
  * **info** Telegram information 


### function operator==

```cpp
inline bool operator==(
    ref rhs
) const
```

Equal operator. 

**Parameters**: 

  * **rhs** Another telegram 


**Return**: Telegram is equal or not 

### function operator<

```cpp
inline bool operator<(
    ref rhs
) const
```

Time order operator. 

**Parameters**: 

  * **rhs** Another telegram 


**Return**: Telegram is earlier or later 

## Public Attributes Documentation

### variable sender

```cpp
id sender;
```

Sender id. 

### variable receiver

```cpp
id receiver;
```

Receiver id. 

### variable msg_id

```cpp
index msg_id = no_index;
```

Message id. 

### variable dispatch_time

```cpp
ms dispatch_time;
```

Dispatch time. 

### variable info

```cpp
any info;
```

Telegram information. 

-------------------------------

Updated on 2026-02-01 at 18:13:39 +0000