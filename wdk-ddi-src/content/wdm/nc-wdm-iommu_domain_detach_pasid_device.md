---
UID: NC:wdm.IOMMU_DOMAIN_DETACH_PASID_DEVICE
tech.root: kernel
title: IOMMU_DOMAIN_DETACH_PASID_DEVICE
ms.date: 08/06/2025
targetos: Windows
description: Detaches a PASID sub-device from the domain it is currently attached to. 
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
 - IOMMU_DOMAIN_DETACH_PASID_DEVICE
f1_keywords:
 - IOMMU_DOMAIN_DETACH_PASID_DEVICE
 - wdm/IOMMU_DOMAIN_DETACH_PASID_DEVICE
dev_langs:
 - c++
helpviewer_keywords:
 - IOMMU_DOMAIN_DETACH_PASID_DEVICE
---

## -description

**IOMMU_DOMAIN_DETACH_PASID_DEVICE** detaches a PASID sub-device from the domain it is currently attached to.

## -parameters

### -param PasidDevice

[in] Pointer to the IOMMU_DMA_PASID_DEVICE structure that represents the PASID sub-device to be detached.

## -returns

Returns an NTSTATUS value. Possible values include:

| Return code | Description |
|--|--|
| **STATUS_SUCCESS** | On successful sub-device detachment from the domain. |
| **STATUS_INVALID_PARAMETER_1** | The sub-device could not be detached because it was never attached. |

## -remarks

It is the driver's responsibility to ensure that this function is not called concurrently with any of the following on the same device:

- [**IOMMU_PASID_DEVICE_DELETE**](nc-wdm-iommu_pasid_device_delete.md)
- [**IOMMU_DOMAIN_DELETE**](nc-wdm-iommu_domain_delete.md)
- [**IOMMU_DOMAIN_ATTACH_PASID_DEVICE**](nc-wdm-iommu_domain_attach_pasid_device.md)
- [**IOMMU_DOMAIN_DETACH_PASID_DEVICE**](nc-wdm-iommu_domain_detach_pasid_device.md)

## -see-also

[**IOMMU_DOMAIN_ATTACH_PASID_DEVICE**](nc-wdm-iommu_domain_attach_pasid_device.md)

[**IOMMU_PASID_DEVICE_DELETE**](nc-wdm-iommu_pasid_device_delete.md)
