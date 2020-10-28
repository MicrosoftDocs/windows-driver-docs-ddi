---
UID: NE:wdm._DMA_COMMON_BUFFER_EXTENDED_CONFIGURATION_TYPE
title: DMA_COMMON_BUFFER_EXTENDED_CONFIGURATION_TYPE (wdm.h)
description: Provides the types of optional configurations that can be provided when creating a common buffer from an MDL. The configuration values corresponding to the types are held in the DMA_COMMON_BUFFER_EXTENDED_CONFIGURATION structure.
tech.root:
ms.assetid: 7a3c7fc8-e72d-4555-8f93-c1171c07c3f4
ms.date: 08/19/2020
keywords: ["DMA_COMMON_BUFFER_EXTENDED_CONFIGURATION_TYPE enumeration"]
f1_keywords:
 - "wdm/DMA_COMMON_BUFFER_EXTENDED_CONFIGURATION_TYPE"
 - "DMA_COMMON_BUFFER_EXTENDED_CONFIGURATION_TYPE"
req.header: wdm.h
req.include-header:
req.target-type: Desktop
req.target-min-winverclnt: Windows 10, version [FUTURE]
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.ddi-compliance:
req.max-support:
req.typenames: DMA_COMMON_BUFFER_EXTENDED_CONFIGURATION_TYPE, *PDMA_COMMON_BUFFER_EXTENDED_CONFIGURATION_TYPE
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - wdm.h
api_name:
 - DMA_COMMON_BUFFER_EXTENDED_CONFIGURATION_TYPE
targetos: Windows
---

# TODO: Copy STUB branch once available

# DMA_COMMON_BUFFER_EXTENDED_CONFIGURATION_TYPE enumeration

## -description

Provides the types of optional configurations that can be provided when creating a common buffer from an MDL. The configuration values corresponding to the types are held in the [DMA_COMMON_BUFFER_EXTENDED_CONFIGURATION](ns-wdm-_dma_common_buffer_extended_configuration.md) structure.

## -prototype

```cpp
typedef enum _DMA_COMMON_BUFFER_EXTENDED_CONFIGURATION_TYPE {
    CommonBufferConfigTypeLogicalAddressLimits,
    CommonBufferConfigTypeSubSection,
    CommonBufferConfigTypeHardwareAccessPermissions,
    CommonBufferConfigTypeMax,
} DMA_COMMON_BUFFER_EXTENDED_CONFIGURATION_TYPE,
  *PDMA_COMMON_BUFFER_EXTENDED_CONFIGURATION_TYPE;
```

## -enum-fields

### -field CommonBufferConfigTypeLogicalAddressLimits

The associated configuration will contain information about the limits of logical address that can be used to fulfill common buffer creation.

### -field CommonBufferConfigTypeSubSection

The associated configuration will contain information about the subsection within the MDL to use to create the common buffer.

### -field CommonBufferConfigTypeAccessPermissions

The associated configuration will contain information about the access permissions for the hardware.

### -field CommonBufferConfigTypeMax

The number of common buffer extended configuration values for this enumeration type that represent actual common buffer configuration types.

## -see-also

[DMA_COMMON_BUFFER_EXTENDED_CONFIGURATION](ns-wdm-_dma_common_buffer_extended_configuration.md)

[PCREATE_COMMON_BUFFER_FROM_MDL](nc-wdm-pcreate-common-buffer-from-mdl.md)