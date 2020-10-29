---
UID: NS:wdm._DMA_COMMON_BUFFER_EXTENDED_CONFIGURATION
title: DMA_COMMON_BUFFER_EXTENDED_CONFIGURATION
ms.date: 10/28/2020
ms.topic: language-reference
targetos: Windows
description:
req.construct-type: structure
req.ddi-compliance:
req.dll:
req.header: wdm.h
req.include-header:
req.kmdf-ver:
req.lib:
req.max-support:
req.redist:
req.target-min-winverclnt: Windows 10, version [FUTURE]
req.target-min-winversvr:
req.target-type:
req.typenames: DMA_COMMON_BUFFER_EXTENDED_CONFIGURATION, *PDMA_COMMON_BUFFER_EXTENDED_CONFIGURATION
req.umdf-ver:
req.unicode-ansi:
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wdm.h
api_name:
 - _DMA_COMMON_BUFFER_EXTENDED_CONFIGURATION
 - PDMA_COMMON_BUFFER_EXTENDED_CONFIGURATION
 - DMA_COMMON_BUFFER_EXTENDED_CONFIGURATION
f1_keywords:
 - _DMA_COMMON_BUFFER_EXTENDED_CONFIGURATION
 - wdm/_DMA_COMMON_BUFFER_EXTENDED_CONFIGURATION
 - PDMA_COMMON_BUFFER_EXTENDED_CONFIGURATION
 - wdm/PDMA_COMMON_BUFFER_EXTENDED_CONFIGURATION
 - DMA_COMMON_BUFFER_EXTENDED_CONFIGURATION
 - wdm/DMA_COMMON_BUFFER_EXTENDED_CONFIGURATION
dev_langs:
 - c++
---

# DMA_COMMON_BUFFER_EXTENDED_CONFIGURATION structure

## -description

Defines a configuration that further describes constraints and features when creating a common buffer. The driver can provide an array of **DMA_COMMON_BUFFER_EXTENDED_CONFIGURATION** structures in the [*CreateCommonBufferFromMdl*](nc-wdm-pcreate-common-buffer-from-mdl.md) callback routine.

## -struct-fields

### -field ConfigType

A [**DMA_COMMON_BUFFER_EXTENDED_CONFIGURATION_TYPE**](ne-wdm-_dma_common_buffer_extended_configuration_type.md)-typed value that indicates the type of common buffer extended configuration this instance represents.

### -field LogicalAddressLimits

When *ConfigType* is **CommonBufferConfigTypeLogicalAddressLimits**, describes the logical address limits for the common buffer being created.

### -field LogicalAddressLimits.MinimumAddress

Provides the (inclusive) minimum starting logical address of the common buffer being created.

### -field LogicalAddressLimits.MaximumAddress

Provides the (inclusive) maximum final logical address of the common buffer being created.

### -field SubSection

When *ConfigType* is **CommonBufferConfigTypeSubSection**, describes the subsection within a backing MDL that should be used to back the common buffer being created.

> [!NOTE]
> A subsection must only be contained within a single MDL in an MDL chain.

### -field SubSection.Offset

Provides the offset into the MDL to indicate the starting address of the common buffer. **Must be page-aligned.**

### -field SubSection.Length

Provides the length of the common buffer subsection. **Must be page-aligned.**

### -field HardwareAccessType

When *ConfigType* is **CommonBufferConfigTypeHardwareAccessPermissions**, this is a [**DMA_COMMON_BUFFER_EXTENDED_CONFIGURATION_ACCESS_TYPE**](ne-wdm-dma_common_buffer_extended_configuration_access_type.md)-typed value that describes the hardware access permissions for the common buffer being created.

> [!NOTE]
> Common buffer creation fails if the access type is not possible on the system. **ReadOnly** and **WriteOnly** are only permissible if the DMA Adapter is using DMA Remapping.

### -field Reserved

This field is unused.

## -remarks

The extended configurations are an optional parameter for the [*CreateCommonBufferFromMdl*](nc-wdm-pcreate-common-buffer-from-mdl.md) callback routine.

If no extended configurations are provided, common buffer creation uses the entire MDL as backing memory, with a minimum logical address of zero and a maximum logical address defined by the [**DMA_ADAPTER**](ns-wdm-_dma_adapter.md) being used.

## -see-also

[**DMA_COMMON_BUFFER_EXTENDED_CONFIGURATION_TYPE**](ne-wdm-_dma_common_buffer_extended_configuration_type.md) enumeration

[**DMA_COMMON_BUFFER_EXTENDED_CONFIGURATION_ACCESS_TYPE**](ne-wdm-_dma_common_buffer_extended_configuration_access_type.md) enumeration

[*PCREATE_COMMON_BUFFER_FROM_MDL*](nc-wdm-pcreate-common-buffer-from-mdl.md) callback routine

