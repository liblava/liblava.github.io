---
title: liblava/base/base.hpp
summary: Vulkan base types. 

---

# liblava/base/base.hpp

Vulkan base types.  [More...](#detailed-description)

## Namespaces

| Name           |
| -------------- |
| **[lava](/_doxybook/Namespaces/namespacelava.md)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| struct | **[lava::vk_result](/_doxybook/Classes/structlava_1_1vk__result.md)** <br>Vulkan result.  |
| struct | **[lava::target_callback](/_doxybook/Classes/structlava_1_1target__callback.md)** <br>Target callback.  |

## Defines

|                | Name           |
| -------------- | -------------- |
|  | **[VK_NO_PROTOTYPES](/_doxybook/Files/base_2base_8hpp.md#define-vk-no-prototypes)**  |

## Detailed Description

Vulkan base types. 

**Author**: Lava Block OÜ and contributors 

**Copyright**: Copyright (c) 2018-present, MIT License 



## Macros Documentation

### define VK_NO_PROTOTYPES

```cpp
#define VK_NO_PROTOTYPES 
```


## Source code

```cpp

#pragma once

#include <liblava/core/version.hpp>
#include <liblava/util/math.hpp>

// clang-format off

#define VK_NO_PROTOTYPES
#include <vulkan/vulkan.h>
#include <volk.h>

// clang-format on

namespace lava {

using VkObjectHandle = ui64;

using VkFormats = std::vector<VkFormat>;

using VkImages = std::vector<VkImage>;

using VkImagesRef = VkImages const&;

using VkImageViews = std::vector<VkImageView>;

using VkFramebuffers = std::vector<VkFramebuffer>;

using VkCommandPools = std::vector<VkCommandPool>;

using VkCommandBuffers = std::vector<VkCommandBuffer>;

using VkFences = std::vector<VkFence>;

using VkSemaphores = std::vector<VkSemaphore>;

using VkPresentModeKHRs = std::vector<VkPresentModeKHR>;

using VkDescriptorSets = std::vector<VkDescriptorSet>;

using VkDescriptorSetLayouts = std::vector<VkDescriptorSetLayout>;

using VkDescriptorSetLayoutBindings = std::vector<VkDescriptorSetLayoutBinding>;

using VkDescriptorPoolSizes = std::vector<VkDescriptorPoolSize>;

using VkDescriptorPoolSizesRef = VkDescriptorPoolSizes const&;

using VkPushConstantRanges = std::vector<VkPushConstantRange>;

using VkAttachmentReferences = std::vector<VkAttachmentReference>;

using VkClearValues = std::vector<VkClearValue>;

using VkPipelineShaderStageCreateInfos = std::vector<VkPipelineShaderStageCreateInfo>;

using VkSpecializationMapEntries = std::vector<VkSpecializationMapEntry>;

using VkVertexInputBindingDescriptions = std::vector<VkVertexInputBindingDescription>;

using VkVertexInputAttributeDescriptions = std::vector<VkVertexInputAttributeDescription>;

using VkPipelineColorBlendAttachmentStates = std::vector<VkPipelineColorBlendAttachmentState>;

using VkDynamicStates = std::vector<VkDynamicState>;

using VkQueueFamilyPropertiesList = std::vector<VkQueueFamilyProperties>;

using VkExtensionPropertiesList = std::vector<VkExtensionProperties>;

using VkLayerPropertiesList = std::vector<VkLayerProperties>;

using VkExtensionPropertiesList = std::vector<VkExtensionProperties>;

using VkPhysicalDevices = std::vector<VkPhysicalDevice>;

bool check(VkResult result);

inline bool failed(VkResult result) {
    return !check(result);
}

string to_string(VkResult result);

string version_to_string(ui32 version);

int_version to_version(ui32 version);

ui32 to_version(int_version version);

enum class api_version : index {
    v1_0 = 0,
    v1_1,
    v1_2,
    v1_3
};

api_version to_api_version(ui32 version);

struct vk_result {
    bool state = false;

    VkResult value = VK_NOT_READY;

    operator bool() {
        return state;
    }
};

constexpr bool const build_failed = false;

constexpr bool const build_done = true;

using VkAttachments = std::vector<VkImageViews>;

using VkAttachmentsRef = VkAttachments const&;

struct target_callback {
    using cptr = target_callback const*;

    using list = std::vector<target_callback*>;

    using clist = std::vector<cptr>;

    using created_func = std::function<bool(VkAttachmentsRef, rect::ref)>;

    created_func on_created;

    using destroyed_func = std::function<void()>;

    destroyed_func on_destroyed;
};

constexpr ui32 const Vk_Limit_DescriptorSets = 4;

constexpr ui32 const Vk_Limit_Bindings = 16;

constexpr ui32 const Vk_Limit_Attachments = 8;

constexpr ui32 const Vk_Limit_VertexAttribs = 16;

constexpr ui32 const Vk_Limit_VertexBuffers = 4;

constexpr ui32 const Vk_Limit_PushConstant_Size = 128;

constexpr ui32 const Vk_Limit_UBO_Size = 16 * 1024;

} // namespace lava
```


-------------------------------

Updated on 2022-11-30 at 01:16:04 +0000
