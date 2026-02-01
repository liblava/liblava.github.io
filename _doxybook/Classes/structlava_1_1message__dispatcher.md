---
title: lava::message_dispatcher
summary: Message dispatcher. 

---

# lava::message_dispatcher



Message dispatcher. 


`#include <telegram.hpp>`

Inherits from [lava::telegraph](/_doxybook/Classes/structlava_1_1telegraph.md), [lava::interface](/_doxybook/Classes/structlava_1_1interface.md)

## Public Types

|                | Name           |
| -------------- | -------------- |
| using std::function< void([telegram::ref](/_doxybook/Classes/structlava_1_1telegram.md#using-ref), [id::ref](/_doxybook/Classes/structlava_1_1id.md#using-ref))> | **[message_func](/_doxybook/Classes/structlava_1_1message__dispatcher.md#using-message-func)** <br>Message function.  |

## Public Functions

|                | Name           |
| -------------- | -------------- |
| | **[~message_dispatcher](/_doxybook/Classes/structlava_1_1message__dispatcher.md#function-~message-dispatcher)**()<br>Destroy the dispatcher.  |
| void | **[setup](/_doxybook/Classes/structlava_1_1message__dispatcher.md#function-setup)**([ui32](/_doxybook/Namespaces/namespacelava.md#using-ui32) thread_count)<br>Set up the dispatcher.  |
| void | **[teardown](/_doxybook/Classes/structlava_1_1message__dispatcher.md#function-teardown)**()<br>Tear down the dispatcher.  |
| void | **[update](/_doxybook/Classes/structlava_1_1message__dispatcher.md#function-update)**([ms](/_doxybook/Namespaces/namespacelava.md#using-ms) current)<br>Update the dispatcher.  |
| virtual void | **[send_message](/_doxybook/Classes/structlava_1_1message__dispatcher.md#function-send-message)**([id::ref](/_doxybook/Classes/structlava_1_1id.md#using-ref) receiver, [id::ref](/_doxybook/Classes/structlava_1_1id.md#using-ref) sender, [index](/_doxybook/Namespaces/namespacelava.md#using-index) message, [ms](/_doxybook/Namespaces/namespacelava.md#using-ms) delay ={}, [any](/_doxybook/Namespaces/namespacelava.md#using-any) const & info ={}) override |
| bool | **[add_dispatch](/_doxybook/Classes/structlava_1_1message__dispatcher.md#function-add-dispatch)**([id::ref](/_doxybook/Classes/structlava_1_1id.md#using-ref) target, [message_func](/_doxybook/Classes/structlava_1_1message__dispatcher.md#using-message-func) func)<br>Add dispatch.  |
| bool | **[remove_dispatch](/_doxybook/Classes/structlava_1_1message__dispatcher.md#function-remove-dispatch)**([id::ref](/_doxybook/Classes/structlava_1_1id.md#using-ref) target)<br>Remove dispatch.  |
| bool | **[has_dispatch](/_doxybook/Classes/structlava_1_1message__dispatcher.md#function-has-dispatch)**([id::ref](/_doxybook/Classes/structlava_1_1id.md#using-ref) target) const<br>Check if dispatch is registered.  |

## Additional inherited members

**Public Functions inherited from [lava::interface](/_doxybook/Classes/structlava_1_1interface.md)**

|                | Name           |
| -------------- | -------------- |
| virtual | **[~interface](/_doxybook/Classes/structlava_1_1interface.md#function-~interface)**() =default<br>Destroy the interface.  |


## Public Types Documentation

### using message_func

```cpp
using lava::message_dispatcher::message_func =  std::function<void(telegram::ref, id::ref)>;
```

Message function. 

## Public Functions Documentation

### function ~message_dispatcher

```cpp
inline ~message_dispatcher()
```

Destroy the dispatcher. 

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


### function send_message

```cpp
inline virtual void send_message(
    id::ref receiver,
    id::ref sender,
    index message,
    ms delay ={},
    any const & info ={}
) override
```


**See**: [telegraph::send_message](/_doxybook/Classes/structlava_1_1telegraph.md#function-send-message)

**Reimplements**: [lava::telegraph::send_message](/_doxybook/Classes/structlava_1_1telegraph.md#function-send-message)


### function add_dispatch

```cpp
inline bool add_dispatch(
    id::ref target,
    message_func func
)
```

Add dispatch. 

**Parameters**: 

  * **target** Sender id 
  * **func** Dispatch function 


**Return**: Dispatch added or not 

### function remove_dispatch

```cpp
inline bool remove_dispatch(
    id::ref target
)
```

Remove dispatch. 

**Parameters**: 

  * **target** Sender id 


**Return**: Dispatch removed or not 

### function has_dispatch

```cpp
inline bool has_dispatch(
    id::ref target
) const
```

Check if dispatch is registered. 

**Parameters**: 

  * **target** Sender id 


**Return**: Dispatch exists or not 

-------------------------------

Updated on 2026-02-01 at 18:13:39 +0000