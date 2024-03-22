---
title: liblava/core/id.hpp
summary: Object Identification. 

---

# liblava/core/id.hpp

Object Identification.  [More...](#detailed-description)

## Namespaces

| Name           |
| -------------- |
| **[lava](/_doxybook/Namespaces/namespacelava.md)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| struct | **[lava::id](/_doxybook/Classes/structlava_1_1id.md)** <br>Identification.  |
| struct | **[lava::ids](/_doxybook/Classes/structlava_1_1ids.md)** <br>Id factory.  |
| struct | **[lava::id_listeners](/_doxybook/Classes/structlava_1_1id__listeners.md)** <br>Id listeners.  |
| struct | **[lava::entity](/_doxybook/Classes/structlava_1_1entity.md)** <br>Entity.  |
| struct | **[lava::id_registry](/_doxybook/Classes/structlava_1_1id__registry.md)** <br>Id registry.  |

## Detailed Description

Object Identification. 

**Author**: Lava Block OÜ and contributors 

**Copyright**: Copyright (c) 2018-present, MIT License 



## Source code

```cpp

#pragma once

#include <atomic>
#include <deque>
#include <memory>
#include <mutex>
#include <set>
#include "liblava/core/types.hpp"

namespace lava {

struct id {
    using ref = id const&;

    using set = std::set<id>;

    using set_ref = set const&;

    using list = std::vector<id>;

    using map = std::map<id, id>;

    using index_map = std::map<id, index>;

    using string_map = std::map<id, string>;

    id() = default;

    id(index value)
    : value(value) {}

    index value = no_index;

    bool valid() const {
        return value != no_index;
    }

    string to_string() const {
        return std::to_string(value);
    }

    void invalidate() {
        *this = {};
    }

    auto operator<=>(id const&) const = default;
};

using string_id_map = std::map<string, id>;

constexpr id const undef_id = id();

inline id to_id(auto value) {
    return { static_cast<index>(value) };
}

struct ids {
    static ids& instance() {
        static ids ids;
        return ids;
    }

    id next() {
        return { ++next_id };
    }

private:
    std::atomic<index> next_id = { no_index };
};

template<typename T>
inline id add_id_map(T const& object,
                     std::map<id, T>& map) {
    auto next = ids::instance().next();
    map.emplace(next, std::move(object));
    return next;
}

template<typename T>
inline bool remove_id_map(id::ref object_id,
                          std::map<id, T>& map) {
    if (!map.count(object_id))
        return false;

    map.erase(object_id);

    return true;
}

template<typename T>
struct id_listeners {
    id add(typename T::func const& listener) {
        return add_id_map(listener, list);
    }

    void remove(id& id) {
        if (remove_id_map(id, list))
            id.invalidate();
    }

    typename T::listeners const& get_list() const {
        return list;
    }

private:
    typename T::listeners list = {};
};

struct entity : no_copy_no_move, interface {
    entity()
    : entity_id(ids::instance().next()) {}

    id::ref get_id() const {
        return entity_id;
    }

private:
    id entity_id;
};

template<typename T, typename Meta>
struct id_registry {
    using ptr = std::shared_ptr<T>;

    using map = std::map<id, ptr>;

    using meta_map = std::map<id, Meta>;

    id create(Meta info = {}) {
        auto object = std::make_shared<T>();
        add(object, info);

        return object->get_id();
    }

    void add(ptr object,
             Meta info = {}) {
        objects.emplace(object->get_id(), object);
        meta.emplace(object->get_id(), info);
    }

    bool exists(id::ref object_id) const {
        return objects.count(object_id);
    }

    ptr get(id::ref object_id) const {
        return objects.at(object_id);
    }

    Meta const& get_meta(id::ref object_id) const {
        return meta.at(object_id);
    }

    map const& get_all() const {
        return objects;
    }

    meta_map const& get_all_meta() const {
        return meta;
    }

    bool update(id::ref object_id,
                Meta const& meta) {
        if (!exists(object_id))
            return false;

        meta.at(object_id) = meta;
        return true;
    }

    void remove(id::ref object_id) {
        objects.erase(object_id);
        meta.erase(object_id);
    }

    void clear() {
        objects.clear();
        meta.clear();
    }

private:
    map objects;

    meta_map meta;
};

} // namespace lava
```


-------------------------------

Updated on 2024-03-22 at 21:51:38 +0000
