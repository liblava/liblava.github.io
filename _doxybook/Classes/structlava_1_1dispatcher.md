---
title: lava::dispatcher
summary: Telegram dispatcher. 

---

# lava::dispatcher



Telegram dispatcher. 


`#include <telegram.hpp>`

## Public Types

|                | Name           |
| -------------- | -------------- |
| using std::function< void([telegram::ref](/_doxybook/Classes/structlava_1_1telegram.md#using-ref), [id::ref](/_doxybook/Classes/structlava_1_1id.md#using-ref))> | **[message_func](/_doxybook/Classes/structlava_1_1dispatcher.md#using-message-func)** <br>Message function.  |

## Public Functions

|                | Name           |
| -------------- | -------------- |
| void | **[setup](/_doxybook/Classes/structlava_1_1dispatcher.md#function-setup)**([ui32](/_doxybook/Namespaces/namespacelava.md#using-ui32) thread_count)<br>Set up the dispatcher.  |
| void | **[teardown](/_doxybook/Classes/structlava_1_1dispatcher.md#function-teardown)**()<br>Tear down the dispatcher.  |
| void | **[update](/_doxybook/Classes/structlava_1_1dispatcher.md#function-update)**([ms](/_doxybook/Namespaces/namespacelava.md#using-ms) current)<br>Update the dispatcher.  |
| void | **[add_message](/_doxybook/Classes/structlava_1_1dispatcher.md#function-add-message)**([id::ref](/_doxybook/Classes/structlava_1_1id.md#using-ref) receiver, [id::ref](/_doxybook/Classes/structlava_1_1id.md#using-ref) sender, [id::ref](/_doxybook/Classes/structlava_1_1id.md#using-ref) message, [ms](/_doxybook/Namespaces/namespacelava.md#using-ms) delay ={}, [any](/_doxybook/Namespaces/namespacelava.md#using-any) const & info ={})<br>Add message to dispatcher.  |

## Public Attributes

|                | Name           |
| -------------- | -------------- |
| [message_func](/_doxybook/Classes/structlava_1_1dispatcher.md#using-message-func) | **[on_message](/_doxybook/Classes/structlava_1_1dispatcher.md#variable-on-message)** <br>Called on message handling.  |

## Public Types Documentation

### using message_func

```cpp
using lava::dispatcher::message_func =  std::function<void(telegram::ref, id::ref)>;
```

Message function. 

## Public Functions Documentation

### function setup

```cpp
inline void setup(
    ui32 thread_count
)
```

Set up the dispatcher. 

**Parameters**: 

  * **thread_count** Number of threads 


### function teardown

```cpp
inline void teardown()
```

Tear down the dispatcher. 

### function update

```cpp
inline void update(
    ms current
)
```

Update the dispatcher. 

**Parameters**: 

  * **current** Time in milliseconds 


### function add_message

```cpp
inline void add_message(
    id::ref receiver,
    id::ref sender,
    id::ref message,
    ms delay ={},
    any const & info ={}
)
```

Add message to dispatcher. 

**Parameters**: 

  * **receiver** Receiver id 
  * **sender** Sender id 
  * **message** Telegram message 
  * **delay** Delay time 
  * **info** Telegram information 


## Public Attributes Documentation

### variable on_message

```cpp
message_func on_message;
```

Called on message handling. 

-------------------------------

Updated on 2022-11-30 at 01:16:03 +0000