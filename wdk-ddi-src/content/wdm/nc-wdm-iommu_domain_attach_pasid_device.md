---
UID: NC:wdm.IOMMU_DOMAIN_ATTACH_PASID_DEVICE
tech.root: kernel
title: IOMMU_DOMAIN_ATTACH_PASID_DEVICE
ms.date: 08/06/2025
targetos: Windows
description: Attaches a PASID sub-device to an existing domain. 
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
 - IOMMU_DOMAIN_ATTACH_PASID_DEVICE
f1_keywords:
 - IOMMU_DOMAIN_ATTACH_PASID_DEVICE
 - wdm/IOMMU_DOMAIN_ATTACH_PASID_DEVICE
dev_langs:
 - c++
helpviewer_keywords:
 - IOMMU_DOMAIN_ATTACH_PASID_DEVICE
---

## -description

**IOMMU_DOMAIN_ATTACH_PASID_DEVICE** attaches a PASID sub-device to an existing domain.

## -parameters

### -param Domain

[in] Handle to the domain that the sub-device will attach to.

### -param PasidDevice

[in] Pointer to the IOMMU_DMA_PASID_DEVICE structure that represents the PASID sub-device to be attached.

## -returns

Returns an NTSTATUS value. Possible values include:

| Return code | Description |
|--|--|
| **STATUS_SUCCESS** | On successful sub-device attachment to the domain. |
| **STATUS_INSUFFICIENT_RESOURCES** | Not enough memory to allocate a cached device for attach/detach bookkeeping. |
| **STATUS_INVALID_PARAMETER_1** | The device is not allowed to attach to the domain type provided. |
| **STATUS_UNSUCCESSFUL** | The sub-device is already attached to a domain. |
| **STATUS_ACCESS_DENIED** | The sub-device is currently not allowed to attach to this domain. |

## -remarks

It is the driver's responsibility to ensure that this function is not called concurrently with any of the following on the same device:

- [**IOMMU_PASID_DEVICE_DELETE**](nc-wdm-iommu_pasid_device_delete.md)
- [**IOMMU_DOMAIN_DELETE_DEVICE**](nc-wdm-iommu_domain_delete_device.md)
- [**IOMMU_DOMAIN_ATTACH_PASID_DEVICE**](nc-wdm-iommu_domain_attach_pasid_device.md)
- [**IOMMU_DOMAIN_DETACH_PASID_DEVICE**](nc-wdm-iommu_domain_detach_pasid_device.md)

## -see-also

[**IOMMU_PASID_DEVICE_CREATE**](nc-wdm-iommu_pasid_device_create.md)

[**IOMMU_DOMAIN_DETACH_PASID_DEVICE**](nc-wdm-iommu_domain_detach_pasid_device.md)
