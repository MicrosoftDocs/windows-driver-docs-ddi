---
UID: NC:d3dkmthk.PFND3DKMT_OUTPUTDUPLGETFRAMEINFO
title: PFND3DKMT_OUTPUTDUPLGETFRAMEINFO
description: The PFND3DKMT_OUTPUTDUPLGETFRAMEINFO callback function gets output duplicate frame info.
ms.assetid: a4f73b4b-cfc5-4fa6-b597-9309a1dce8d2
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
-	PFND3DKMT_OUTPUTDUPLGETFRAMEINFO
product:
-	Windows
targetos: Windows
ms.custom: RS5
tech.root: display
---

# PFND3DKMT_OUTPUTDUPLGETFRAMEINFO callback function

## -description

The PFND3DKMT_OUTPUTDUPLGETFRAMEINFO callback function gets output duplicate frame info.

## -prototype

```cpp
//Declaration

PFND3DKMT_OUTPUTDUPLGETFRAMEINFO Pfnd3dkmtOutputduplgetframeinfo; 

// Definition

NTSTATUS Pfnd3dkmtOutputduplgetframeinfo 
(
	D3DKMT_OUTPUTDUPL_GET_FRAMEINFO *
)
{...}

```

## -parameters

### -param * 

Pointer to a [D3DKMT_OUTPUTDUPL_GET_FRAMEINFO](ns-d3dkmthk-_d3dkmt_outputdupl_get_frameinfo.md) structure.

## -returns

Returns NTSTATUS.


## -remarks




## -see-also
