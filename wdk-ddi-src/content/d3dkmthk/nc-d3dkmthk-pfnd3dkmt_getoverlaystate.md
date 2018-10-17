---
UID: NC:d3dkmthk.PFND3DKMT_GETOVERLAYSTATE
title: PFND3DKMT_GETOVERLAYSTATE
author: windows-driver-content
description: Pfnd3dkmtGetoverlaystate retrieves the status about an overlay.
ms.assetid: 0cad9f03-12b6-4039-9a8a-db420644288b
ms.date: 
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
-	PFND3DKMT_GETOVERLAYSTATE
product:
-	Windows
targetos: Windows
---

# PFND3DKMT_GETOVERLAYSTATE callback function

## -description

Pfnd3dkmtGetoverlaystate retrieves the status about an overlay.

## -prototype

```
//Declaration

PFND3DKMT_GETOVERLAYSTATE Pfnd3dkmtGetoverlaystate; 

// Definition

NTSTATUS Pfnd3dkmtGetoverlaystate 
(
	D3DKMT_GETOVERLAYSTATE *
)
{...}

```

## -parameters

### -param * 

Pointer to a [D3DKMT_GETOVERLAYSTATE](ns-d3dkmthk-_d3dkmt_getoverlaystate.md) structure.

## -returns

Returns NTSTATUS.


## -remarks




## -see-also
