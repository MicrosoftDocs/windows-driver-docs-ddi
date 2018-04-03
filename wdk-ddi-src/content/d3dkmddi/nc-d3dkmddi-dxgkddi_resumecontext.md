---
UID: NC:d3dkmddi.DXGKDDI_RESUMECONTEXT
title: DXGKDDI_RESUMECONTEXT
author: windows-driver-content
description:
ms.assetid: 57730d60-f6d7-4c86-92c5-dcd33108e99b
ms.author: windowsdriverdev
ms.date:
ms.topic: callback
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	apiref
apitype:
-	UserDefined
apilocation:
-	d3dkmddi.h
apiname:
-	DXGKDDI_RESUMECONTEXT
product: Windows
targetos: Windows
---

# DXGKDDI_RESUMECONTEXT callback function

## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.

Implemented by the client driver to resume a context. A context is created in a resumed state by default.

## -prototype

```
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

## -parameters

### -param hAdapter

The hardware context to be resumed.

### -param pResumeContext

Pointer a DXGKARG_RESUMECONTEXT structure that contains information to resume the content.


## -returns

Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate NTSTATUS Values error code.

## -remarks

Register your implementation of this callback function by setting the appropriate member of DXGKARG_RESUMECONTEXT and then calling DxgkDdiResumeContext.


## -see-also