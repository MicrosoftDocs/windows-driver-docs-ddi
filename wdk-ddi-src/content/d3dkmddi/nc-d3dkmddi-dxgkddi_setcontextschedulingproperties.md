---
UID: NC:d3dkmddi.DXGKDDI_SETCONTEXTSCHEDULINGPROPERTIES
title: DXGKDDI_SETCONTEXTSCHEDULINGPROPERTIES (d3dkmddi.h)
description: Set up or modify the scheduling properties for a device context.
ms.assetid: be40d154-343b-431d-a2d7-da0dfaa4fb41
ms.date: 10/19/2018
ms.topic: callback
f1_keywords:
 - "d3dkmddi/DXGKDDI_SETCONTEXTSCHEDULINGPROPERTIES"
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
- apiref
api_type:
- UserDefined
api_location:
- d3dkmddi.h
api_name:
- DXGKDDI_SETCONTEXTSCHEDULINGPROPERTIES
product:
- Windows
targetos: Windows
tech.root: display
ms.custom: RS5
---

# DXGKDDI_SETCONTEXTSCHEDULINGPROPERTIES callback function

## -description

Set up or modify the scheduling properties for a device context.

## -prototype

```cpp
//Declaration

DXGKDDI_SETCONTEXTSCHEDULINGPROPERTIES DxgkddiSetcontextschedulingproperties;

// Definition

NTSTATUS DxgkddiSetcontextschedulingproperties
(
	IN_CONST_HANDLE hAdapter
	IN_CONST_PDXGKARG_SETCONTEXTSCHEDULINGPROPERTIES pSetContextSchedulingProperties
)
{...}

DXGKDDI_SETCONTEXTSCHEDULINGPROPERTIES *PDXGKDDI_SETCONTEXTSCHEDULINGPROPERTIES


```

## -parameters

### -param hAdapter

A handle to the device context.

### -param pSetContextSchedulingProperties:

Pointer to a [DXGKARG_SETCONTEXTSCHEDULINGPROPERTIES](ns-d3dkmddi-_dxgkarg_setcontextschedulingproperties.md) structure that contains the scheduling properties.

## -returns

Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate NTSTATUS Values error code.

## -remarks

Register your implementation of this callback function by setting the appropriate member of DXGKARG_SETCONTEXTSCHEDULINGPROPERTIES and then calling DxgkDdiSetContextSchedulingProperties.

When an adapter is opened for the first time for a particular process, the OS calls [DxgkDdiCreateProcess](nc-d3dkmddi-dxgkddi_createprocess.md) so that the kernel mode driver (KMD) can create an appropriate per process, per adapter tracking data structure. When a context is created, the KMD knows what device and adapter it is created for, and it should be able to look up the KMD process handle from the adapter tracking data structure for this process. Within the KMD process, the scheduler is expected to have tracking data structures for all four potential priority bands contexts should be assigned to.

When a context is created, or a Direct3D device changes priority, or an application gains or loses focus, the OS calls the GPU scheduler to set up or modify its scheduling properties. For newly created contexts, the OS guarantees that context scheduling properties will be set prior to the first submission to this context is allowed. This call can be made in the middle of a context execution. GPU scheduler has some leeway in terms of how it affects the current scheduling period, and the OS requirement is that the change should take effect on the next scheduling iteration for the priority band.

## -see-also
