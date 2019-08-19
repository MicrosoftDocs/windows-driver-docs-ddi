---
UID: NC:wdm.PFREE_COMMON_BUFFER_FROM_VECTOR
title: PFREE_COMMON_BUFFER_FROM_VECTOR
author: windows-driver-content
description: 
tech.root:
ms.assetid: 739dda10-91e5-4844-9468-0e9196b7e25d
ms.author: windowsdriverdev
ms.date: 08/19/2019
ms.topic: callback
f1_keywords:
 - "wdm/PFREE_COMMON_BUFFER_FROM_VECTOR"
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
 - PFREE_COMMON_BUFFER_FROM_VECTOR
product: 
 - Windows
targetos: Windows
ms.custom: 19H1
---

# PFREE_COMMON_BUFFER_FROM_VECTOR callback function

## -description

Implemented by the client driver to ... 

## -prototype

```
//Declaration

PFREE_COMMON_BUFFER_FROM_VECTOR PfreeCommonBufferFromVector; 

// Definition

VOID PfreeCommonBufferFromVector 
(
	PDMA_ADAPTER DmaAdapter
	PDMA_COMMON_BUFFER_VECTOR Vector
	ULONG Index
)
{...}

```

## -parameters

### -param DmaAdapter: 
### -param Vector: 
### -param Index: 



## -returns

Returns VOID that ...

## -remarks

Register your implementation of this callback function by setting the appropriate member of <!-- REPLACE ME --> and then calling <!-- REPLACE ME -->.


## -see-also
