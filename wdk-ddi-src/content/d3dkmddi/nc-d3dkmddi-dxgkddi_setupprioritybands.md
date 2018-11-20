---
UID: NC:d3dkmddi.DXGKDDI_SETUPPRIORITYBANDS
title: DXGKDDI_SETUPPRIORITYBANDS
author: windows-driver-content
description: Set up the GPU scheduler priority band configuration, after adapter startup and before scheduling the first GPU work item.
ms.assetid: c655afa4-9c1a-4c25-995f-1d1762ef0b6c
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
-	DXGKDDI_SETUPPRIORITYBANDS
product:
-	Windows
targetos: Windows
tech.root: display
ms.custom: RS5
---

# DXGKDDI_SETUPPRIORITYBANDS callback function

## -description

Set up the GPU scheduler priority band configuration, after adapter startup and before scheduling the first GPU work item. This call can be made in the middle of GPU work execution, and the GPU scheduler needs to use the new value during the next yield calculation.

## -prototype

```cpp
//Declaration

DXGKDDI_SETUPPRIORITYBANDS DxgkddiSetupprioritybands;

// Definition

NTSTATUS DxgkddiSetupprioritybands
(
	IN_CONST_HANDLE hAdapter
	IN_CONST_PDXGKARG_SETUPPRIORITYBANDS pSetupPriorityBands
)
{...}

DXGKDDI_SETUPPRIORITYBANDS *PDXGKDDI_SETUPPRIORITYBANDS


```

## -parameters

### -param hAdapter

The logical adapter for which the priority band assignment is made.

### -param pSetupPriorityBands:

Pointer to a [DXGKARG_SETUPPRIORITYBANDS](ns-d3dkmddi-_dxgkarg_setupprioritybands.md) structure that contains information to set up priority bands.

## -returns

Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate NTSTATUS Values error code.

## -remarks

Register your implementation of this callback function by setting the appropriate member of DXGKARG_SETUPPRIORITYBANDS and then calling DxgkDdiSetupPriorityBands.


## -see-also
