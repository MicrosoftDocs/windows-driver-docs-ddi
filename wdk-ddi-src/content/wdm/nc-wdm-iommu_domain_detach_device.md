---
UID: NC:wdm.IOMMU_DOMAIN_DETACH_DEVICE
title: IOMMU_DOMAIN_DETACH_DEVICE
author: windows-driver-content
description: Detaches a device from an existing domain. 
ms.assetid: 57f3e503-dd8d-487c-87b7-a0f9f0b126dc
ms.date: 
ms.topic: callback
req.header: wdm.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 1803
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
topictype: 
-	apiref
apitype: 
-	UserDefined
apilocation: 
-	wdm.h
apiname: 
-	IOMMU_DOMAIN_DETACH_DEVICE
product:
-	Windows
targetos: Windows
---

# IOMMU_DOMAIN_DETACH_DEVICE callback function

## -description

Detaches a device from an existing domain. 

## -prototype

```cpp
//Declaration

IOMMU_DOMAIN_DETACH_DEVICE IommuDomainDetachDevice; 

// Definition

NTSTATUS IommuDomainDetachDevice 
(
	PIOMMU_DMA_DOMAIN Domain
	PDEVICE_OBJECT PhysicalDeviceObject
	ULONG InputMappingId
)
{...}

IOMMU_DOMAIN_DETACH_DEVICE *PIOMMU_DOMAIN_DETACH_DEVICE


```

## -parameters

### -param Domain
[_In_] A pointer to the handle to the domain.

### -param PhysicalDeviceObject
[_In_] A pointer the physical device object (PDO) in the device stack of the device.

### -param InputMappingId
[_In_] The input mapping for the device's desired stream.


## -returns

Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate NTSTATUS Values error code. For more information, see [NTSTATUS Values](https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values).

## -remarks

It is driver's responsibility to ensure that this function is not called concurrently with IOMMU_DOMAIN_ATTACH_DEVICE or IOMMU_SET_DEVICE_FAULT_REPORTING calls on the same device.


InputMappingId is used only for ACPI-enumerated devices on ARM64. For all other cases, this value must be zero.

If multiple devices are simultaneously attached using the _MappingCount_ value specified in the [_IOMMU_DOMAIN_ATTACH_DEVICE_](nc-wdm-iommu_domain_attach_device.md) call, then those devices can only be detached as a group by specifying an _InputMappingId_ value that is equal to the _InputMappingIdBase_ value of [_IOMMU_DOMAIN_ATTACH_DEVICE_] used when attaching.


## -see-also
