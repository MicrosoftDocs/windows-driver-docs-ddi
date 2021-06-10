---
UID: NC:wdm.IOMMU_DEVICE_CREATE
tech.root: kernel
title: IOMMU_DEVICE_CREATE
ms.date: 06/04/2021
targetos: Windows
description: Takes a physical device object and creates an IOMMU_DMA_DEVICE.
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
 - IOMMU_DEVICE_CREATE
f1_keywords:
 - IOMMU_DEVICE_CREATE
 - wdm/IOMMU_DEVICE_CREATE
dev_langs:
 - c++
---

## -description

Takes a physical device object and creates an opaque token representing the **IOMMU_DMA_DEVICE** that can be used with the IOMMU interface APIs.

## -parameters

### -param DeviceObject

[*In*] A pointer to the physical device object of the device that the created **IOMMU_DMA_DEVICE** will represent.

### -param DeviceConfig

[*In*, optional] An optional pointer to a list of configurations that may be needed for device creation, depending on the system. Currently, this is required for ACPI devices on ARM64.

### -param DmaDeviceOut

[*Out*] A pointer to the opaque token representing the created **IOMMU_DMA_DEVICE**.

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
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The provided PDO represents a device that is not behind an IOMMU.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER_2</b></dt>
</dl>
</td>
<td width="60%">
The provided inputs do not match system support.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
The routine failed to allocate resources required for an **IOMMU_DMA_DEVICE** structure.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_UNSUCCESSFUL</b></dt>
</dl>
</td>
<td width="60%">
The underlying IOMMU Interface is not correctly implemented for the `GetDeviceId` function.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NOT_FOUND</b></dt>
</dl>
</td>
<td width="60%">
The provided PDO represents a device that is not behind an IOMMU.

If the device is not found behind an IOMMU then it should already have direct physical memory access and the platform is not DMA Guard compliant.

</td>
</tr>
</table>

For more information, see [NTSTATUS Values](/windows-hardware/drivers/kernel/ntstatus-values).

## -remarks

ACPI devices on ARM64 systems must provide input mappings through the `DeviceConfig` parameter. All other device types on ARM64 systems and any device on non-ARM64 systems should **NOT** provide any device configurations; otherwise, the call will fail on **STATUS_INVALID_PARAMETER_2**.

## -see-also

[**IOMMU_DEVICE_CREATION_CONFIGURATION**](ns-wdm-iommu_device_creation_configuration.md)

[**IOMMU_DEVICE_DELETE**](nc-wdm-iommu_device_delete.md)

[**DMA_IOMMU_INTERFACE_V2**](ns-wdm-dma_iommu_interface_v2.md)

[**DMA_IOMMU_INTERFACE_EX**](ns-wdm-dma_iommu_interface_ex.md)
