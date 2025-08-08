---
UID: NC:wdm.IOMMU_PASID_DEVICE_CREATE
tech.root: kernel
title: IOMMU_PASID_DEVICE_CREATE
ms.date: 08/06/2025
targetos: Windows
description: Creates a new sub-device with its own PASID from an IOMMU DMA device. 
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
 - IOMMU_PASID_DEVICE_CREATE
f1_keywords:
 - IOMMU_PASID_DEVICE_CREATE
 - wdm/IOMMU_PASID_DEVICE_CREATE
dev_langs:
 - c++
helpviewer_keywords:
 - IOMMU_PASID_DEVICE_CREATE
---

## -description

**IOMMU_PASID_DEVICE_CREATE** takes an IOMMU_DMA_DEVICE token and spawns a new PASID sub-device representing the newly assigned ASID.

## -parameters

### -param DmaDevice

[in] Pointer to the IOMMU_DMA_DEVICE token from which sub-devices are spawned.

[in] Pointer to the IOMMU_DMA_DEVICE token from which sub-devices are spawned.

### -param PasidDeviceOut

[out] Pointer to an opaque IOMMU_DMA_PASID_DEVICE structure that represents the newly created IOMMU DMA PASID sub-device.

### -param AsidOut

[out] Pointer to hold the system-assigned PASID.

## -returns

**IOMMU_PASID_DEVICE_CREATE** returns an NTSTATUS value. Possible values include:

| Return code | Description |
|--|--|
| **STATUS_SUCCESS** | The sub-device was successfully created. **PasidDeviceOut** returns a valid pointer. |
| **STATUS_INVALID_PARAMETER_1** | The provided device token is not configured for PASID-tagged DMA or PASIDs are not supported. |
| **STATUS_INSUFFICIENT_RESOURCES** | Not enough memory to allocate an IOMMU_DMA_PASID_DEVICE structure. |
| **STATUS_NONE_MAPPED** | An ASID could not be allocated. |

## -remarks

## -see-also

[**IOMMU_PASID_DEVICE_DELETE**](nc-wdm-iommu_pasid_device_delete.md)

[**IOMMU_DOMAIN_ATTACH_PASID_DEVICE**](nc-wdm-iommu_domain_attach_pasid_device.md)

[**IOMMU_DOMAIN_DETACH_PASID_DEVICE**](nc-wdm-iommu_domain_detach_pasid_device.md)
