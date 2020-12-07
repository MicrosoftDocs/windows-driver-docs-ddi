---
UID: NC:d3dkmthk.PFND3DKMT_OPENSYNCOBJECTFROMNTHANDLE
title: PFND3DKMT_OPENSYNCOBJECTFROMNTHANDLE (d3dkmthk.h)
description: The PFND3DKMT_OPENSYNCOBJECTFROMNTHANDLE callback function maps an NT process handle to a graphics processing unit (GPU) synchronization object.
ms.date: 10/19/2018
keywords: ["PFND3DKMT_OPENSYNCOBJECTFROMNTHANDLE callback function"]
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
targetos: Windows
ms.custom: RS5
tech.root: display
f1_keywords:
 - PFND3DKMT_OPENSYNCOBJECTFROMNTHANDLE
 - d3dkmthk/PFND3DKMT_OPENSYNCOBJECTFROMNTHANDLE
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3dkmthk.h
api_name:
 - PFND3DKMT_OPENSYNCOBJECTFROMNTHANDLE
dev_langs:
 - c++
---

# PFND3DKMT_OPENSYNCOBJECTFROMNTHANDLE callback function


## -description

The PFND3DKMT_OPENSYNCOBJECTFROMNTHANDLE callback function maps an NT process handle to a graphics processing unit (GPU) synchronization object.

## -parameters

### -param Arg1

Pointer to a [D3DKMT_OPENSYNCOBJECTFROMNTHANDLE](ns-d3dkmthk-_d3dkmt_opensyncobjectfromnthandle.md) structure.

## -returns

Returns NTSTATUS.

## -prototype

```cpp
//Declaration

PFND3DKMT_OPENSYNCOBJECTFROMNTHANDLE Pfnd3dkmtOpensyncobjectfromnthandle; 

// Definition

NTSTATUS Pfnd3dkmtOpensyncobjectfromnthandle 
(
	D3DKMT_OPENSYNCOBJECTFROMNTHANDLE *
)
{...}

```

## -remarks

## -see-also

