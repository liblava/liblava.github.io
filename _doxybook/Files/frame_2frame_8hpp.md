---
title: liblava/frame/frame.hpp
summary: Framework. 

---

# liblava/frame/frame.hpp

Framework.  [More...](#detailed-description)

## Namespaces

| Name           |
| -------------- |
| **[lava](/_doxybook/Namespaces/namespacelava.md)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| struct | **[lava::frame_env](/_doxybook/Classes/structlava_1_1frame__env.md)** <br>Framework environment.  |
| struct | **[lava::frame](/_doxybook/Classes/structlava_1_1frame.md)** <br>Framework.  |

## Detailed Description

Framework. 

**Author**: Lava Block OÜ and contributors 

**Copyright**: Copyright (c) 2018-present, MIT License 



## Source code

```cpp

#pragma once

#include <liblava/base/device.hpp>
#include <liblava/base/instance.hpp>
#include <liblava/base/platform.hpp>
#include <liblava/core/time.hpp>
#include <liblava/frame/argh.hpp>

namespace lava {

struct frame_env {
    using ref = frame_env const&;

    explicit frame_env() {
        set_default();
    }

    explicit frame_env(name app_name,
                       argh::parser cmd_line)
    : cmd_line(cmd_line) {
        info.app_name = app_name;
        set_default();
    }

    void set_default();

    argh::parser cmd_line;

    log_config log;

    instance_info info;

    instance::create_param param;

    instance::debug_config debug;
};

enum error {
    not_ready = -1,
    create_failed = -2,
    init_failed = -3,
    load_failed = -4,
    run_aborted = -5,
    still_running = -6,
    program_failed = -7,
};

ms now();

constexpr bool const run_abort = false;

constexpr bool const run_continue = true;

struct frame : interface, no_copy_no_move {
    using ptr = std::shared_ptr<frame>;

    explicit frame(argh::parser cmd_line);

    explicit frame(frame_env env);

    ~frame() override;

    bool ready() const {
        return initialized;
    }

    using result = i32; // error < 0

    result run();

    bool shut_down();

    using run_func = std::function<bool(id::ref)>;

    using run_func_ref = run_func const&;

    id add_run(run_func_ref func);

    using run_end_func = std::function<void()>;

    using run_end_func_ref = run_end_func const&;

    id add_run_end(run_end_func_ref func);

    using run_once_func = std::function<bool()>;

    using run_once_func_ref = run_once_func const&;

    void add_run_once(run_once_func_ref func) {
        run_once_list.push_back(func);
    }

    bool remove(id::ref func_id);

    ms get_running_time() const {
        return now() - start_time;
    }

    r64 get_running_time_sec() const {
        return to_sec(get_running_time());
    }

    cmd_line get_cmd_line() const {
        return env.cmd_line;
    }

    frame_env::ref get_env() const {
        return env;
    }

    name get_name() const {
        return env.info.app_name;
    }

    bool waiting_for_events() const {
        return wait_for_events;
    }

    void set_wait_for_events(bool value = true) {
        wait_for_events = value;
    }

    platform_t platform;

private:
    bool setup();

    void teardown();

    bool run_step();

    void trigger_run_remove();

    void trigger_run_end();

    bool initialized = false;

    frame_env env;

    bool running = false;

    bool wait_for_events = false;

    ms start_time;

    using run_func_map = std::map<id, run_func>;

    run_func_map run_map;

    using run_end_func_map = std::map<id, run_end_func>;

    run_end_func_map run_end_map;

    using run_once_func_list = std::vector<run_once_func>;

    run_once_func_list run_once_list;

    id::list run_remove_list;
};

void handle_events(bool wait = false);

void handle_events(ms timeout);

void handle_events(seconds timeout);

void post_empty_event();

} // namespace lava
```


-------------------------------

Updated on 2022-11-30 at 01:16:04 +0000
