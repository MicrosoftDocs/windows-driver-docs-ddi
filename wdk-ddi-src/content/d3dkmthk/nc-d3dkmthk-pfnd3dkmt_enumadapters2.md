---
UID: NC:d3dkmthk.PFND3DKMT_ENUMADAPTERS2
title: PFND3DKMT_ENUMADAPTERS2 (d3dkmthk.h)
description: The PFND3DKMT_ENUMADAPTERS2 callback function enumerates all graphics adapters on the system.
ms.assetid: 06879518-8a38-4b70-ae9c-25fb4ed35c70
ms.date: 11/21/2018
ms.topic: callback
f1_keywords:
 - "d3dkmthk/PFND3DKMT_ENUMADAPTERS2"
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
- PFND3DKMT_ENUMADAPTERS2
product:
- Windows
targetos: Windows
ms.custom: RS5
tech.root: display
---

# PFND3DKMT_ENUMADAPTERS2 callback function

## -description

The PFND3DKMT_ENUMADAPTERS2 callback function enumerates all graphics and display adapters on the system.

## -prototype

```cpp
//Declaration

PFND3DKMT_ENUMADAPTERS2 Pfnd3dkmtEnumadapters2; 

// Definition

NTSTATUS Pfnd3dkmtEnumadapters2 
(
	const D3DKMT_ENUMADAPTERS2 *
)
{...}

```

## -parameters

### -param *
*\_Inout\_* *[D3DKMT_ENUMADAPTERS2](ns-d3dkmthk-_d3dkmt_enumadapters2.md)* * *Arg1*

Caller passes in array size and empty array space.
Callee verifies enough room in the array, fills out array, and passes back how much of the array was used.

## -returns
This function returns NTSTATUS.

Return Code | Description
--- | ---
STATUS_BUFFER_TOO_SMALL | When the provided array is too small to receive all the adapters.
STATUS_INVALID_PARAMETER | When pEnumAdapters is null or is otherwise an invalid memory region.
STATUS_NO_MEMORY | When memory cannot be allocated to satisfy the operation.

## -remarks
When D3DKMT_ENUMADAPTERS2\::pAdapters is null, D3DKMT_ENUMADAPTERS2\::NumAdapters is set to the maximum supported adapter count.
Callees will commonly invoke the method, first, to retrieve the maximum supported adapter count.

When the callee successfully enumerates adapters, it becomes responsible for explicitly managing the lifespan of adapter D3DKMT_HANDLEs.
These handles are returned to the callee through pEnumAdapters, and must be closed with [D3DKMTCloseAdapter](nf-d3dkmthk-d3dkmtcloseadapter.md).

## -see-also
- [D3DKMT_ENUMADAPTERS2](ns-d3dkmthk-_d3dkmt_enumadapters2.md)
- [D3DKMTEnumAdapters2](nf-d3dkmthk-d3dkmtenumadapters2.md)
- [PFND3DKMT_CLOSEADAPTER](nc-d3dkmthk-pfnd3dkmt_closeadapter.md)
