---
UID: NC:wdm.PALLOCATE_COMMON_BUFFER_VECTOR
title: PALLOCATE_COMMON_BUFFER_VECTOR
author: windows-driver-content
description: 
tech.root:
ms.assetid: be2dd87e-6c09-4493-82ef-152dfce0917e
ms.author: windowsdriverdev
ms.date: 08/19/2019
ms.topic: callback
f1_keywords:
 - "wdm/PALLOCATE_COMMON_BUFFER_VECTOR"
req.header: wdm.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
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
 - PALLOCATE_COMMON_BUFFER_VECTOR
product: 
 - Windows
targetos: Windows
ms.custom: 19H1
---

# PALLOCATE_COMMON_BUFFER_VECTOR callback function

## -description

Implemented by the client driver to ... 

## -prototype

```
//Declaration

PALLOCATE_COMMON_BUFFER_VECTOR PallocateCommonBufferVector; 

// Definition

NTSTATUS PallocateCommonBufferVector 
(
	PDMA_ADAPTER DmaAdapter
	PHYSICAL_ADDRESS LowAddress
	PHYSICAL_ADDRESS HighAddress
	MEMORY_CACHING_TYPE CacheType
	ULONG IdealNode
	ULONG Flags
	ULONG NumberOfElements
	ULONGLONG SizeOfElements
	PDMA_COMMON_BUFFER_VECTOR *VectorOut
)
{...}

```

## -parameters

### -param DmaAdapter: 
### -param LowAddress: 
### -param HighAddress: 
### -param CacheType: 
### -param IdealNode: 
### -param Flags: 
### -param NumberOfElements: 
### -param SizeOfElements: 
### -param *VectorOut: 



## -returns

Returns NTSTATUS that ...
Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate NTSTATUS Values error code. For more information, see [NTSTATUS Values](https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/ntstatus-values).

## -remarks

Register your implementation of this callback function by setting the appropriate member of <!-- REPLACE ME --> and then calling <!-- REPLACE ME -->.


## -see-also
