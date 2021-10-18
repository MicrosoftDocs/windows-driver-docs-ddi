---
UID: NC:d3dkmddi.DXGKCB_GETHANDLEPARENT
title: DXGKCB_GETHANDLEPARENT (d3dkmddi.h)
description: The DxgkCbGetHandleParent function retrieves the parent resource from the specified allocation.
old-location: display\dxgkcbgethandleparent.htm
ms.date: 10/13/2021
keywords: ["DXGKCB_GETHANDLEPARENT callback function"]
ms.keywords: DXGKCB_GETHANDLEPARENT, DXGKCB_GETHANDLEPARENT callback, DpFunctions_7094d9b1-3262-45b9-88de-e834878b6b2d.xml, DxgkCbGetHandleParent, DxgkCbGetHandleParent callback function [Display Devices], d3dkmddi/DxgkCbGetHandleParent, display.dxgkcbgethandleparent
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Desktop
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
req.lib: 
req.dll: 
req.irql: < DISPATCH_LEVEL
targetos: Windows
tech.root: display
req.typenames: 
f1_keywords:
 - DXGKCB_GETHANDLEPARENT
 - d3dkmddi/DXGKCB_GETHANDLEPARENT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dkmddi.h
api_name:
 - DXGKCB_GETHANDLEPARENT
---

# DXGKCB_GETHANDLEPARENT callback function

## -description

**DXGKCB_GETHANDLEPARENT** retrieves the parent resource from the specified allocation.

## -parameters

### -param hAllocation

[in] A handle to an allocation. This handle must be the kernel-mode handle that the DirectX graphics kernel subsystem (*Dxgkrnl.sys*) assigned for the allocation.

## -returns

**DXGKCB_GETHANDLEPARENT** returns a graphics subsystem-specific handle to the parent resource for the allocation that is associated with the handle that the **hAllocation** parameter specifies.

If **DXGKCB_GETHANDLEPARENT** returns a NULL handle, *Dxgkrnl.sys* was unable to resolve the handle to the parent resource for a reason such as the following possibilities:

* An invalid handle was received from the user-mode display driver because of a malicious attack or some other bug.
* Allocations had lifetime issues.

If a NULL handle is returned, the display miniport driver should fail its currently running DDI function with STATUS_INVALID_HANDLE.

## -remarks

For **DXGKCB_GETHANDLEPARENT** to return a resource handle, the handle in **hAllocation** must be an allocation handle that is associated with a resource; otherwise, **DXGKCB_GETHANDLEPARENT** returns NULL.

*DXGKCB_XXX* functions are implemented by *Dxgkrnl*. To use this callback function, call **DxgkCbGetHandleParent** via the [**DXGKRNL_INTERFACE**](../dispmprt/ns-dispmprt-_dxgkrnl_interface.md).

## -see-also

[**DXGKRNL_INTERFACE**](../dispmprt/ns-dispmprt-_dxgkrnl_interface.md)
