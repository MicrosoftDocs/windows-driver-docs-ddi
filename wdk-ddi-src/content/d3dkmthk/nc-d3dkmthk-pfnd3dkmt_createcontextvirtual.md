---
UID: NC:d3dkmthk.PFND3DKMT_CREATECONTEXTVIRTUAL
title: PFND3DKMT_CREATECONTEXTVIRTUAL (d3dkmthk.h)
description: The D3dkmtCreateContextVirtual callback function creates a virtual context.
ms.date: 10/19/2018
keywords: ["PFND3DKMT_CREATECONTEXTVIRTUAL callback function"]
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
 - PFND3DKMT_CREATECONTEXTVIRTUAL
 - d3dkmthk/PFND3DKMT_CREATECONTEXTVIRTUAL
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3dkmthk.h
api_name:
 - PFND3DKMT_CREATECONTEXTVIRTUAL
dev_langs:
 - c++
---

# PFND3DKMT_CREATECONTEXTVIRTUAL callback function


## -description

The D3dkmtCreateContextVirtual callback function creates a virtual context.

## -parameters

### -param Arg1

[in, out] Pointer to a [D3DKMT_CREATECONTEXTVIRTUAL](ns-d3dkmthk-_d3dkmt_createcontextvirtual.md) structure.

## -returns

Returns NTSTATUS.

## -prototype

```cpp
//Declaration

PFND3DKMT_CREATECONTEXTVIRTUAL Pfnd3dkmtCreatecontextvirtual; 

// Definition

NTSTATUS Pfnd3dkmtCreatecontextvirtual 
(
	D3DKMT_CREATECONTEXTVIRTUAL *
)
{...}

```

