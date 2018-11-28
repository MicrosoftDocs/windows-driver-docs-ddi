---
UID: NC:wdm.IOMMU_SET_DEVICE_FAULT_REPORTING
title: IOMMU_SET_DEVICE_FAULT_REPORTING
author: windows-driver-content
description: This routine sets the device fault reporting state to a device already attached to a domain.
ms.assetid: 111049ce-9f18-4807-a6c2-5641b115a4b5
ms.date: 09/30/2018
ms.topic: callback
req.header: wdm.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 1809.
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
topic_type: 
-	apiref
api_type: 
-	UserDefined
api_location: 
-	wdm.h
api_name: 
-	IOMMU_SET_DEVICE_FAULT_REPORTING
product: Windows
targetos: Windows
ms.custom: RS5
---

# IOMMU_SET_DEVICE_FAULT_REPORTING callback function

## -description

This routine sets the device fault reporting state to a device already attached to a domain.
> It is driver's responsibility to ensure that this function is not called concurrently with any [**IommuDomainAttachDevice**](nc-wdm-iommu_domain_attach_device.md) or [**IommuDomainDetachDevice**](nc-wdm-iommu_domain_detach_device.md) calls on the same device.

## -prototype

```cpp
//Declaration

IOMMU_SET_DEVICE_FAULT_REPORTING IommuSetDeviceFaultReporting; 

// Definition

NTSTATUS IommuSetDeviceFaultReporting 
(
	PDEVICE_OBJECT PhysicalDeviceObject
	ULONG InputMappingIdBase
	BOOLEAN Enable
	PDEVICE_FAULT_CONFIGURATION FaultConfig
)
{...}

```

## -parameters

### -param PhysicalDeviceObject
[In] A pointer the physical device object (PDO) in the device stack of the device.

### -param InputMappingIdBase
[In] The input mapping base for the device's desired stream.

### -param Enable
[In] a BOOLEAN value that indicates whether to enable fault reporting for the device.

### -param FaultConfig
[in] Optional.  A pointer to [**DEVICE_FAULT_CONFIGURATION**](ns-wdm-_device_fault_configuration.md). This is only used for enabling fault reporting.


## -returns

Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate NTSTATUS Values error code. For more information, see [NTSTATUS Values](https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values).

## -remarks

Register your implementation of this callback function by setting **SetDeviceFaultReporting** of [_DMA_IOMMU_INTERFACE](ns-wdm-_dma_iommu_interface.md).


## -see-also
