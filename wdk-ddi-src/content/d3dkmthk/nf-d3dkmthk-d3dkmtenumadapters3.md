---
UID: NF:d3dkmthk.D3DKMTEnumAdapters3
title: D3DKMTEnumAdapters2 function (d3dkmthk.h)
description: Supplies information for enumerating all graphics adapters on the system.
ms.assetid: 1e17d460-500d-4e4b-92f7-0505acc8436d
ms.date: 03/24/2020
keywords: ["D3DKMTEnumAdapters3 function"]
f1_keywords:
 - "d3dkmthk/D3DKMTEnumAdapters3"
 - "D3DKMTEnumAdapters3"
ms.keywords: D3DKMTEnumAdapters3
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 2004
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib: Gdi32.lib
req.dll: Gdi32.dll
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
- DllExport
api_location: 
- Gdi32.dll
api_name: 
- D3DKMTEnumAdapters2
targetos: Windows
tech.root: display
req.typenames: D3DKMTEnumAdapters3
dev_langs:
 - c++
ms.custom:
---

# D3DKMTEnumAdapters3 function

## -description

Supplies information for enumerating graphics and display adapters on the system.

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

When the callee successfully enumerates adapters, it becomes responsible for explicitly managing the lifespan of adapter D3DKMT_HANDLEs. These handles are returned to the callee through pEnumAdapters, and they must be closed with [**D3DKMTCloseAdapter**](nf-d3dkmthk-d3dkmtcloseadapter.md).

Setting none of the D3DKMT_ENUMADAPTERS3::Filter flags will still enumerate adapters, but there are fewer adapters than [**D3DKMTEnumAdapters2**](nf-d3dkmthk-d3dkmtenumadapters2.md) enumerates. ComputeOnly adapters are left out of the default enumeration, to avoid breaking applications. DisplayOnly adapters are also left out of the default enumeration.

## -see-also

[**D3DKMT_ENUMADAPTERS3**](ns-d3dkmthk-_d3dkmt_enumadapters3.md)

[**D3DKMTCloseAdapter**](nf-d3dkmthk-d3dkmtcloseadapter.md)

[**PFND3DKMT_ENUMADAPTERS3**](nc-d3dkmthk-pfnd3dkmt_enumadapters3.md)

[**D3DKMTCloseAdapter**](nf-d3dkmthk-d3dkmtcloseadapter.md)
