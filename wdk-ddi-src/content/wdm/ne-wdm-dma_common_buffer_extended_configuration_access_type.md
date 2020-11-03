---
UID: NE:wdm._DMA_COMMON_BUFFER_EXTENDED_CONFIGURATION_ACCESS_TYPE
title: DMA_COMMON_BUFFER_EXTENDED_CONFIGURATION_ACCESS_TYPE
ms.date: 10/28/2020
ms.topic: language-reference
targetos: Windows
description:
req.construct-type: enumeration
req.ddi-compliance:
req.header: wdm.h
req.include-header:
req.kmdf-ver:
req.max-support:
req.target-min-winverclnt: Windows 10, version [FUTURE]
req.target-min-winversvr:
req.target-type:
req.typenames:
req.umdf-ver:
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wdm.h
api_name:
 - _DMA_COMMON_BUFFER_EXTENDED_CONFIGURATION_ACCESS_TYPE
 - PDMA_COMMON_BUFFER_EXTENDED_CONFIGURATION_ACCESS_TYPE
 - DMA_COMMON_BUFFER_EXTENDED_CONFIGURATION_ACCESS_TYPE
f1_keywords:
 - _DMA_COMMON_BUFFER_EXTENDED_CONFIGURATION_ACCESS_TYPE
 - wdm/_DMA_COMMON_BUFFER_EXTENDED_CONFIGURATION_ACCESS_TYPE
 - PDMA_COMMON_BUFFER_EXTENDED_CONFIGURATION_ACCESS_TYPE
 - wdm/PDMA_COMMON_BUFFER_EXTENDED_CONFIGURATION_ACCESS_TYPE
 - DMA_COMMON_BUFFER_EXTENDED_CONFIGURATION_ACCESS_TYPE
 - wdm/DMA_COMMON_BUFFER_EXTENDED_CONFIGURATION_ACCESS_TYPE
dev_langs:
 - c++
---

## -description

Provides the permissions for hardware access for a common buffer being created
when using a [DMA_COMMON_BUFFER_EXTENDED_CONFIGURATION](ns-wdm-_dma_common_buffer_extended_configuration.md) of type *CommonBufferConfigTypeHardwareAccessPermissions*.

## -enum-fields

### -fields CommonBufferHardwareAccessReadOnly

Hardware will only have read access to the common buffer being created.

### -field CommonBufferHardwareAccessWriteOnly

Hardware will only have write access to the common buffer being created.

### -field CommonBufferHardwareAccessReadWrite

Hardware will have both read and write access to the common buffer being created.

### -field CommonBufferHardwareAccessMax

The number of common buffer hardware access values for this enumeration type that represent actual access types.

## -see-also

[DMA_COMMON_BUFFER_EXTENDED_CONFIGURATION](ns-wdm-_dma_common_buffer_extended_configuration.md)

[PCREATE_COMMON_BUFFER_FROM_MDL](nc-wdm-pcreate-common-buffer-from-mdl.md)

