---
title: lava::frame
summary: Framework. 

---

# lava::frame



Framework. 


`#include <frame.hpp>`

Inherits from [lava::interface](/_doxybook/Classes/structlava_1_1interface.md), [lava::no_copy_no_move](/_doxybook/Classes/structlava_1_1no__copy__no__move.md)

Inherited by [lava::app](/_doxybook/Classes/structlava_1_1app.md)

## Public Types

|                | Name           |
| -------------- | -------------- |
| using std::shared_ptr< [frame](/_doxybook/Classes/structlava_1_1frame.md) > | **[s_ptr](/_doxybook/Classes/structlava_1_1frame.md#using-s-ptr)** <br>Shared pointer to framework.  |
| using [i32](/_doxybook/Namespaces/namespacelava.md#using-i32) | **[result](/_doxybook/Classes/structlava_1_1frame.md#using-result)** <br>Framework result.  |
| using std::function< bool([id::ref](/_doxybook/Classes/structlava_1_1id.md#using-ref))> | **[run_func](/_doxybook/Classes/structlava_1_1frame.md#using-run-func)** <br>Run function.  |
| using [run_func](/_doxybook/Classes/structlava_1_1frame.md#using-run-func) const  & | **[run_func_ref](/_doxybook/Classes/structlava_1_1frame.md#using-run-func-ref)** <br>Reference to run function.  |
| using std::function< void()> | **[run_end_func](/_doxybook/Classes/structlava_1_1frame.md#using-run-end-func)** <br>Run end function.  |
| using [run_end_func](/_doxybook/Classes/structlava_1_1frame.md#using-run-end-func) const  & | **[run_end_func_ref](/_doxybook/Classes/structlava_1_1frame.md#using-run-end-func-ref)** <br>Reference to run end function.  |
| using std::function< bool()> | **[run_once_func](/_doxybook/Classes/structlava_1_1frame.md#using-run-once-func)** <br>Run once function.  |
| using [run_once_func](/_doxybook/Classes/structlava_1_1frame.md#using-run-once-func) const  & | **[run_once_func_ref](/_doxybook/Classes/structlava_1_1frame.md#using-run-once-func-ref)** <br>Reference to run once function.  |

## Public Functions

|                | Name           |
| -------------- | -------------- |
| | **[frame](/_doxybook/Classes/structlava_1_1frame.md#function-frame)**(argh::parser cmd_line)<br>Construct a new framework.  |
| | **[frame](/_doxybook/Classes/structlava_1_1frame.md#function-frame)**([frame_env](/_doxybook/Classes/structlava_1_1frame__env.md) env)<br>Construct a new framework.  |
| | **[~frame](/_doxybook/Classes/structlava_1_1frame.md#function-~frame)**() override<br>Destroy the framework.  |
| bool | **[ready](/_doxybook/Classes/structlava_1_1frame.md#function-ready)**() const<br>Check if framework is ready.  |
| [result](/_doxybook/Classes/structlava_1_1frame.md#using-result) | **[run](/_doxybook/Classes/structlava_1_1frame.md#function-run)**()<br>Run the framework.  |
| bool | **[shut_down](/_doxybook/Classes/structlava_1_1frame.md#function-shut-down)**()<br>Shut down the framework.  |
| [id](/_doxybook/Classes/structlava_1_1id.md) | **[add_run](/_doxybook/Classes/structlava_1_1frame.md#function-add-run)**([run_func_ref](/_doxybook/Classes/structlava_1_1frame.md#using-run-func-ref) func)<br>Add run to framework.  |
| [id](/_doxybook/Classes/structlava_1_1id.md) | **[add_run_end](/_doxybook/Classes/structlava_1_1frame.md#function-add-run-end)**([run_end_func_ref](/_doxybook/Classes/structlava_1_1frame.md#using-run-end-func-ref) func)<br>Add run end to framework.  |
| void | **[add_run_once](/_doxybook/Classes/structlava_1_1frame.md#function-add-run-once)**([run_once_func_ref](/_doxybook/Classes/structlava_1_1frame.md#using-run-once-func-ref) func)<br>Add run once to framework.  |
| bool | **[remove](/_doxybook/Classes/structlava_1_1frame.md#function-remove)**([id::ref](/_doxybook/Classes/structlava_1_1id.md#using-ref) func_id)<br>Remove a function from framework.  |
| [ms](/_doxybook/Namespaces/namespacelava.md#using-ms) | **[get_running_time](/_doxybook/Classes/structlava_1_1frame.md#function-get-running-time)**() const<br>Get the running time.  |
| [r64](/_doxybook/Namespaces/namespacelava.md#using-r64) | **[get_running_time_sec](/_doxybook/Classes/structlava_1_1frame.md#function-get-running-time-sec)**() const<br>Get the running time in seconds.  |
| [cmd_line](/_doxybook/Namespaces/namespacelava.md#using-cmd-line) | **[get_cmd_line](/_doxybook/Classes/structlava_1_1frame.md#function-get-cmd-line)**() const<br>Get the command line arguments.  |
| [frame_env::ref](/_doxybook/Classes/structlava_1_1frame__env.md#using-ref) | **[get_env](/_doxybook/Classes/structlava_1_1frame.md#function-get-env)**() const<br>Get the framework environment.  |
| [name](/_doxybook/Namespaces/namespacelava.md#using-name) | **[get_name](/_doxybook/Classes/structlava_1_1frame.md#function-get-name)**() const<br>Get the name of application.  |
| bool | **[waiting_for_events](/_doxybook/Classes/structlava_1_1frame.md#function-waiting-for-events)**() const<br>Check if framework is waiting for events.  |
| void | **[set_wait_for_events](/_doxybook/Classes/structlava_1_1frame.md#function-set-wait-for-events)**(bool value =true)<br>Set wait for events in framework.  |

## Public Attributes

|                | Name           |
| -------------- | -------------- |
| [lava::run_time](/_doxybook/Classes/structlava_1_1run__time.md) | **[run_time](/_doxybook/Classes/structlava_1_1frame.md#variable-run-time)** <br>Run time.  |
| [lava::platform](/_doxybook/Classes/structlava_1_1platform.md) | **[platform](/_doxybook/Classes/structlava_1_1frame.md#variable-platform)** <br>Stage platform.  |
| [message_dispatcher](/_doxybook/Classes/structlava_1_1message__dispatcher.md) | **[telegraph](/_doxybook/Classes/structlava_1_1frame.md#variable-telegraph)** <br>Message dispatcher.  |

## Additional inherited members

**Public Functions inherited from [lava::interface](/_doxybook/Classes/structlava_1_1interface.md)**

|                | Name           |
| -------------- | -------------- |
| virtual | **[~interface](/_doxybook/Classes/structlava_1_1interface.md#function-~interface)**() =default<br>Destroy the interface.  |

**Public Functions inherited from [lava::no_copy_no_move](/_doxybook/Classes/structlava_1_1no__copy__no__move.md)**

|                | Name           |
| -------------- | -------------- |
| | **[no_copy_no_move](/_doxybook/Classes/structlava_1_1no__copy__no__move.md#function-no-copy-no-move)**() =default<br>Construct a new object.  |
| | **[no_copy_no_move](/_doxybook/Classes/structlava_1_1no__copy__no__move.md#function-no-copy-no-move)**([no_copy_no_move](/_doxybook/Classes/structlava_1_1no__copy__no__move.md) const & ) =delete<br>No copy.  |
| void | **[operator=](/_doxybook/Classes/structlava_1_1no__copy__no__move.md#function-operator=)**([no_copy_no_move](/_doxybook/Classes/structlava_1_1no__copy__no__move.md) const & ) =delete<br>No move.  |


## Public Types Documentation

### using s_ptr

```cpp
using lava::frame::s_ptr =  std::shared_ptr<frame>;
```

Shared pointer to framework. 

### using result

```cpp
using lava::frame::result =  i32;
```

Framework result. 

### using run_func

```cpp
using lava::frame::run_func =  std::function<bool(id::ref)>;
```

Run function. 

### using run_func_ref

```cpp
using lava::frame::run_func_ref =  run_func const&;
```

Reference to run function. 

### using run_end_func

```cpp
using lava::frame::run_end_func =  std::function<void()>;
```

Run end function. 

### using run_end_func_ref

```cpp
using lava::frame::run_end_func_ref =  run_end_func const&;
```

Reference to run end function. 

### using run_once_func

```cpp
using lava::frame::run_once_func =  std::function<bool()>;
```

Run once function. 

### using run_once_func_ref

```cpp
using lava::frame::run_once_func_ref =  run_once_func const&;
```

Reference to run once function. 

## Public Functions Documentation

### function frame

```cpp
explicit frame(
    argh::parser cmd_line
)
```

Construct a new framework. 

**Parameters**: 

  * **[cmd_line](/_doxybook/Namespaces/namespacelava.md#using-cmd-line)** Command line arguments 


### function frame

```cpp
explicit frame(
    frame_env env
)
```

Construct a new framework. 

**Parameters**: 

  * **env** Framework environment 


### function ~frame

```cpp
~frame() override
```

Destroy the framework. 

### function ready

```cpp
inline bool ready() const
```

Check if framework is ready. 

**Return**: Framework is ready or not 

### function run

```cpp
result run()
```

Run the framework. 

**Return**: result Run result 

### function shut_down

```cpp
bool shut_down()
```

Shut down the framework. 

**Return**: Shut down was successful or failed 

### function add_run

```cpp
id add_run(
    run_func_ref func
)
```

Add run to framework. 

**Parameters**: 

  * **func** Run function 


**Return**: id Id of function 

### function add_run_end

```cpp
id add_run_end(
    run_end_func_ref func
)
```

Add run end to framework. 

**Parameters**: 

  * **func** Run end function 


**Return**: id Id of function 

### function add_run_once

```cpp
inline void add_run_once(
    run_once_func_ref func
)
```

Add run once to framework. 

**Parameters**: 

  * **func** Run once function 


### function remove

```cpp
bool remove(
    id::ref func_id
)
```

Remove a function from framework. 

**Parameters**: 

  * **func_id** Id of function 


**Return**: Remove was successful or failed 

### function get_running_time

```cpp
inline ms get_running_time() const
```

Get the running time. 

**Return**: ms Time since start of framework 

### function get_running_time_sec

```cpp
inline r64 get_running_time_sec() const
```

Get the running time in seconds. 

**Return**: [r64](/_doxybook/Namespaces/namespacelava.md#using-r64) Time since start of framework 

### function get_cmd_line

```cpp
inline cmd_line get_cmd_line() const
```

Get the command line arguments. 

**Return**: [cmd_line](/_doxybook/Namespaces/namespacelava.md#using-cmd-line) Command line arguments 

### function get_env

```cpp
inline frame_env::ref get_env() const
```

Get the framework environment. 

**Return**: [frame_env::ref](/_doxybook/Classes/structlava_1_1frame__env.md#using-ref) Framework environment 

### function get_name

```cpp
inline name get_name() const
```

Get the name of application. 

**Return**: name Name of application 

### function waiting_for_events

```cpp
inline bool waiting_for_events() const
```

Check if framework is waiting for events. 

**Return**: Framework waits for events or not 

### function set_wait_for_events

```cpp
inline void set_wait_for_events(
    bool value =true
)
```

Set wait for events in framework. 

**Parameters**: 

  * **value** Wait for events state 


## Public Attributes Documentation

### variable run_time

```cpp
lava::run_time run_time;
```

Run time. 

### variable platform

```cpp
lava::platform platform;
```

Stage platform. 

### variable telegraph

```cpp
message_dispatcher telegraph;
```

Message dispatcher. 

-------------------------------

Updated on 2026-02-01 at 18:13:39 +0000