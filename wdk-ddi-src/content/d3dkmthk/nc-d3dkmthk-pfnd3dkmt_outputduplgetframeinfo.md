---
UID: NC:d3dkmthk.PFND3DKMT_OUTPUTDUPLGETFRAMEINFO
title: PFND3DKMT_OUTPUTDUPLGETFRAMEINFO (d3dkmthk.h)
description: The PFND3DKMT_OUTPUTDUPLGETFRAMEINFO callback function gets output duplicate frame info.
ms.date: 10/19/2018
keywords: ["PFND3DKMT_OUTPUTDUPLGETFRAMEINFO callback function"]
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
 - PFND3DKMT_OUTPUTDUPLGETFRAMEINFO
 - d3dkmthk/PFND3DKMT_OUTPUTDUPLGETFRAMEINFO
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3dkmthk.h
api_name:
 - PFND3DKMT_OUTPUTDUPLGETFRAMEINFO
dev_langs:
 - c++
---

# PFND3DKMT_OUTPUTDUPLGETFRAMEINFO callback function


## -description

The PFND3DKMT_OUTPUTDUPLGETFRAMEINFO callback function gets output duplicate frame info.

## -parameters

### -param Arg1

Pointer to a [D3DKMT_OUTPUTDUPL_GET_FRAMEINFO](ns-d3dkmthk-_d3dkmt_outputdupl_get_frameinfo.md) structure.

## -returns

Returns NTSTATUS.

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

## -remarks

## -see-also

