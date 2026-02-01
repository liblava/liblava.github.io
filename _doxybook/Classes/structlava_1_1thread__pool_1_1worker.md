---
title: lava::thread_pool::worker
summary: Thread worker. 

---

# lava::thread_pool::worker



Thread worker. 

## Public Functions

|                | Name           |
| -------------- | -------------- |
| | **[worker](/_doxybook/Classes/structlava_1_1thread__pool_1_1worker.md#function-worker)**([thread_pool](/_doxybook/Classes/structlava_1_1thread__pool.md) & pool)<br>Construct a new worker.  |
| void | **[operator()](/_doxybook/Classes/structlava_1_1thread__pool_1_1worker.md#function-operator())**()<br>Run task operator.  |

## Public Functions Documentation

### function worker

```cpp
inline explicit worker(
    thread_pool & pool
)
```

Construct a new worker. 

**Parameters**: 

  * **pool** Thread pool 


### function operator()

```cpp
inline void operator()()
```

Run task operator. 

-------------------------------

Updated on 2026-02-01 at 18:13:39 +0000