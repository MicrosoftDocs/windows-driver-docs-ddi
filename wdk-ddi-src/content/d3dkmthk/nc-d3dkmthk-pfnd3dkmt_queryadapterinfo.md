---
UID: NC:d3dkmthk.PFND3DKMT_QUERYADAPTERINFO
title: PFND3DKMT_QUERYADAPTERINFO (d3dkmthk.h)
description: The PFND3DKMT_QUERYADAPTERINFO callback function retrieves graphics adapter information.
ms.assetid: fc4f4324-cb20-49ae-8f1c-3aa8e75d3d9a
ms.date: 11/21/2018
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
 - "d3dkmthk/PFND3DKMT_QUERYADAPTERINFO"
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3dkmthk.h
api_name:
 - PFND3DKMT_QUERYADAPTERINFO
product:
 - Windows
dev_langs:
 - c++
---

# PFND3DKMT_QUERYADAPTERINFO callback function

## -description

The PFND3DKMT_QUERYADAPTERINFO callback function retrieves various adapter information from an adapter handle.

## -parameters

### -param Arg1

*\_In\_* *[D3DKMT_QUERYADAPTERINFO](ns-d3dkmthk-_d3dkmt_queryadapterinfo.md)* * *Arg1*

See documentation of structure type for more details.

## -returns

Returns NTSTATUS.

Return Code | Description
--- | ---
**STATUS_SUCCESS** | Adapter information was successfully retrieved.
**STATUS_DEVICE_REMOVED** | The adapter was stopped.
**STATUS_INVALID_PARAMETER** | Parameters were validated and determined to be incorrect.
**STATUS_NO_MEMORY** | Not enough memory could be allocated to satisfy the operation.

This function might also return other NTSTATUS values.

## -prototype

```cpp
//Declaration

PFND3DKMT_QUERYADAPTERINFO Pfnd3dkmtQueryadapterinfo; 

// Definition

NTSTATUS Pfnd3dkmtQueryadapterinfo 
(
	const D3DKMT_QUERYADAPTERINFO *
)
{...}

```

## -remarks

## -see-also

- [D3DKMT_QUERYADAPTERINFO](ns-d3dkmthk-_d3dkmt_queryadapterinfo.md)
- [D3DKMTQueryAdapterInfo](nf-d3dkmthk-d3dkmtqueryadapterinfo.md)

