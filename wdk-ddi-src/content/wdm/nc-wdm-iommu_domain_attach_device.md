---
UID: NC:wdm.IOMMU_DOMAIN_ATTACH_DEVICE
title: IOMMU_DOMAIN_ATTACH_DEVICE (wdm.h)
description: Attaches a device to an existing domain.
ms.assetid: 9d1b51df-e599-49e4-8465-ad283e60027a
ms.date: 10/19/2018
keywords: ["IOMMU_DOMAIN_ATTACH_DEVICE callback function"]
f1_keywords:
 - "wdm/IOMMU_DOMAIN_ATTACH_DEVICE"
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
topic_type: 
- apiref
api_type: 
- UserDefined
api_location:
- wdm.h
api_name: 
- IOMMU_DOMAIN_ATTACH_DEVICE
product:
- Windows
targetos: Windows
---

# IOMMU_DOMAIN_ATTACH_DEVICE callback function

## -description

Attaches a device to an existing domain.

## -prototype

```cpp
//Declaration

IOMMU_DOMAIN_ATTACH_DEVICE IommuDomainAttachDevice; 

// Definition

NTSTATUS IommuDomainAttachDevice 
(
	PIOMMU_DMA_DOMAIN Domain
	PDEVICE_OBJECT PhysicalDeviceObject
	ULONG InputMappingIdBase
	ULONG MappingCount
)
{...}

IOMMU_DOMAIN_ATTACH_DEVICE *PIOMMU_DOMAIN_ATTACH_DEVICE


```

## -parameters

### -param Domain
[_In_] A pointer to the handle to the domain.

### -param PhysicalDeviceObject
[_In_] A pointer the physical device object (PDO) in the device stack of the device.

### -param InputMappingIdBase
[_In_] The input mapping base for the device's desired stream.

### -param MappingCount
[_In_] The count of mappings beginning at the base.



## -returns

Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate NTSTATUS Values error code. For more information, see [NTSTATUS Values](https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values).

## -remarks
It is driver's responsibility to ensure that this function is not called concurrently with IOMMU_DOMAIN_DETACH_DEVICE or IOMMU_SET_DEVICE_FAULT_REPORTING calls on the same device.

_InputMappingIdBase_ and _MappingCount_ are intended only to accommodate ACPI-enumerated devices that support multiple stream IDs on ARM64. For any other device or architecture, these values must be:
- InputMappingIdBase = 0
- MappingCount = 1


## -see-also
