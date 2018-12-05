---
UID: NC:d3dkmthk.PFND3DKMT_OPENSYNCOBJECTNTHANDLEFROMNAME
title: PFND3DKMT_OPENSYNCOBJECTNTHANDLEFROMNAME
author: windows-driver-content
description: The PFND3DKMT_OPENSYNCOBJECTNTHANDLEFROMNAME callback function opens an NT handle for a named shared monitored fence object, similar to what D3DKMTOpenNtHandleFromName does for shared allocations.
ms.assetid: c7fe8045-ff2e-4cfc-a909-b2fae49e0eb4
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
-	PFND3DKMT_OPENSYNCOBJECTNTHANDLEFROMNAME
product:
-	Windows
targetos: Windows
ms.custom: RS5
tech.root: display
---

# PFND3DKMT_OPENSYNCOBJECTNTHANDLEFROMNAME callback function

## -description

The PFND3DKMT_OPENSYNCOBJECTNTHANDLEFROMNAME callback function opens an NT handle for a named shared monitored fence object, similar to what D3DKMTOpenNtHandleFromName does for shared allocations.

## -prototype

```cpp
//Declaration

PFND3DKMT_OPENSYNCOBJECTNTHANDLEFROMNAME Pfnd3dkmtOpensyncobjectnthandlefromname; 

// Definition

NTSTATUS Pfnd3dkmtOpensyncobjectnthandlefromname 
(
	D3DKMT_OPENSYNCOBJECTNTHANDLEFROMNAME *
)
{...}

```

## -parameters

### -param * 

Pointer to a [D3DKMT_OPENSYNCOBJECTNTHANDLEFROMNAME](ns-d3dkmthk-_d3dkmt_opensyncobjectnthandlefromname.md) structure.

## -returns

Returns NTSTATUS.


## -remarks




## -see-also
