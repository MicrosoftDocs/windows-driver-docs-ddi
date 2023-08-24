---
UID: NS:wdm._DMA_IOMMU_INTERFACE_EX
tech.root: kernel
title: DMA_IOMMU_INTERFACE_EX
ms.date: 08/16/2023
targetos: Windows
description: An interface structure that allows device drivers to interface with the IOMMU functions that perform device domain operations.
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: wdm.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: Windows Server 2022
req.target-type: 
req.typenames: DMA_IOMMU_INTERFACE_EX, *PDMA_IOMMU_INTERFACE_EX
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wdm.h
api_name:
 - _DMA_IOMMU_INTERFACE_EX
 - PDMA_IOMMU_INTERFACE_EX
 - DMA_IOMMU_INTERFACE_EX
f1_keywords:
 - _DMA_IOMMU_INTERFACE_EX
 - wdm/_DMA_IOMMU_INTERFACE_EX
 - PDMA_IOMMU_INTERFACE_EX
 - wdm/PDMA_IOMMU_INTERFACE_EX
 - DMA_IOMMU_INTERFACE_EX
 - wdm/DMA_IOMMU_INTERFACE_EX
dev_langs:
 - c++
---

## -description

An interface structure that allows device drivers to interface with the IOMMU functions that perform device domain operations.

## -struct-fields

### -field Size

The size (in bytes) of the interface structure.

### -field Version

The interface version number that determines the set of interface functions that are provided by this interface structure.

### -field V1

A [**DMA_IOMMU_INTERFACE_V1**](ns-wdm-dma_iommu_interface_v1.md) structure that specifies the set of Version 1 (V1) IOMMU interface functions.

These are the same set of functions as those provided by the deprecated [**DMA_IOMMU_INTERFACE**](ns-wdm-_dma_iommu_interface.md) structure.

### -field V2

A [**DMA_IOMMU_INTERFACE_V2**](ns-wdm-dma_iommu_interface_v2.md) structure that specifies the set of Version 2 (V2) IOMMU interface functions.

## -remarks

Use this structure for V1 functions instead of the deprecated [**DMA_IOMMU_INTERFACE**](ns-wdm-_dma_iommu_interface.md) structure.

## -see-also

[**DMA_IOMMU_INTERFACE_V1**](ns-wdm-dma_iommu_interface_v1.md)

[**DMA_IOMMU_INTERFACE_V2**](ns-wdm-dma_iommu_interface_v2.md)

[IoGetIommuInterfaceEx](nf-wdm-iogetiommuinterfaceex.md)
