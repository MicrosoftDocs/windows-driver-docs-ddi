---
UID: NC:d3dkmddi.DXGKDDI_BEGINEXCLUSIVEACCESS
title: DXGKDDI_BEGINEXCLUSIVEACCESS (d3dkmddi.h)
description: Implemented by the client driver to begin exclusive access.
ms.assetid: 23fc30a6-54b3-48d9-97d9-271ffc38ef5f
ms.date: 10/19/2018
ms.topic: callback
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
topic_type:
-	apiref
api_type:
-	UserDefined
api_location:
-	d3dkmddi.h
api_name:
-	DXGKDDI_BEGINEXCLUSIVEACCESS
product:
-	Windows
targetos: Windows
tech.root: display
ms.custom: RS5
---

# DXGKDDI_BEGINEXCLUSIVEACCESS callback function

## -description

Implemented by the client driver to begin exclusive access.

## -prototype

```cpp
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

Pointer to a [DXGKARG_BEGINEXCLUSIVEACCESS](ns-d3dkmddi-_dxgkarg_beginexclusiveaccess.md) structure to begin exclusive access.

## -returns

Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate NTSTATUS Values error code.

## -remarks

Register your implementation of this callback function by setting the appropriate member of DXGKARG_BEGINEXCLUSIVEACCESS and then calling DxgkddiBeginExclusiveAccess.


## -see-also
