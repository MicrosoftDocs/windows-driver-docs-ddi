---
UID: NC:d3dkmthk.PFND3DKMT_QUERYADAPTERINFO
title: PFND3DKMT_QUERYADAPTERINFO (d3dkmthk.h)
description: Learn more about the PFND3DKMT_QUERYADAPTERINFO callback function.
ms.date: 02/06/2025
req.header: d3dkmthk.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows Vista (WDDM 1.0)
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
 - PFND3DKMT_QUERYADAPTERINFO
 - d3dkmthk/PFND3DKMT_QUERYADAPTERINFO
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3dkmthk.h
api_name:
 - PFND3DKMT_QUERYADAPTERINFO
dev_langs:
 - c++
---

# PFND3DKMT_QUERYADAPTERINFO callback function

## -description

The **PFND3DKMT_QUERYADAPTERINFO** callback function retrieves adapter information from an adapter handle.

## -parameters

### -param unnamedParam1

[in/out] Pointer to a [**D3DKMT_QUERYADAPTERINFO**](ns-d3dkmthk-_d3dkmt_queryadapterinfo.md) structure in which the adapter information is retrieved.

## -returns

**Pfnd3dkmtQueryadapterinfo** returns an NTSTATUS code such as one of the following:

| Return Code | Description |
| --- | --- |
| STATUS_SUCCESS | Adapter information was successfully retrieved. |
| STATUS_DEVICE_REMOVED | The adapter was stopped. |
| STATUS_INVALID_PARAMETER | Parameters were validated and determined to be incorrect. |
| STATUS_NO_MEMORY | Not enough memory could be allocated to satisfy the operation. |

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

[**D3DKMT_QUERYADAPTERINFO**](ns-d3dkmthk-_d3dkmt_queryadapterinfo.md)

[**D3DKMTQueryAdapterInfo**](nf-d3dkmthk-d3dkmtqueryadapterinfo.md)
