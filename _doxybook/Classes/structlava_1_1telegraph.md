---
title: lava::telegraph
summary: Telegraph station. 

---

# lava::telegraph



Telegraph station. 


`#include <telegram.hpp>`

Inherits from [lava::interface](/_doxybook/Classes/structlava_1_1interface.md)

Inherited by [lava::message_dispatcher](/_doxybook/Classes/structlava_1_1message__dispatcher.md)

## Public Functions

|                | Name           |
| -------------- | -------------- |
| virtual void | **[send_message](/_doxybook/Classes/structlava_1_1telegraph.md#function-send-message)**([id::ref](/_doxybook/Classes/structlava_1_1id.md#using-ref) receiver, [id::ref](/_doxybook/Classes/structlava_1_1id.md#using-ref) sender, [index](/_doxybook/Namespaces/namespacelava.md#using-index) message, [ms](/_doxybook/Namespaces/namespacelava.md#using-ms) delay ={}, [any](/_doxybook/Namespaces/namespacelava.md#using-any) const & info ={}) =0<br>Send message to dispatcher.  |

## Additional inherited members

**Public Functions inherited from [lava::interface](/_doxybook/Classes/structlava_1_1interface.md)**

|                | Name           |
| -------------- | -------------- |
| virtual | **[~interface](/_doxybook/Classes/structlava_1_1interface.md#function-~interface)**() =default<br>Destroy the interface.  |


## Public Functions Documentation

### function send_message

```cpp
virtual void send_message(
    id::ref receiver,
    id::ref sender,
    index message,
    ms delay ={},
    any const & info ={}
) =0
```

Send message to dispatcher. 

**Parameters**: 

  * **receiver** Receiver id 
  * **sender** Sender id 
  * **message** Message id 
  * **delay** Delay time 
  * **info** Telegram information 


**Reimplemented by**: [lava::message_dispatcher::send_message](/_doxybook/Classes/structlava_1_1message__dispatcher.md#function-send-message)


-------------------------------

Updated on 2026-02-01 at 18:13:39 +0000