---
UID: NC:wdm.IOMMU_DOMAIN_ATTACH_DEVICE_EX
tech.root: kernel
title: IOMMU_DOMAIN_ATTACH_DEVICE_EX
ms.date: 06/04/2021
targetos: Windows
description: Attaches an IOMMU_DMA_DEVICE to an existing DMA device domain.
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
 - IOMMU_DOMAIN_ATTACH_DEVICE_EX
f1_keywords:
 - IOMMU_DOMAIN_ATTACH_DEVICE_EX
 - wdm/IOMMU_DOMAIN_ATTACH_DEVICE_EX
dev_langs:
 - c++
---

## -description

Attaches an **IOMMU_DMA_DEVICE** to an existing DMA device domain.

## -parameters

### -param Domain

[*In*] A handle to the domain that the **IOMMU_DMA_DEVICE** will attach to.

### -param DmaDevice

[*In*] A pointer to the **IOMMU_DMA_DEVICE** to be attached.

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
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
The routine failed to allocate required resources.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The device is already attached to a domain.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_ACCESS_DENIED</b></dt>
</dl>
</td>
<td width="60%">
The device is currently not allowed to attach to this domain type.

</td>
</tr>
</table>

For more information, see [NTSTATUS Values](/windows-hardware/drivers/kernel/ntstatus-values).

## -remarks

The caller is responsible for ensuring that the **IOMMU_DMA_DEVICE** is first detached, using [**IOMMU_DOMAIN_DETACH_DEVICE_EX**](nc-wdm-iommu_domain_detach_device_ex.md), from any previously attached domain before attempting to attach it to another domain.

It is the driver's responsibility to ensure that this function is not called concurrently with any [**IOMMU_DOMAIN_DETACH_DEVICE_EX**](nc-wdm-iommu_domain_detach_device_ex.md) or [**IOMMU_SET_DEVICE_FAULT_REPORTING_EX**](nc-wdm-iommu_set_device_fault_reporting_ex.md) calls on the same device.

If `STATUS_ACCESS_DENIED` is returned, then it is likely the domain type is not currently available for the device to attach to. It is recommended to utilize [**IOMMU_DEVICE_QUERY_DOMAIN_TYPES**](nc-wdm-iommu_device_query_domain_types.md) to determine what domain types are available for the specified device. The types available can vary depending on the DMA Guard policy and the device characteristics. To be notified of when domain types are available, consider using [**IOMMU_REGISTER_INTERFACE_STATE_CHANGE_CALLBACK**](nc-wdm-iommu_register_interface_state_change_callback.md) to register a notification callback whenever the available domain types change.

## -see-also

[**IOMMU_DOMAIN_DETACH_DEVICE_EX**](nc-wdm-iommu_domain_detach_device_ex.md)

[**IOMMU_SET_DEVICE_FAULT_REPORTING_EX**](nc-wdm-iommu_set_device_fault_reporting_ex.md)

[**IOMMU_DEVICE_QUERY_DOMAIN_TYPES**](nc-wdm-iommu_device_query_domain_types.md)

[**IOMMU_REGISTER_INTERFACE_STATE_CHANGE_CALLBACK**](nc-wdm-iommu_register_interface_state_change_callback.md)

[**DMA_IOMMU_INTERFACE_V2**](ns-wdm-dma_iommu_interface_v2.md)

[**DMA_IOMMU_INTERFACE_EX**](ns-wdm-dma_iommu_interface_ex.md)
