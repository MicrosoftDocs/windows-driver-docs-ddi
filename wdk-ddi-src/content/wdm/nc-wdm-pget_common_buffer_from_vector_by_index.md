---
UID: NC:wdm.PGET_COMMON_BUFFER_FROM_VECTOR_BY_INDEX
title: PGET_COMMON_BUFFER_FROM_VECTOR_BY_INDEX
description: 
tech.root: 
ms.assetid: 7dcb7dd4-8d35-4715-806a-3886fe484366
ms.author: windowsdriverdev
ms.date: 08/19/2019
keywords: ["PGET_COMMON_BUFFER_FROM_VECTOR_BY_INDEX callback function"]
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
targetos: Windows
ms.custom: 19H1
f1_keywords:
 - PGET_COMMON_BUFFER_FROM_VECTOR_BY_INDEX
 - wdm/PGET_COMMON_BUFFER_FROM_VECTOR_BY_INDEX
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - wdm.h
api_name:
 - PGET_COMMON_BUFFER_FROM_VECTOR_BY_INDEX
product:
 - Windows
---

# PGET_COMMON_BUFFER_FROM_VECTOR_BY_INDEX callback function


## -description

Implemented by the client driver to ...

## -parameters

### -param DmaAdapter: 

### -param Vector: 

### -param Index: 

### -param VirtualAddressOut: 

### -param LogicalAddressOut: 

## -prototype

```
//Declaration

PGET_COMMON_BUFFER_FROM_VECTOR_BY_INDEX PgetCommonBufferFromVectorByIndex; 

// Definition

VOID PgetCommonBufferFromVectorByIndex 
(
	PDMA_ADAPTER DmaAdapter
	PDMA_COMMON_BUFFER_VECTOR Vector
	ULONG Index
	PVOID *VirtualAddressOut
	PPHYSICAL_ADDRESS LogicalAddressOut
)
{...}

```

## -remarks

Register your implementation of this callback function by setting the appropriate member of <!-- REPLACE ME --> and then calling <!-- REPLACE ME -->.

## -see-also

