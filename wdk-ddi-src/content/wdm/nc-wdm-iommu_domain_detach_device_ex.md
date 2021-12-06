---
UID: NC:wdm.IOMMU_DOMAIN_DETACH_DEVICE_EX
tech.root: kernel
title: IOMMU_DOMAIN_DETACH_DEVICE_EX
ms.date: 06/13/2021
targetos: Windows
description: Detaches a IOMMU_DMA_DEVICE from an existing domain.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: wdm.h
req.idl: 
req.include-header: Wdm.h
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: Windows Server 2022
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - LibDef
api_location:
 - wdm.h
api_name:
 - IOMMU_DOMAIN_DETACH_DEVICE_EX
f1_keywords:
 - IOMMU_DOMAIN_DETACH_DEVICE_EX
 - wdm/IOMMU_DOMAIN_DETACH_DEVICE_EX
dev_langs:
 - c++
---

## -description

Detaches a **IOMMU_DMA_DEVICE** from an existing domain.

## -parameters

### -param DmaDevice [in]


A pointer to the **IOMMU_DMA_DEVICE** to be detached.

## -returns

**STATUS_SUCCESS** if the operation is successful. Possible error return values include the following status codes.

| Return code | Description |
|--|--|
| STATUS_INVALID_PARAMETER_1 | The device could not be detached because it is not currently attached to any domain. |

For more information, see [NTSTATUS Values](/windows-hardware/drivers/kernel/ntstatus-values).

## -remarks

The caller must call `DetachDeviceEx` before attempting to attach the device to another domain.

## -see-also

[**IOMMU_DOMAIN_ATTACH_DEVICE_EX**](nc-wdm-iommu_domain_attach_device_ex.md)

[**DMA_IOMMU_INTERFACE_V2**](ns-wdm-dma_iommu_interface_v2.md)

[**DMA_IOMMU_INTERFACE_EX**](ns-wdm-dma_iommu_interface_ex.md)
