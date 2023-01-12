---
UID: NS:wdm._DMA_ADAPTER_INFO
tech.root: kernel
title: DMA_ADAPTER_INFO (wdm.h)
ms.date: 03/02/2022
targetos: Windows
description: The DMA_ADAPTER_INFO structure is a container for a DMA_ADAPTER_INFO_XXX structure that describes the capabilities of a system DMA controller.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Supported starting with Windows 8.
req.target-min-winversvr: 
req.target-type: Windows
req.typenames: DMA_ADAPTER_INFO, *PDMA_ADAPTER_INFO
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wdm.h
api_name:
 - _DMA_ADAPTER_INFO
 - PDMA_ADAPTER_INFO
 - DMA_ADAPTER_INFO
f1_keywords:
 - _DMA_ADAPTER_INFO
 - wdm/_DMA_ADAPTER_INFO
 - PDMA_ADAPTER_INFO
 - wdm/PDMA_ADAPTER_INFO
 - DMA_ADAPTER_INFO
 - wdm/DMA_ADAPTER_INFO
dev_langs:
 - c++
helpviewer_keywords:
 - _DMA_ADAPTER_INFO
---

## -description

The DMA_ADAPTER_INFO structure is a container for a DMA_ADAPTER_INFO_XXX structure that describes the capabilities of a system DMA controller.

## -struct-fields

### -field Version

The version number of the **DMA_ADAPTER_INFO_***XXX* structure that follows this member. For a [DMA_ADAPTER_INFO_V1](./ns-wdm-_dma_adapter_info_v1.md) structure, set this member to DMA_ADAPTER_INFO_VERSION1 before calling the [GetDmaAdapterInfo](./nc-wdm-pget_dma_adapter_info.md) routine.

### -field V1

The capabilities of the bus-master DMA device or the system DMA controller. For more information, see [DMA_ADAPTER_INFO_V1](./ns-wdm-_dma_adapter_info_v1.md).

### -field Crashdump

Defines the **DMA_ADAPTER_INFO_CRASHDUMP** member **Crashdump**.

## -remarks

A device driver calls the [GetDmaAdapterInfo](./nc-wdm-pget_dma_adapter_info.md) routine to obtain a **DMA_ADAPTER_INFO** structure that describes the capabilities of a DMA controller.

The unnamed union in this structure contains a **DMA_ADAPTER_INFO_***XXX* structure. The **Version** member indicates which version of the **DMA_ADAPTER_INFO_***XXX* structure is contained in the union. Currently, only version 1 is supported.

## -see-also

[DMA_ADAPTER_INFO_V1](./ns-wdm-_dma_adapter_info_v1.md)

[GetDmaAdapterInfo](./nc-wdm-pget_dma_adapter_info.md)