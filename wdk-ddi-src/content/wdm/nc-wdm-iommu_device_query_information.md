---
UID: NC:wdm.IOMMU_DEVICE_QUERY_INFORMATION
tech.root: kernel
title: IOMMU_DEVICE_QUERY_INFORMATION
ms.date: 08/06/2025
targetos: Windows
description: Queries information about an IOMMU DMA device. 
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: wdm.h
req.idl: 
req.include-header: 
req.irql: PASSIVE_LEVEL 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
ai-usage: ai-assisted 
topic_type:
 - apiref
api_type:
 - LibDef
api_location:
 - wdm.h
api_name:
 - IOMMU_DEVICE_QUERY_INFORMATION
f1_keywords:
 - IOMMU_DEVICE_QUERY_INFORMATION
 - wdm/IOMMU_DEVICE_QUERY_INFORMATION
dev_langs:
 - c++
helpviewer_keywords:
 - IOMMU_DEVICE_QUERY_INFORMATION
---

## -description

**IOMMU_DEVICE_QUERY_INFORMATION** takes an IOMMU_DMA_DEVICE token and returns the device info.

## -parameters

### -param DmaDevice

[in] Pointer to the IOMMU_DMA_DEVICE token.

### -param Size

[in] Supplies the size in bytes of the provided buffer.

### -param BytesWritten

[out] Pointer to receive the number of bytes written to the buffer.

### -param Buffer

[out] Pointer to a [**IOMMU_DMA_DEVICE_INFORMATION**](ns-wdm-iommu_dma_device_information.md) structure that receives the device information.

## -returns

Returns an NTSTATUS value. Possible values include:

| Return code | Description |
|--|--|
| **STATUS_SUCCESS** | If the device info was successfully written into the buffer. |
| **STATUS_BUFFER_TOO_SMALL** | If the provided buffer does not meet minimum size requirements. |

## -remarks

## -see-also

[**IOMMU_PASID_DEVICE_CREATE**](nc-wdm-iommu_pasid_device_create.md)

[**IOMMU_DMA_DEVICE_INFORMATION**](ns-wdm-iommu_dma_device_information.md)
