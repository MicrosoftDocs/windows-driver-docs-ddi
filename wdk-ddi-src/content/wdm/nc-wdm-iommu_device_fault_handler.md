---
UID: NC:wdm.IOMMU_DEVICE_FAULT_HANDLER
title: IOMMU_DEVICE_FAULT_HANDLER
description: Reports fault from a specific device and domain.
ms.assetid: 6efa32ef-39c2-43f3-8808-d7649cfc493d
ms.date: 10/19/2018
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
req.irql: PASSIVE_LEVEL
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
-	IOMMU_DEVICE_FAULT_HANDLER
product: Windows
targetos: Windows
ms.custom: RS5
---

# IOMMU_DEVICE_FAULT_HANDLER callback function

## -description

Reports fault from a specific device and domain.

## -prototype

```cpp
//Declaration

IOMMU_DEVICE_FAULT_HANDLER IommuDeviceFaultHandler; 

// Definition

VOID IommuDeviceFaultHandler 
(
	PVOID Context
	PFAULT_INFORMATION FaultInformation
)
{...}

```

## -parameters

### -param Context
A pointer to the opaque driver-supplied fault context.

### -param FaultInformation
A pointer to a [**FAULT_INFORMATION**](ns-wdm-_fault_information.md) structure that contains fault information.


## -returns

.

## -remarks

Register your implementation of this callback function by setting the **FaultHandler** member of [**DEVICE_FAULT_CONFIGURATION**](ns-wdm-_device_fault_configuration.md).


## -see-also
