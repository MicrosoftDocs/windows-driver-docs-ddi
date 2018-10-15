---
UID: NC:wdm.IOMMU_QUERY_INPUT_MAPPINGS
title: IOMMU_QUERY_INPUT_MAPPINGS
author: windows-driver-content
description: Attempts to find input mapping IDs which are valid for the given device and populate the provied buffer with those IDs.
ms.assetid: 5664ad95-31b2-4457-9aab-ecf3768eec69
ms.author: windowsdriverdev
ms.date: 
ms.topic: callback
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	IOMMU_QUERY_INPUT_MAPPINGS
product:
-	Windows
targetos: Windows
---

# IOMMU_QUERY_INPUT_MAPPINGS callback function

## -description

Attempts to find input mapping IDs which are valid for the given device and populate the provied buffer with those IDs.

## -prototype

```
//Declaration

IOMMU_QUERY_INPUT_MAPPINGS IommuQueryInputMappings; 

// Definition

NTSTATUS IommuQueryInputMappings 
(
	PDEVICE_OBJECT PhysicalDeviceObject
	PINPUT_MAPPING_ELEMENT Buffer
	ULONG BufferLength
	PULONG ReturnLength
)
{...}

IOMMU_QUERY_INPUT_MAPPINGS *PIOMMU_QUERY_INPUT_MAPPINGS


```

## -parameters

### -param PhysicalDeviceObject
[_In_] A pointer to the physical device object (PDO) in the device stack.

### -param Buffer
[_Inout_] A pointer to the buffer of the type [**INPUT_MAPPING_ELEMENT**](ns-wdm-_input_mapping_element.md) that is populated with the input mapping IDs.
 
### -param BufferLength
[_In_] The length of the buffer pointed to by _Buffer_.
 
### -param ReturnLength: 
[_Out_opt] Optional. A pointer to store the amount of data written (or data that would be written if a buffer of sufficient size was provided).


## -returns

Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate NTSTATUS Values error code. For more information, see [NTSTATUS Values](https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values). Possible values include:

| Error code              | Description                                  |
| ----------------------- | -------------------------------------------- |
| STATUS_BUFFER_TOO_SMALL | The provided buffer is of insufficient size. |
| STATUS_UNSUCCESSFUL     | The request cannot be satisfied.             |
| STATUS_SUCCESS          | The buffer has been populated correctly.     |


## -remarks

If the buffer is of insufficient length, no IDs will be written and ReturnLength (if provided) will be populated with the required buffer size.

This routine is currently only supported on ARM64 systems.


## -see-also