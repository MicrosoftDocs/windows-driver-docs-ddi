---
UID: NC:d3dkmddi.DXGKDDI_ENDEXCLUSIVEACCESS
title: DXGKDDI_ENDEXCLUSIVEACCESS
author: windows-driver-content
description:
ms.assetid: 942f37e5-310a-4233-bda9-5e606d41756e
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
-	DXGKDDI_ENDEXCLUSIVEACCESS
product: Windows
targetos: Windows
---

# DXGKDDI_ENDEXCLUSIVEACCESS callback function

## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.

Implemented by the client driver to end exclusive access.

## -prototype

```
//Declaration

DXGKDDI_ENDEXCLUSIVEACCESS DxgkddiEndexclusiveaccess;

// Definition

NTSTATUS DxgkddiEndexclusiveaccess
(
	IN_CONST_HANDLE hAdapter
	IN_PDXGKARG_ENDEXCLUSIVEACCESS pEndExclusiveAccess
)
{...}

DXGKDDI_ENDEXCLUSIVEACCESS *PDXGKDDI_ENDEXCLUSIVEACCESS


```

## -parameters

### -param hAdapter

A handle to a context block that is associated with a display adapter.

### -param pEndExclusiveAccess:

Pointer to a DXGKARG_ENDEXCLUSIVEACCESS structure to begin exclusive access.

## -returns

Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate NTSTATUS Values error code.

## -remarks

Register your implementation of this callback function by setting the appropriate member of DXGKARG_ENDEXCLUSIVEACCESS and then calling DxgkddiEndexclusiveaccess.


## -see-also