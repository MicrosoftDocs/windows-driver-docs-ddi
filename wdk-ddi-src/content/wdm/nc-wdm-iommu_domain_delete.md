---
UID: NC:wdm.IOMMU_DOMAIN_DELETE
title: IOMMU_DOMAIN_DELETE (wdm.h)
description: Deletes an existing domain.
tech.root: kernel
ms.date: 01/19/2023
keywords: ["IOMMU_DOMAIN_DELETE callback function"]
req.header: wdm.h
req.include-header: Wdm.h
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1803
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.irql: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
targetos: Windows
f1_keywords:
 - IOMMU_DOMAIN_DELETE
 - wdm/IOMMU_DOMAIN_DELETE
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - wdm.h
api_name:
 - IOMMU_DOMAIN_DELETE
---

## -description

Deletes an existing domain. The domain must contain no devices in order to be successfully deleted.

## -parameters

### -param Domain [_In_]

A pointer to the handle to the domain to be deleted.

## -returns

Return **STATUS_SUCCESS** if the operation succeeds. Otherwise, return an appropriate NTSTATUS values error code. For more information, see [NTSTATUS Values](/windows-hardware/drivers/kernel/ntstatus-values).

## -remarks

This can be called on any **IOMMU_DMA_DOMAIN** that was created through either the [**DMA_IOMMU_INTERFACE_EX**](ns-wdm-dma_iommu_interface_ex.md) or [**DMA_IOMMU_INTERFACE**](ns-wdm-_dma_iommu_interface.md).

## -see-also

[IOMMU_DOMAIN_CREATE_EX](nc-wdm-iommu_domain_create_ex.md)

[**DMA_IOMMU_INTERFACE_V2**](ns-wdm-dma_iommu_interface_v2.md)

[**DMA_IOMMU_INTERFACE_EX**](ns-wdm-dma_iommu_interface_ex.md)
