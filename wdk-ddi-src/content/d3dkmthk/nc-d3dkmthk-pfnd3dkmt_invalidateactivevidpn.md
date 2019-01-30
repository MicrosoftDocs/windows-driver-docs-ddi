---
UID: NC:d3dkmthk.PFND3DKMT_INVALIDATEACTIVEVIDPN
title: PFND3DKMT_INVALIDATEACTIVEVIDPN (d3dkmthk.h)
description: Pfnd3dkmtInvalidateactivevidpn invalidates the active video present network (VidPN) currently in use.
ms.assetid: 9f286769-6655-46ef-93bc-5b9e0337c724
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
-	PFND3DKMT_INVALIDATEACTIVEVIDPN
product:
-	Windows
targetos: Windows
ms.custom: RS5
tech.root: display
---

# PFND3DKMT_INVALIDATEACTIVEVIDPN callback function

## -description

Pfnd3dkmtInvalidateactivevidpn invalidates the active video present network (VidPN) currently in use.

## -prototype

```cpp
//Declaration

PFND3DKMT_INVALIDATEACTIVEVIDPN Pfnd3dkmtInvalidateactivevidpn; 

// Definition

NTSTATUS Pfnd3dkmtInvalidateactivevidpn 
(
	const D3DKMT_INVALIDATEACTIVEVIDPN *
)
{...}

```

## -parameters

### -param * 

Pointer to a [D3DKMT_INVALIDATEACTIVEVIDPN](ns-d3dkmthk-_d3dkmt_invalidateactivevidpn.md) structure.

## -returns

Returns NTSTATUS.


## -remarks




## -see-also
