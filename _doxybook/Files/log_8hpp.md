---
title: liblava/util/log.hpp
summary: Logging. 

---

# liblava/util/log.hpp

Logging.  [More...](#detailed-description)

## Namespaces

| Name           |
| -------------- |
| **[lava](/_doxybook/Namespaces/namespacelava.md)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| struct | **[lava::log_config](/_doxybook/Classes/structlava_1_1log__config.md)** <br>Log configuration.  |
| struct | **[lava::global_logger](/_doxybook/Classes/structlava_1_1global__logger.md)** <br>Global logger.  |

## Detailed Description

Logging. 

**Author**: Lava Block OÜ and contributors 

**Copyright**: Copyright (c) 2018-present, MIT License 



## Source code

```cpp

#pragma once

#include <memory>
#include "liblava/core/version.hpp"
#include "spdlog/sinks/basic_file_sink.h"
#include "spdlog/sinks/stdout_color_sinks.h"
#include "spdlog/spdlog.h"

namespace lava {

using logger = std::shared_ptr<spdlog::logger>;

inline string to_string(string_ref id, string_ref name) {
    return fmt::format("{} | {}", id, name);
}

inline string to_string(sem_version const& version) {
    return fmt::format("{}.{}.{}",
                       version.major,
                       version.minor,
                       version.patch);
}

inline string semantic_version_string() {
    return to_string(sem_version{});
}

inline string sem_version_string() {
    return semantic_version_string();
}

inline name to_string(version_stage stage) {
    switch (stage) {
    case version_stage::preview:
        return "preview";
    case version_stage::alpha:
        return "alpha";
    case version_stage::beta:
        return "beta";
    case version_stage::rc:
        return "rc";
    default:
        return "";
    }
}

inline string to_string(version const& version) {
    string stage_str = to_string(version.stage);
    if ((version.rev > 1) && (version.stage != version_stage::release))
        stage_str += fmt::format(" {}", version.rev);

    if (version.release == 0) {
        if (stage_str.empty())
            return fmt::format("{}", version.year);
        else
            return fmt::format("{} {}",
                               version.year, stage_str);
    } else
        return fmt::format("{}.{} {}",
                           version.year, version.release, stage_str);
}

inline string version_string() {
    return to_string(version{});
}

struct log_config {
    name logger = _lava_;

    name file = "lava.log";

    i32 level = undef;

    bool debug = false;
};

inline logger setup_log(log_config config = {}) {
    if (config.debug) {
        auto log = spdlog::stdout_color_mt(config.logger);
        log->set_level((config.level < 0)
                           ? spdlog::level::debug
                           : (spdlog::level::level_enum) config.level);
        return log;
    } else {
        auto log = spdlog::basic_logger_mt(config.logger, config.file);
        log->set_level((config.level < 0)
                           ? spdlog::level::warn
                           : (spdlog::level::level_enum) config.level);
        return log;
    }
}

inline void teardown_log(log_config config = {}) {
    spdlog::drop(config.logger);
}

struct global_logger {
    static global_logger& singleton() {
        static global_logger global_logger;
        return global_logger;
    }

    logger get() {
        return log;
    }

    void set(lava::logger l) {
        log = l;
    }

    void reset() {
        log = nullptr;
    }

private:
    logger log;
};

inline logger log() {
    return global_logger::singleton().get();
}

} // namespace lava
```


-------------------------------

Updated on 2024-03-22 at 21:51:38 +0000
