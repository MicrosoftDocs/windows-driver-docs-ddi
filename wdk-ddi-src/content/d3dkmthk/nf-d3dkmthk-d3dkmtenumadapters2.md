---
UID: NF:d3dkmthk.D3DKMTEnumAdapters2
title: D3DKMTEnumAdapters2 function (d3dkmthk.h)
description: Supplies information for enumerating all graphics adapters on the system.
ms.assetid: 9db2a84b-4aac-48df-81f6-4cb681b3c7f4
ms.date: 11/21/2018
ms.topic: function
ms.keywords: D3DKMTEnumAdapters2
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
-	apiref
api_type: 
-	DllExport
api_location: 
-	Gdi32.dll
api_name: 
-	D3DKMTEnumAdapters2
product:
-	Windows
targetos: Windows
tech.root: display
req.typenames: D3DKMTEnumAdapters2
ms.custom: RS5
---

# D3DKMTEnumAdapters2 function


## -description

Supplies information for enumerating all graphics and display adapters on the system.

## -parameters

### -param Arg1
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
These handles are returned to the callee through pEnumAdapters, and they must be closed with [D3DKMTCloseAdapter](nf-d3dkmthk-d3dkmtcloseadapter.md).

## -see-also
- [D3DKMT_ENUMADAPTERS2](ns-d3dkmthk-_d3dkmt_enumadapters2.md)
- [PFND3DKMT_ENUMADAPTERS2](nc-d3dkmthk-pfnd3dkmt_enumadapters2.md)
- [D3DKMTCloseAdapter](nf-d3dkmthk-d3dkmtcloseadapter.md)
