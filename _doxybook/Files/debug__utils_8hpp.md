---
title: liblava/base/debug_utils.hpp
summary: Debug utilities. 

---

# liblava/base/debug_utils.hpp

Debug utilities.  [More...](#detailed-description)

## Namespaces

| Name           |
| -------------- |
| **[lava](/_doxybook/Namespaces/namespacelava.md)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| struct | **[lava::scoped_label](/_doxybook/Classes/structlava_1_1scoped__label.md)** <br>Scoped debug util label.  |

## Defines

|                | Name           |
| -------------- | -------------- |
|  | **[LAVA_DEBUG_UTILS](/_doxybook/Files/debug__utils_8hpp.md#define-lava-debug-utils)** <br>Only active in debug - enable for release profiling.  |

## Detailed Description

Debug utilities. 

**Author**: Lava Block OÜ and contributors 

**Copyright**: Copyright (c) 2018-present, MIT License 



## Macros Documentation

### define LAVA_DEBUG_UTILS

```cpp
#define LAVA_DEBUG_UTILS LAVA_DEBUG
```

Only active in debug - enable for release profiling. 

## Source code

```cpp


#pragma once

#include "liblava/base/base.hpp"
#include "liblava/core/def.hpp"

#ifndef LAVA_DEBUG_UTILS
    #define LAVA_DEBUG_UTILS LAVA_DEBUG
#endif

namespace lava {

#if LAVA_DEBUG_UTILS

void begin_label(VkCommandBuffer cmd_buf,
                 name label,
                 v4 color);

void end_label(VkCommandBuffer cmd_buf);

void insert_label(VkCommandBuffer cmd_buf,
                  name label,
                  v4 color);

void begin_label(VkQueue queue,
                 name label,
                 v4 color);

void end_label(VkQueue queue);

void insert_label(VkQueue queue,
                  name label,
                  v4 color);

void set_object_name(VkDevice device,
                     VkObjectType type,
                     VkObjectHandle handle,
                     name object);

void set_object_tag(VkDevice device,
                    VkObjectType type,
                    VkObjectHandle handle,
                    ui64 name,
                    void_c_ptr tag,
                    size_t size);

#else

inline void begin_label(VkCommandBuffer cmd_buf,
                        name label,
                        v4 color) {}

inline void end_label(VkCommandBuffer cmd_buf) {}

inline void insert_label(VkCommandBuffer cmd_buf,
                         name label,
                         v4 color) {}

inline void begin_label(VkQueue queue,
                        name label,
                        v4 color) {}

inline void end_label(VkQueue queue) {}

inline void insert_label(VkQueue queue,
                         name label,
                         v4 color) {}

inline void set_object_name(VkDevice device,
                            VkObjectType type,
                            VkObjectHandle handle,
                            name object) {}

inline void set_object_tag(VkDevice device,
                           VkObjectType type,
                           VkObjectHandle handle,
                           ui64 name,
                           void_c_ptr tag,
                           size_t size) {}

#endif

template <typename T>
struct scoped_label {
    scoped_label(T scope, name label, v4 color = v4(0.f))
    : m_scope(scope) {
        begin_label(m_scope, label, color);
    }

    ~scoped_label() {
        end_label(m_scope);
    }

private:
    T m_scope;
};

inline void set_name(VkDevice device,
                     VkObjectHandle handle,
                     name object) {
    set_object_name(device,
                    VK_OBJECT_TYPE_UNKNOWN,
                    handle,
                    object);
}

inline void set_tag(VkDevice device,
                    VkObjectHandle handle,
                    ui64 name,
                    void_c_ptr tag,
                    size_t size) {
    set_object_tag(device,
                   VK_OBJECT_TYPE_UNKNOWN,
                   handle,
                   name,
                   tag,
                   size);
}

// ---

inline void set_instance_name(VkDevice device,
                              VkInstance handle,
                              name object) {
    set_object_name(device,
                    VK_OBJECT_TYPE_INSTANCE,
                    VkObjectHandle(handle),
                    object);
}

inline void set_instance_tag(VkDevice device,
                             VkInstance handle,
                             ui64 name,
                             void_c_ptr tag,
                             size_t size) {
    set_object_tag(device,
                   VK_OBJECT_TYPE_INSTANCE,
                   VkObjectHandle(handle),
                   name,
                   tag,
                   size);
}

// ---

inline void set_physical_device_name(VkDevice device,
                                     VkPhysicalDevice handle,
                                     name object) {
    set_object_name(device,
                    VK_OBJECT_TYPE_PHYSICAL_DEVICE,
                    VkObjectHandle(handle),
                    object);
}

inline void set_physical_device_tag(VkDevice device,
                                    VkPhysicalDevice handle,
                                    ui64 name,
                                    void_c_ptr tag,
                                    size_t size) {
    set_object_tag(device,
                   VK_OBJECT_TYPE_PHYSICAL_DEVICE,
                   VkObjectHandle(handle),
                   name,
                   tag,
                   size);
}

// ---

inline void set_device_name(VkDevice device,
                            name object) {
    set_object_name(device,
                    VK_OBJECT_TYPE_DEVICE,
                    VkObjectHandle(device),
                    object);
}

inline void set_device_tag(VkDevice device,
                           ui64 name,
                           void_c_ptr tag,
                           size_t size) {
    set_object_tag(device,
                   VK_OBJECT_TYPE_DEVICE,
                   VkObjectHandle(device),
                   name,
                   tag,
                   size);
}

// ---

inline void set_queue_name(VkDevice device,
                           VkQueue handle,
                           name object) {
    set_object_name(device,
                    VK_OBJECT_TYPE_QUEUE,
                    VkObjectHandle(handle),
                    object);
}

inline void set_queue_tag(VkDevice device,
                          VkQueue handle,
                          ui64 name,
                          void_c_ptr tag,
                          size_t size) {
    set_object_tag(device,
                   VK_OBJECT_TYPE_QUEUE,
                   VkObjectHandle(handle),
                   name,
                   tag,
                   size);
}

// ---

inline void set_semaphore_name(VkDevice device,
                               VkSemaphore handle,
                               name object) {
    set_object_name(device,
                    VK_OBJECT_TYPE_SEMAPHORE,
                    VkObjectHandle(handle),
                    object);
}

inline void set_semaphore_tag(VkDevice device,
                              VkSemaphore handle,
                              ui64 name,
                              void_c_ptr tag,
                              size_t size) {
    set_object_tag(device,
                   VK_OBJECT_TYPE_SEMAPHORE,
                   VkObjectHandle(handle),
                   name,
                   tag,
                   size);
}

// ---

inline void set_command_buffer_name(VkDevice device,
                                    VkCommandBuffer handle,
                                    name object) {
    set_object_name(device,
                    VK_OBJECT_TYPE_COMMAND_BUFFER,
                    VkObjectHandle(handle),
                    object);
}

inline void set_command_buffer_tag(VkDevice device,
                                   VkCommandBuffer handle,
                                   ui64 name,
                                   void_c_ptr tag,
                                   size_t size) {
    set_object_tag(device,
                   VK_OBJECT_TYPE_COMMAND_BUFFER,
                   VkObjectHandle(handle),
                   name,
                   tag,
                   size);
}

// ---

inline void set_fence_name(VkDevice device,
                           VkFence handle,
                           name object) {
    set_object_name(device,
                    VK_OBJECT_TYPE_FENCE,
                    VkObjectHandle(handle),
                    object);
}

inline void set_fence_tag(VkDevice device,
                          VkFence handle,
                          ui64 name,
                          void_c_ptr tag,
                          size_t size) {
    set_object_tag(device,
                   VK_OBJECT_TYPE_FENCE,
                   VkObjectHandle(handle),
                   name,
                   tag,
                   size);
}

// ---

inline void set_device_memory_name(VkDevice device,
                                   VkDeviceMemory handle,
                                   name object) {
    set_object_name(device,
                    VK_OBJECT_TYPE_DEVICE_MEMORY,
                    VkObjectHandle(handle),
                    object);
}

inline void set_device_memory_tag(VkDevice device,
                                  VkDeviceMemory handle,
                                  ui64 name,
                                  void_c_ptr tag,
                                  size_t size) {
    set_object_tag(device,
                   VK_OBJECT_TYPE_DEVICE_MEMORY,
                   VkObjectHandle(handle),
                   name,
                   tag,
                   size);
}

// ---

inline void set_buffer_name(VkDevice device,
                            VkBuffer handle,
                            name object) {
    set_object_name(device,
                    VK_OBJECT_TYPE_BUFFER,
                    VkObjectHandle(handle),
                    object);
}

inline void set_buffer_tag(VkDevice device,
                           VkBuffer handle,
                           ui64 name,
                           void_c_ptr tag,
                           size_t size) {
    set_object_tag(device,
                   VK_OBJECT_TYPE_BUFFER,
                   VkObjectHandle(handle),
                   name,
                   tag,
                   size);
}

// ---

inline void set_image_name(VkDevice device,
                           VkImage handle,
                           name object) {
    set_object_name(device,
                    VK_OBJECT_TYPE_IMAGE,
                    VkObjectHandle(handle),
                    object);
}

inline void set_image_tag(VkDevice device,
                          VkImage handle,
                          ui64 name,
                          void_c_ptr tag,
                          size_t size) {
    set_object_tag(device,
                   VK_OBJECT_TYPE_IMAGE,
                   VkObjectHandle(handle),
                   name,
                   tag,
                   size);
}

// ---

inline void set_event_name(VkDevice device,
                           VkEvent handle,
                           name object) {
    set_object_name(device,
                    VK_OBJECT_TYPE_EVENT,
                    VkObjectHandle(handle),
                    object);
}

inline void set_event_tag(VkDevice device,
                          VkEvent handle,
                          ui64 name,
                          void_c_ptr tag,
                          size_t size) {
    set_object_tag(device,
                   VK_OBJECT_TYPE_EVENT,
                   VkObjectHandle(handle),
                   name,
                   tag,
                   size);
}

// ---

inline void set_query_pool_name(VkDevice device,
                                VkQueryPool handle,
                                name object) {
    set_object_name(device,
                    VK_OBJECT_TYPE_QUERY_POOL,
                    VkObjectHandle(handle),
                    object);
}

inline void set_query_pool_tag(VkDevice device,
                               VkQueryPool handle,
                               ui64 name,
                               void_c_ptr tag,
                               size_t size) {
    set_object_tag(device,
                   VK_OBJECT_TYPE_QUERY_POOL,
                   VkObjectHandle(handle),
                   name,
                   tag,
                   size);
}

// ---

inline void set_buffer_view_name(VkDevice device,
                                 VkBufferView handle,
                                 name object) {
    set_object_name(device,
                    VK_OBJECT_TYPE_BUFFER_VIEW,
                    VkObjectHandle(handle),
                    object);
}

inline void set_buffer_view_tag(VkDevice device,
                                VkBufferView handle,
                                ui64 name,
                                void_c_ptr tag,
                                size_t size) {
    set_object_tag(device,
                   VK_OBJECT_TYPE_BUFFER_VIEW,
                   VkObjectHandle(handle),
                   name,
                   tag,
                   size);
}

// ---

inline void set_image_view_name(VkDevice device,
                                VkImageView handle,
                                name object) {
    set_object_name(device,
                    VK_OBJECT_TYPE_IMAGE_VIEW,
                    VkObjectHandle(handle),
                    object);
}

inline void set_image_view_tag(VkDevice device,
                               VkImageView handle,
                               ui64 name,
                               void_c_ptr tag,
                               size_t size) {
    set_object_tag(device,
                   VK_OBJECT_TYPE_IMAGE_VIEW,
                   VkObjectHandle(handle),
                   name,
                   tag,
                   size);
}

// ---

inline void set_shader_module_name(VkDevice device,
                                   VkShaderModule handle,
                                   name object) {
    set_object_name(device,
                    VK_OBJECT_TYPE_SHADER_MODULE,
                    VkObjectHandle(handle),
                    object);
}

inline void set_shader_module_tag(VkDevice device,
                                  VkShaderModule handle,
                                  ui64 name,
                                  void_c_ptr tag,
                                  size_t size) {
    set_object_tag(device,
                   VK_OBJECT_TYPE_SHADER_MODULE,
                   VkObjectHandle(handle),
                   name,
                   tag,
                   size);
}

// ---

inline void set_pipeline_cache_name(VkDevice device,
                                    VkPipelineCache handle,
                                    name object) {
    set_object_name(device,
                    VK_OBJECT_TYPE_PIPELINE_CACHE,
                    VkObjectHandle(handle),
                    object);
}

inline void set_pipeline_cache_tag(VkDevice device,
                                   VkPipelineCache handle,
                                   ui64 name,
                                   void_c_ptr tag,
                                   size_t size) {
    set_object_tag(device,
                   VK_OBJECT_TYPE_PIPELINE_CACHE,
                   VkObjectHandle(handle),
                   name,
                   tag,
                   size);
}

// ---

inline void set_pipeline_layout_name(VkDevice device,
                                     VkPipelineLayout handle,
                                     name object) {
    set_object_name(device,
                    VK_OBJECT_TYPE_PIPELINE_LAYOUT,
                    VkObjectHandle(handle),
                    object);
}

inline void set_pipeline_layout_tag(VkDevice device,
                                    VkPipelineLayout handle,
                                    ui64 name,
                                    void_c_ptr tag,
                                    size_t size) {
    set_object_tag(device,
                   VK_OBJECT_TYPE_PIPELINE_LAYOUT,
                   VkObjectHandle(handle),
                   name,
                   tag,
                   size);
}

// ---

inline void set_render_pass_name(VkDevice device,
                                 VkRenderPass handle,
                                 name object) {
    set_object_name(device,
                    VK_OBJECT_TYPE_RENDER_PASS,
                    VkObjectHandle(handle),
                    object);
}

inline void set_render_pass_tag(VkDevice device,
                                VkRenderPass handle,
                                ui64 name,
                                void_c_ptr tag,
                                size_t size) {
    set_object_tag(device,
                   VK_OBJECT_TYPE_RENDER_PASS,
                   VkObjectHandle(handle),
                   name,
                   tag,
                   size);
}

// ---

inline void set_pipeline_name(VkDevice device,
                              VkPipeline handle,
                              name object) {
    set_object_name(device,
                    VK_OBJECT_TYPE_PIPELINE,
                    VkObjectHandle(handle),
                    object);
}

inline void set_pipeline_tag(VkDevice device,
                             VkPipeline handle,
                             ui64 name,
                             void_c_ptr tag,
                             size_t size) {
    set_object_tag(device,
                   VK_OBJECT_TYPE_PIPELINE,
                   VkObjectHandle(handle),
                   name,
                   tag,
                   size);
}

// ---

inline void set_descriptor_set_layout_name(VkDevice device,
                                           VkDescriptorSetLayout handle,
                                           name object) {
    set_object_name(device,
                    VK_OBJECT_TYPE_DESCRIPTOR_SET_LAYOUT,
                    VkObjectHandle(handle),
                    object);
}

inline void set_descriptor_set_layout_tag(VkDevice device,
                                          VkDescriptorSetLayout handle,
                                          ui64 name,
                                          void_c_ptr tag,
                                          size_t size) {
    set_object_tag(device,
                   VK_OBJECT_TYPE_DESCRIPTOR_SET_LAYOUT,
                   VkObjectHandle(handle),
                   name,
                   tag,
                   size);
}

// ---

inline void set_sampler_name(VkDevice device,
                             VkSampler handle,
                             name object) {
    set_object_name(device,
                    VK_OBJECT_TYPE_SAMPLER,
                    VkObjectHandle(handle),
                    object);
}

inline void set_sampler_tag(VkDevice device,
                            VkSampler handle,
                            ui64 name,
                            void_c_ptr tag,
                            size_t size) {
    set_object_tag(device,
                   VK_OBJECT_TYPE_SAMPLER,
                   VkObjectHandle(handle),
                   name,
                   tag,
                   size);
}

// ---

inline void set_descriptor_pool_name(VkDevice device,
                                     VkDescriptorPool handle,
                                     name object) {
    set_object_name(device,
                    VK_OBJECT_TYPE_DESCRIPTOR_POOL,
                    VkObjectHandle(handle),
                    object);
}

inline void set_descriptor_pool_tag(VkDevice device,
                                    VkDescriptorPool handle,
                                    ui64 name,
                                    void_c_ptr tag,
                                    size_t size) {
    set_object_tag(device,
                   VK_OBJECT_TYPE_DESCRIPTOR_POOL,
                   VkObjectHandle(handle),
                   name,
                   tag,
                   size);
}

// ---

inline void set_descriptor_set_name(VkDevice device,
                                    VkDescriptorSet handle,
                                    name object) {
    set_object_name(device,
                    VK_OBJECT_TYPE_DESCRIPTOR_SET,
                    VkObjectHandle(handle),
                    object);
}

inline void set_descriptor_set_tag(VkDevice device,
                                   VkDescriptorSet handle,
                                   ui64 name,
                                   void_c_ptr tag,
                                   size_t size) {
    set_object_tag(device,
                   VK_OBJECT_TYPE_DESCRIPTOR_SET,
                   VkObjectHandle(handle),
                   name,
                   tag,
                   size);
}

// ---

inline void set_framebuffer_name(VkDevice device,
                                 VkFramebuffer handle,
                                 name object) {
    set_object_name(device,
                    VK_OBJECT_TYPE_FRAMEBUFFER,
                    VkObjectHandle(handle),
                    object);
}

inline void set_framebuffer_tag(VkDevice device,
                                VkFramebuffer handle,
                                ui64 name,
                                void_c_ptr tag,
                                size_t size) {
    set_object_tag(device,
                   VK_OBJECT_TYPE_FRAMEBUFFER,
                   VkObjectHandle(handle),
                   name,
                   tag,
                   size);
}

// ---

inline void set_command_pool_name(VkDevice device,
                                  VkCommandPool handle,
                                  name object) {
    set_object_name(device,
                    VK_OBJECT_TYPE_COMMAND_POOL,
                    VkObjectHandle(handle),
                    object);
}

inline void set_command_pool_tag(VkDevice device,
                                 VkCommandPool handle,
                                 ui64 name,
                                 void_c_ptr tag,
                                 size_t size) {
    set_object_tag(device,
                   VK_OBJECT_TYPE_COMMAND_POOL,
                   VkObjectHandle(handle),
                   name,
                   tag,
                   size);
}

// ---

inline void set_sampler_ycbcr_conversion_name(VkDevice device,
                                              VkSamplerYcbcrConversion handle,
                                              name object) {
    set_object_name(device,
                    VK_OBJECT_TYPE_SAMPLER_YCBCR_CONVERSION,
                    VkObjectHandle(handle),
                    object);
}

inline void set_sampler_ycbcr_conversion_tag(VkDevice device,
                                             VkSamplerYcbcrConversion handle,
                                             ui64 name,
                                             void_c_ptr tag,
                                             size_t size) {
    set_object_tag(device,
                   VK_OBJECT_TYPE_SAMPLER_YCBCR_CONVERSION,
                   VkObjectHandle(handle),
                   name,
                   tag,
                   size);
}

// ---

inline void set_descriptor_update_template_name(VkDevice device,
                                                VkDescriptorUpdateTemplate handle,
                                                name object) {
    set_object_name(device,
                    VK_OBJECT_TYPE_DESCRIPTOR_UPDATE_TEMPLATE,
                    VkObjectHandle(handle),
                    object);
}

inline void set_descriptor_update_template_tag(VkDevice device,
                                               VkDescriptorUpdateTemplate handle,
                                               ui64 name,
                                               void_c_ptr tag,
                                               size_t size) {
    set_object_tag(device,
                   VK_OBJECT_TYPE_DESCRIPTOR_UPDATE_TEMPLATE,
                   VkObjectHandle(handle),
                   name,
                   tag,
                   size);
}

// ---

inline void set_surface_name(VkDevice device,
                             VkSurfaceKHR handle,
                             name object) {
    set_object_name(device,
                    VK_OBJECT_TYPE_SURFACE_KHR,
                    VkObjectHandle(handle),
                    object);
}

inline void set_surface_tag(VkDevice device,
                            VkSurfaceKHR handle,
                            ui64 name,
                            void_c_ptr tag,
                            size_t size) {
    set_object_tag(device,
                   VK_OBJECT_TYPE_SURFACE_KHR,
                   VkObjectHandle(handle),
                   name,
                   tag,
                   size);
}

// ---

inline void set_swapchain_name(VkDevice device,
                               VkSwapchainKHR handle,
                               name object) {
    set_object_name(device,
                    VK_OBJECT_TYPE_SWAPCHAIN_KHR,
                    VkObjectHandle(handle),
                    object);
}

inline void set_swapchain_tag(VkDevice device,
                              VkSwapchainKHR handle,
                              ui64 name,
                              void_c_ptr tag,
                              size_t size) {
    set_object_tag(device,
                   VK_OBJECT_TYPE_SWAPCHAIN_KHR,
                   VkObjectHandle(handle),
                   name,
                   tag,
                   size);
}

// ---

inline void set_display_name(VkDevice device,
                             VkDisplayKHR handle,
                             name object) {
    set_object_name(device,
                    VK_OBJECT_TYPE_DISPLAY_KHR,
                    VkObjectHandle(handle),
                    object);
}

inline void set_display_tag(VkDevice device,
                            VkDisplayKHR handle,
                            ui64 name,
                            void_c_ptr tag,
                            size_t size) {
    set_object_tag(device,
                   VK_OBJECT_TYPE_DISPLAY_KHR,
                   VkObjectHandle(handle),
                   name,
                   tag,
                   size);
}

// ---

inline void set_display_mode_name(VkDevice device,
                                  VkDisplayModeKHR handle,
                                  name object) {
    set_object_name(device,
                    VK_OBJECT_TYPE_DISPLAY_MODE_KHR,
                    VkObjectHandle(handle),
                    object);
}

inline void set_display_mode_tag(VkDevice device,
                                 VkDisplayModeKHR handle,
                                 ui64 name,
                                 void_c_ptr tag,
                                 size_t size) {
    set_object_tag(device,
                   VK_OBJECT_TYPE_DISPLAY_MODE_KHR,
                   VkObjectHandle(handle),
                   name,
                   tag,
                   size);
}

// ---

inline void set_debug_report_callback_name(VkDevice device,
                                           VkDebugReportCallbackEXT handle,
                                           name object) {
    set_object_name(device,
                    VK_OBJECT_TYPE_DEBUG_REPORT_CALLBACK_EXT,
                    VkObjectHandle(handle),
                    object);
}

inline void set_debug_report_callback_tag(VkDevice device,
                                          VkDebugReportCallbackEXT handle,
                                          ui64 name,
                                          void_c_ptr tag,
                                          size_t size) {
    set_object_tag(device,
                   VK_OBJECT_TYPE_DEBUG_REPORT_CALLBACK_EXT,
                   VkObjectHandle(handle),
                   name,
                   tag,
                   size);
}

// ---

inline void set_indirect_commands_layout_name(VkDevice device,
                                              VkIndirectCommandsLayoutNV handle,
                                              name object) {
    set_object_name(device,
                    VK_OBJECT_TYPE_INDIRECT_COMMANDS_LAYOUT_NV,
                    VkObjectHandle(handle),
                    object);
}

inline void set_indirect_commands_layout_tag(VkDevice device,
                                             VkIndirectCommandsLayoutNV handle,
                                             ui64 name,
                                             void_c_ptr tag,
                                             size_t size) {
    set_object_tag(device,
                   VK_OBJECT_TYPE_INDIRECT_COMMANDS_LAYOUT_NV,
                   VkObjectHandle(handle),
                   name,
                   tag,
                   size);
}

// ---

inline void set_debug_utils_messenger_name(VkDevice device,
                                           VkDebugUtilsMessengerEXT handle,
                                           name object) {
    set_object_name(device,
                    VK_OBJECT_TYPE_DEBUG_UTILS_MESSENGER_EXT,
                    VkObjectHandle(handle),
                    object);
}

inline void set_debug_utils_messenger_tag(VkDevice device,
                                          VkDebugUtilsMessengerEXT handle,
                                          ui64 name,
                                          void_c_ptr tag,
                                          size_t size) {
    set_object_tag(device,
                   VK_OBJECT_TYPE_DEBUG_UTILS_MESSENGER_EXT,
                   VkObjectHandle(handle),
                   name,
                   tag,
                   size);
}

// ---

inline void set_validation_cache_name(VkDevice device,
                                      VkValidationCacheEXT handle,
                                      name object) {
    set_object_name(device,
                    VK_OBJECT_TYPE_VALIDATION_CACHE_EXT,
                    VkObjectHandle(handle),
                    object);
}

inline void set_validation_cache_tag(VkDevice device,
                                     VkValidationCacheEXT handle,
                                     ui64 name,
                                     void_c_ptr tag,
                                     size_t size) {
    set_object_tag(device,
                   VK_OBJECT_TYPE_VALIDATION_CACHE_EXT,
                   VkObjectHandle(handle),
                   name,
                   tag,
                   size);
}

// ---

inline void set_acceleration_structure_nv_name(VkDevice device,
                                               VkAccelerationStructureNV handle,
                                               name object) {
    set_object_name(device,
                    VK_OBJECT_TYPE_ACCELERATION_STRUCTURE_NV,
                    VkObjectHandle(handle),
                    object);
}

inline void set_acceleration_structure_nv_tag(VkDevice device,
                                              VkAccelerationStructureNV handle,
                                              ui64 name,
                                              void_c_ptr tag,
                                              size_t size) {
    set_object_tag(device,
                   VK_OBJECT_TYPE_ACCELERATION_STRUCTURE_NV,
                   VkObjectHandle(handle),
                   name,
                   tag,
                   size);
}

// ---

inline void set_acceleration_structure_name(VkDevice device,
                                            VkAccelerationStructureKHR handle,
                                            name object) {
    set_object_name(device,
                    VK_OBJECT_TYPE_ACCELERATION_STRUCTURE_KHR,
                    VkObjectHandle(handle),
                    object);
}

inline void set_acceleration_structure_tag(VkDevice device,
                                           VkAccelerationStructureKHR handle,
                                           ui64 name,
                                           void_c_ptr tag,
                                           size_t size) {
    set_object_tag(device,
                   VK_OBJECT_TYPE_ACCELERATION_STRUCTURE_KHR,
                   VkObjectHandle(handle),
                   name,
                   tag,
                   size);
}

// ---

inline void set_performance_configuration_name(VkDevice device,
                                               VkPerformanceConfigurationINTEL handle,
                                               name object) {
    set_object_name(device,
                    VK_OBJECT_TYPE_PERFORMANCE_CONFIGURATION_INTEL,
                    VkObjectHandle(handle),
                    object);
}

inline void set_performance_configuration_tag(VkDevice device,
                                              VkPerformanceConfigurationINTEL handle,
                                              ui64 name,
                                              void_c_ptr tag,
                                              size_t size) {
    set_object_tag(device,
                   VK_OBJECT_TYPE_PERFORMANCE_CONFIGURATION_INTEL,
                   VkObjectHandle(handle),
                   name,
                   tag,
                   size);
}

// ---

inline void set_deferred_operation_name(VkDevice device,
                                        VkDeferredOperationKHR handle,
                                        name object) {
    set_object_name(device,
                    VK_OBJECT_TYPE_DEFERRED_OPERATION_KHR,
                    VkObjectHandle(handle),
                    object);
}

inline void set_deferred_operation_tag(VkDevice device,
                                       VkDeferredOperationKHR handle,
                                       ui64 name,
                                       void_c_ptr tag,
                                       size_t size) {
    set_object_tag(device,
                   VK_OBJECT_TYPE_DEFERRED_OPERATION_KHR,
                   VkObjectHandle(handle),
                   name,
                   tag,
                   size);
}

// ---

inline void set_private_data_slot_name(VkDevice device,
                                       VkPrivateDataSlotEXT handle,
                                       name object) {
    set_object_name(device,
                    VK_OBJECT_TYPE_PRIVATE_DATA_SLOT_EXT,
                    VkObjectHandle(handle),
                    object);
}

inline void set_private_data_slot_tag(VkDevice device,
                                      VkPrivateDataSlotEXT handle,
                                      ui64 name,
                                      void_c_ptr tag,
                                      size_t size) {
    set_object_tag(device,
                   VK_OBJECT_TYPE_PRIVATE_DATA_SLOT_EXT,
                   VkObjectHandle(handle),
                   name,
                   tag,
                   size);
}

} // namespace lava
```


-------------------------------

Updated on 2026-02-01 at 18:13:39 +0000
