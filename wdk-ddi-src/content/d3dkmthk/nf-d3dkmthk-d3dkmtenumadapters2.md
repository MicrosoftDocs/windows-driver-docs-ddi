---
UID: NF:d3dkmthk.D3DKMTEnumAdapters2
title: D3DKMTEnumAdapters2 function (d3dkmthk.h)
description: Learn more about the D3DKMTEnumAdapters2 function.
ms.date: 08/30/2022
keywords: ["D3DKMTEnumAdapters2 function"]
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
targetos: Windows
tech.root: display
req.typenames: D3DKMTEnumAdapters2
ms.custom: RS5
f1_keywords:
 - D3DKMTEnumAdapters2
 - d3dkmthk/D3DKMTEnumAdapters2
topic_type:
 - apiref
api_type:
 - DllExport
api_location:
 - Gdi32.dll
api_name:
 - D3DKMTEnumAdapters2
dev_langs:
 - c++
---

# D3DKMTEnumAdapters2 function

## -description

The **D3DKMTEnumAdapters2** function supplies information for enumerating all graphics and display adapters on the system.

## -parameters

### -param unnamedParam1

[in, out] Pointer to a [**D3DKMT_ENUMADAPTERS2**](ns-d3dkmthk-_d3dkmt_enumadapters2.md) structure in which to supply information about adapters on the system. See Remarks.

## -returns

**D3DKMTEnumAdapters2** returns STATUS_SUCCESS upon success or an error such as one of the following.

| Return Code | Description |
| ----------- | ----------- |
| STATUS_BUFFER_TOO_SMALL | The provided array is too small to receive all the adapters. |
| STATUS_INVALID_PARAMETER | **pAdapters** is NULL or is otherwise an invalid memory region. |
| STATUS_NO_MEMORY | Memory cannot be allocated to satisfy the operation. |

## -remarks

On input, [**NumAdapters**](ns-d3dkmthk-_d3dkmt_enumadapters2.md) specifies how many adapters can be returned in the empty array that **pAdapters** points to. On return, if **D3DKMT_ENUMADAPTERS2** returns STATUS_SUCCESS:

* If **pAdapters** is non-NULL, **NumAdapters** will contain the number of adapters returned in the **pAdapters** array.
* If **pAdapters** is NULL, **NumAdapters** will contain the maximum supported adapter count.

If **D3DKMT_ENUMADAPTERS2** returns an error, **NumAdapters** is undefined.

**D3DKMTEnumAdapters2** is typically called twice:

* For the first call, set **pAdapters** to NULL. **D3DKMTEnumAdapters2** will write the maximum supported adapter count in [**NumAdapters**](ns-d3dkmthk-_d3dkmt_enumadapters2.md).

* For the second call, set **NumAdapters** to the value returned in the first call and set **pAdapters** to point to an array of **NumAdapters** [**D3DKMT_ENUMADAPTERS2**](ns-d3dkmthk-_d3dkmt_enumadapters2.md) structures. **D3DKMTEnumAdapters2** will fill in the array and pass back the number of array structures (adapters) that it filled.

Once the caller of **D3DKMTEnumAdapters2** has successfully received an enumeration of the adapters, it is the caller's responsibility to manage the lifespan of the adapter D3DKMT_HANDLEs. These handles are returned through **pAdapters**, and they must be closed with [**D3DKMTCloseAdapter**](nf-d3dkmthk-d3dkmtcloseadapter.md).

## -see-also

[**D3DKMT_ENUMADAPTERS2**](ns-d3dkmthk-_d3dkmt_enumadapters2.md)

[**PFND3DKMT_ENUMADAPTERS2**](nc-d3dkmthk-pfnd3dkmt_enumadapters2.md)

[**D3DKMTCloseAdapter**](nf-d3dkmthk-d3dkmtcloseadapter.md)
