---
UID: NC:d3dkmthk.PFND3DKMT_OUTPUTDUPLGETPOINTERSHAPEDATA
title: PFND3DKMT_OUTPUTDUPLGETPOINTERSHAPEDATA (d3dkmthk.h)
description: The PFND3DKMT_OUTPUTDUPLGETPOINTERSHAPEDATA callback function gets output duplicate pointer shape data.
ms.date: 10/19/2018
keywords: ["PFND3DKMT_OUTPUTDUPLGETPOINTERSHAPEDATA callback function"]
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
 - PFND3DKMT_OUTPUTDUPLGETPOINTERSHAPEDATA
 - d3dkmthk/PFND3DKMT_OUTPUTDUPLGETPOINTERSHAPEDATA
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3dkmthk.h
api_name:
 - PFND3DKMT_OUTPUTDUPLGETPOINTERSHAPEDATA
dev_langs:
 - c++
---

# PFND3DKMT_OUTPUTDUPLGETPOINTERSHAPEDATA callback function


## -description

The PFND3DKMT_OUTPUTDUPLGETPOINTERSHAPEDATA callback function gets output duplicate pointer shape data.

## -parameters

### -param Arg1

Pointer to a [D3DKMT_OUTPUTDUPL_GET_POINTER_SHAPE_DATA](ns-d3dkmthk-_d3dkmt_outputdupl_get_pointer_shape_data.md) structure.

## -returns

Returns NTSTATUS.

## -prototype

```cpp
//Declaration

PFND3DKMT_OUTPUTDUPLGETPOINTERSHAPEDATA Pfnd3dkmtOutputduplgetpointershapedata; 

// Definition

NTSTATUS Pfnd3dkmtOutputduplgetpointershapedata 
(
	D3DKMT_OUTPUTDUPL_GET_POINTER_SHAPE_DATA *
)
{...}

```

## -remarks

## -see-also

