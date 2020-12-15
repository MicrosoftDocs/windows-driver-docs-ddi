---
UID: NC:d3dkmddi.DXGKDDI_RESUMECONTEXT
title: DXGKDDI_RESUMECONTEXT (d3dkmddi.h)
description: Resumes a context. A context is created in a resumed state by default.
ms.date: 10/19/2018
keywords: ["DXGKDDI_RESUMECONTEXT callback function"]
req.header: d3dkmddi.h
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
tech.root: display
ms.custom: RS5
f1_keywords:
 - DXGKDDI_RESUMECONTEXT
 - d3dkmddi/DXGKDDI_RESUMECONTEXT
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3dkmddi.h
api_name:
 - DXGKDDI_RESUMECONTEXT
dev_langs:
 - c++
---

# DXGKDDI_RESUMECONTEXT callback function


## -description

Resumes a context. A context is created in a resumed state by default.

## -parameters

### -param hAdapter

The hardware context to be resumed.

### -param pResumeContext

Pointer a [DXGKARG_RESUMECONTEXT](ns-d3dkmddi-_dxgkarg_resumecontext.md) structure that contains information to resume the content.

## -returns

Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate NTSTATUS Values error code.

## -prototype

```cpp
//Declaration

DXGKDDI_RESUMECONTEXT DxgkddiResumecontext;

// Definition

NTSTATUS DxgkddiResumecontext
(
	IN_CONST_HANDLE hAdapter
	IN_CONST_PDXGKARG_RESUMECONTEXT pResumeContext
)
{...}

DXGKDDI_RESUMECONTEXT *PDXGKDDI_RESUMECONTEXT


```

## -remarks

Register your implementation of this callback function by setting the appropriate member of DXGKARG_RESUMECONTEXT and then calling DxgkDdiResumeContext.

## -see-also

