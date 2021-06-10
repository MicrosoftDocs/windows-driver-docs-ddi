---
UID: NC:wdm.IOMMU_DEVICE_DELETE
tech.root: kernel
title: IOMMU_DEVICE_DELETE
ms.date: 06/04/2021
targetos: Windows
description: Deletes the provided IOMMU_DMA_DEVICE.
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
 - IOMMU_DEVICE_DELETE
f1_keywords:
 - IOMMU_DEVICE_DELETE
 - wdm/IOMMU_DEVICE_DELETE
dev_langs:
 - c++
---

## -description

Deletes the provided opaque token representing the **IOMMU_DMA_DEVICE**.

## -parameters

### -param DmaDevice

[*In*] A pointer to the opaque token representing the **IOMMU_DMA_DEVICE** to be deleted.

## -returns

**STATUS_SUCCESS** if the operation is successful. Possible error return values include the following status codes.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_RESOURCE_IN_USE</b></dt>
</dl>
</td>
<td width="60%">
The device is still attached to a domain. Callers are responsible for calling [**DetachDeviceEx**](nc-wdm-iommu_domain_detach_device_ex.md) before calling `DeleteDevice`.

</td>
</tr>
</table>

For more information, see [NTSTATUS Values](/windows-hardware/drivers/kernel/ntstatus-values).

## -remarks

The caller must ensure that the **IOMMU_DMA_DEVICE** is detached from any domain it was previously attached to before the caller attempts to delete and free the device.

## -see-also

[**IOMMU_DEVICE_CREATE**](nc-wdm-iommu_device_create.md)

[**DMA_IOMMU_INTERFACE_V2**](ns-wdm-dma_iommu_interface_v2.md)

[**DMA_IOMMU_INTERFACE_EX**](ns-wdm-dma_iommu_interface_ex.md)
