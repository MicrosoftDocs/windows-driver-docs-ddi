---
UID: NC:wdm.PFREE_COMMON_BUFFER_VECTOR
title: PFREE_COMMON_BUFFER_VECTOR
description: 
tech.root: 
ms.assetid: 73dfdcdd-d131-44ec-b32e-8c0eaeac33d8
ms.date: 08/19/2019
keywords: ["PFREE_COMMON_BUFFER_VECTOR callback function"]
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
 - PFREE_COMMON_BUFFER_VECTOR
 - wdm/PFREE_COMMON_BUFFER_VECTOR
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
---

# PFREE_COMMON_BUFFER_VECTOR callback function


## -description

Implemented by the client driver to ...

## -parameters

### -param DmaAdapter: 

### -param Vector: 

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

## -remarks

Register your implementation of this callback function by setting the appropriate member of <!-- REPLACE ME --> and then calling <!-- REPLACE ME -->.

## -see-also

