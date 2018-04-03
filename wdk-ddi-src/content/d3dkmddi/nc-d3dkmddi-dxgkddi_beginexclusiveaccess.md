---
UID: NC:d3dkmddi.DXGKDDI_BEGINEXCLUSIVEACCESS
title: DXGKDDI_BEGINEXCLUSIVEACCESS
author: windows-driver-content
description:
ms.assetid: 23fc30a6-54b3-48d9-97d9-271ffc38ef5f
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
-	DXGKDDI_BEGINEXCLUSIVEACCESS
product: Windows
targetos: Windows
---

# DXGKDDI_BEGINEXCLUSIVEACCESS callback function

## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.

Implemented by the client driver to begin exclusive access.

## -prototype

```
//Declaration

DXGKDDI_BEGINEXCLUSIVEACCESS DxgkddiBeginexclusiveaccess;

// Definition

NTSTATUS DxgkddiBeginexclusiveaccess
(
	IN_CONST_HANDLE hAdapter
	IN_PDXGKARG_BEGINEXCLUSIVEACCESS pBeginExclusiveAccess
)
{...}

DXGKDDI_BEGINEXCLUSIVEACCESS *PDXGKDDI_BEGINEXCLUSIVEACCESS


```

## -parameters

### -param hAdapter

A handle to a context block that is associated with a display adapter.

### -param pBeginExclusiveAccess:

Pointer to a DXGKARG_BEGINEXCLUSIVEACCESS structure to begin exclusive access.

## -returns

Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate NTSTATUS Values error code.

## -remarks

Register your implementation of this callback function by setting the appropriate member of DXGKARG_BEGINEXCLUSIVEACCESS and then calling DxgkddiBeginExclusiveAccess.


## -see-also