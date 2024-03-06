---
UID: NC:wdm.PGET_COMMON_BUFFER_FROM_VECTOR_BY_INDEX
title: PGET_COMMON_BUFFER_FROM_VECTOR_BY_INDEX (wdm.h)
description: Describes the PGET_COMMON_BUFFER_FROM_VECTOR_BY_INDEX callback function.
tech.root: kernel
ms.date: 01/19/2023
keywords: ["PGET_COMMON_BUFFER_FROM_VECTOR_BY_INDEX callback function"]
req.header: wdm.h
req.include-header: Wdm.h
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
---

## -description

Describes the PGET_COMMON_BUFFER_FROM_VECTOR_BY_INDEX callback function.

## -parameters

### -param DmaAdapter

Defines the **PDMA_ADAPTER** parameter DmaAdapter.

### -param Vector

Defines the **PDMA_COMMON_BUFFER_VECTOR** parameter Vector.

### -param Index

Defines the **ULONG** parameter Index.

### -param VirtualAddressOut

Defines the **PVOID** parameter VirtualAddressOut.

### -param LogicalAddressOut

Defines the **PPHYSICAL_ADDRESS** parameter LogicalAddressOut.

## -remarks

## -see-also
