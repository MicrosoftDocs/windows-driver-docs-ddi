---
UID: NC:wdm.PFREE_COMMON_BUFFER_VECTOR
title: PFREE_COMMON_BUFFER_VECTOR
author: windows-driver-content
description: 
tech.root:
ms.assetid: 73dfdcdd-d131-44ec-b32e-8c0eaeac33d8
ms.author: windowsdriverdev
ms.date: 
ms.topic: callback
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
 - PFREE_COMMON_BUFFER_VECTOR
product: 
 - Windows
targetos: Windows
ms.custom: 19H1
---

# PFREE_COMMON_BUFFER_VECTOR callback function

## -description

Implemented by the client driver to ... 

## -prototype

```
//Declaration

PFREE_COMMON_BUFFER_VECTOR PfreeCommonBufferVector; 

// Definition

VOID PfreeCommonBufferVector 
(
	PDMA_ADAPTER DmaAdapter
	PDMA_COMMON_BUFFER_VECTOR Vector
)
{...}

```

## -parameters

### -param DmaAdapter: 
### -param Vector: 



## -returns

Returns VOID that ...

## -remarks

Register your implementation of this callback function by setting the appropriate member of <!-- REPLACE ME --> and then calling <!-- REPLACE ME -->.


## -see-also
