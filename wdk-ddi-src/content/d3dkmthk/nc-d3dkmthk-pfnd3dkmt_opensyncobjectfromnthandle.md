---
UID: NC:d3dkmthk.PFND3DKMT_OPENSYNCOBJECTFROMNTHANDLE
title: PFND3DKMT_OPENSYNCOBJECTFROMNTHANDLE (d3dkmthk.h)
description: The PFND3DKMT_OPENSYNCOBJECTFROMNTHANDLE callback function maps an NT process handle to a graphics processing unit (GPU) synchronization object.
ms.assetid: c50784ef-67bb-410e-8d67-0592cc3a980c
ms.date: 10/19/2018
keywords: ["PFND3DKMT_OPENSYNCOBJECTFROMNTHANDLE callback function"]
f1_keywords:
 - "d3dkmthk/PFND3DKMT_OPENSYNCOBJECTFROMNTHANDLE"
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
- apiref
api_type: 
- UserDefined
api_location: 
- d3dkmthk.h
api_name: 
- PFND3DKMT_OPENSYNCOBJECTFROMNTHANDLE
product:
- Windows
targetos: Windows
ms.custom: RS5
dev_langs:
 - c++
tech.root: display
---

# PFND3DKMT_OPENSYNCOBJECTFROMNTHANDLE callback function

## -description

The PFND3DKMT_OPENSYNCOBJECTFROMNTHANDLE callback function maps an NT process handle to a graphics processing unit (GPU) synchronization object.

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

## -parameters

### -param Arg1

Pointer to a [D3DKMT_OPENSYNCOBJECTFROMNTHANDLE](ns-d3dkmthk-_d3dkmt_opensyncobjectfromnthandle.md) structure.

## -returns

Returns NTSTATUS.


## -remarks




## -see-also
