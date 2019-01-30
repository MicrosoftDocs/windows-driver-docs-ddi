---
UID: NC:d3dkmthk.PFND3DKMT_OPENSYNCOBJECTFROMNTHANDLE2
title: PFND3DKMT_OPENSYNCOBJECTFROMNTHANDLE2 (d3dkmthk.h)
description: The PFND3DKMT_OPENSYNCOBJECTFROMNTHANDLE2 callback function maps an NT process handle to a graphics processing unit (GPU) synchronization object.
ms.assetid: 4ca41a3c-3bd5-4964-8299-72c78b0df435
ms.date: 10/19/2018
ms.topic: callback
req.header: d3dkmthk.h
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
-	apiref
api_type: 
-	UserDefined
api_location: 
-	d3dkmthk.h
api_name: 
-	PFND3DKMT_OPENSYNCOBJECTFROMNTHANDLE2
product:
-	Windows
targetos: Windows
ms.custom: RS5
tech.root: display
---

# PFND3DKMT_OPENSYNCOBJECTFROMNTHANDLE2 callback function

## -description

The PFND3DKMT_OPENSYNCOBJECTFROMNTHANDLE2 callback function maps an NT process handle to a graphics processing unit (GPU) synchronization object.

## -prototype

```cpp
//Declaration

PFND3DKMT_OPENSYNCOBJECTFROMNTHANDLE2 Pfnd3dkmtOpensyncobjectfromnthandle2; 

// Definition

NTSTATUS Pfnd3dkmtOpensyncobjectfromnthandle2 
(
	D3DKMT_OPENSYNCOBJECTFROMNTHANDLE2 *
)
{...}

```

## -parameters

### -param * 

Pointer to a [D3DKMT_OPENSYNCOBJECTFROMNTHANDLE2](ns-d3dkmthk-_d3dkmt_opensyncobjectfromnthandle2.md) structure.

## -returns

Returns NTSTATUS.


## -remarks




## -see-also
