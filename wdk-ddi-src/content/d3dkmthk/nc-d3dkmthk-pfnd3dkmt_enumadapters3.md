---
UID: NC:d3dkmthk.PFND3DKMT_ENUMADAPTERS3
title: PFND3DKMT_ENUMADAPTERS3 (d3dkmthk.h)
description: The PFND3DKMT_ENUMADAPTERS3 callback function enumerates all graphics adapters on the system.
ms.assetid: 5943cc94-cdd6-4d68-8592-43fb9c29487f
ms.date: 03/24/2020
keywords: ["PFND3DKMT_ENUMADAPTERS3 callback function"]
f1_keywords:
 - "d3dkmthk/PFND3DKMT_ENUMADAPTERS3"
 - "PFND3DKMT_ENUMADAPTERS3"
req.header: d3dkmthk.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 2004
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
- PFND3DKMT_ENUMADAPTERS3
product:
- Windows
targetos: Windows
ms.custom:
dev_langs:
 - c++
tech.root: display
---

# PFND3DKMT_ENUMADAPTERS3 callback function

## -description

The **PFND3DKMT_ENUMADAPTERS3** callback function enumerates graphics and display adapters on the system.

## -prototype

```cpp
//Declaration

PFND3DKMT_ENUMADAPTERS3 Pfnd3dkmtEnumadapters3;

// Definition

NTSTATUS Pfnd3dkmtEnumadapters3
(
	const D3DKMT_ENUMADAPTERS3 *Arg1
)
{...}

```

## -parameters

### -param Arg1

[in/out] A [D3DKMT_ENUMADAPTERS3](ns-d3dkmthk-_d3dkmt_enumadapters3.md) structure. The caller passes in the array size and an empty array space. The callee verifies that there is enough room in the array, fills out the array, and passes back how much of the array was used.

## -returns

This function returns NTSTATUS.

Return Code | Description
--- | ---
STATUS_BUFFER_TOO_SMALL | The provided array is too small to receive all the adapters.
STATUS_INVALID_PARAMETER | The pEnumAdapters member is null or is otherwise an invalid memory region.
STATUS_NO_MEMORY | Memory cannot be allocated to satisfy the operation.

## -remarks

When D3DKMT_ENUMADAPTERS3::pAdapters is null, D3DKMT_ENUMADAPTERS3::NumAdapters is set to the maximum supported adapter count. Callees will commonly invoke the method, first, to retrieve the maximum supported adapter count.

When the callee successfully enumerates adapters, it becomes responsible for explicitly managing the lifespan of adapter D3DKMT_HANDLEs. These handles are returned to the callee through **pEnumAdapters**, and must be closed with [**D3DKMTCloseAdapter**](nf-d3dkmthk-d3dkmtcloseadapter.md).

Setting none of the D3DKMT_ENUMADAPTERS3::Filter flags will still enumerate adapters, but there are fewer adapters than [**PFND3DKMT_ENUMADAPTERS2**](nc-d3dkmthk-pfnd3dkmt_enumadapters2.md) enumerates. ComputeOnly adapters are left out of the default enumeration, to avoid breaking applications. DisplayOnly adapters are also left out of the default enumeration.

## -see-also

[**D3DKMT_ENUMADAPTERS3**](ns-d3dkmthk-_d3dkmt_enumadapters3.md)

[**D3DKMTCloseAdapter**](nf-d3dkmthk-d3dkmtcloseadapter.md)

[**D3DKMTEnumAdapters3**](nf-d3dkmthk-d3dkmtenumadapters3.md)

[**PFND3DKMT_CLOSEADAPTER**](nc-d3dkmthk-pfnd3dkmt_closeadapter.md)

[**PFND3DKMT_ENUMADAPTERS2**](nc-d3dkmthk-pfnd3dkmt_enumadapters2.md)
