---
UID: NC:d3dkmthk.PFND3DKMT_OUTPUTDUPLGETPOINTERSHAPEDATA
title: PFND3DKMT_OUTPUTDUPLGETPOINTERSHAPEDATA
author: windows-driver-content
description: The PFND3DKMT_OUTPUTDUPLGETPOINTERSHAPEDATA callback function gets output duplicate pointer shape data.
ms.assetid: 0c69e0f9-143e-4254-897f-a27a7562cda7
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
-	PFND3DKMT_OUTPUTDUPLGETPOINTERSHAPEDATA
product:
-	Windows
targetos: Windows
---

# PFND3DKMT_OUTPUTDUPLGETPOINTERSHAPEDATA callback function

## -description

The PFND3DKMT_OUTPUTDUPLGETPOINTERSHAPEDATA callback function gets output duplicate pointer shape data.

## -prototype

```
//Declaration

PFND3DKMT_OUTPUTDUPLGETPOINTERSHAPEDATA Pfnd3dkmtOutputduplgetpointershapedata; 

// Definition

NTSTATUS Pfnd3dkmtOutputduplgetpointershapedata 
(
	D3DKMT_OUTPUTDUPL_GET_POINTER_SHAPE_DATA *
)
{...}

```

## -parameters

### -param * 

Pointer to a [D3DKMT_OUTPUTDUPL_GET_POINTER_SHAPE_DATA](ns-d3dkmthk-_d3dkmt_outputdupl_get_pointer_shape_data.md) structure.

## -returns

Returns NTSTATUS.


## -remarks




## -see-also
