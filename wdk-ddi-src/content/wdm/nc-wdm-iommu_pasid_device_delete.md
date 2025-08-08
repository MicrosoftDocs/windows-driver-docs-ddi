---
UID: NC:wdm.IOMMU_PASID_DEVICE_DELETE
tech.root: kernel
title: IOMMU_PASID_DEVICE_DELETE
ms.date: 08/06/2025
targetos: Windows
description: Deletes a PASID sub-device and frees its ASID. 
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
 - IOMMU_PASID_DEVICE_DELETE
f1_keywords:
 - IOMMU_PASID_DEVICE_DELETE
 - wdm/IOMMU_PASID_DEVICE_DELETE
dev_langs:
 - c++
helpviewer_keywords:
 - IOMMU_PASID_DEVICE_DELETE
---

## -description

**IOMMU_PASID_DEVICE_DELETE** deletes a PASID sub-device and frees its ASID.

## -parameters

### -param PasidDevice

[in] Pointer to the IOMMU_DMA_PASID_DEVICE structure that represents the PASID sub-device to be deleted.

## -returns

Returns an NTSTATUS value. Possible values include:

| Return code | Description |
|--|--|
| **STATUS_SUCCESS** | On successful deletion of the PASID sub-device. |
| **STATUS_RESOURCE_IN_USE** | Device is still attached to a domain. Callers are responsible detaching devices from domains before deleting the device. |

## -remarks

Callers are responsible for detaching devices from domains before deleting the device.

## -see-also

[**IOMMU_PASID_DEVICE_CREATE**](nc-wdm-iommu_pasid_device_create.md)

[**IOMMU_DOMAIN_DETACH_PASID_DEVICE**](nc-wdm-iommu_domain_detach_pasid_device.md)
