---
UID: NF:d3dkmthk.D3DKMTQueryAdapterInfo
title: D3DKMTQueryAdapterInfo function (d3dkmthk.h)
description: Learn more about the D3DKMTQueryAdapterInfo function.
ms.date: 02/03/2025
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Universal
req.target-min-winverclnt: Windows Vista (WDDM 1.0)
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Gdi32.lib
req.dll: Gdi32.dll
req.irql: 
targetos: Windows
tech.root: display
req.typenames: 
f1_keywords:
 - D3DKMTQueryAdapterInfo
 - d3dkmthk/D3DKMTQueryAdapterInfo
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Gdi32.dll
 - API-MS-Win-dx-d3dkmt-l1-1-0.dll
 - API-MS-Win-dx-d3dkmt-l1-1-1.dll
 - API-MS-Win-DX-D3DKMT-L1-1-2.dll
api_name:
 - D3DKMTQueryAdapterInfo
---

# D3DKMTQueryAdapterInfo function

## -description

The **D3DKMTQueryAdapterInfo** function retrieves adapter information from an adapter handle.

## -parameters

### -param unnamedParam1 [in/out]

Pointer to a [**D3DKMT_QUERYADAPTERINFO**](ns-d3dkmthk-_d3dkmt_queryadapterinfo.md) structure that describes the adapter information to retrieve.

## -returns

**D3DKMTQueryAdapterInfo** returns an NTSTATUS code such as one of the following:

| Return code | Description |
|--|--|
| STATUS_SUCCESS | Adapter information was successfully retrieved. |
| STATUS_DEVICE_REMOVED | The adapter was stopped. |
| STATUS_INVALID_PARAMETER | Parameters were validated and determined to be incorrect. |
| STATUS_NO_MEMORY | **D3DKMTQueryAdapterInfo** couldn't complete because of insufficient memory. |

## -see-also

[**D3DKMT_QUERYADAPTERINFO**](ns-d3dkmthk-_d3dkmt_queryadapterinfo.md)

[**PFND3DKMT_QUERYADAPTERINFO**](nc-d3dkmthk-pfnd3dkmt_queryadapterinfo.md)
