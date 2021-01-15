---
UID: NC:d3dkmddi.DXGKCB_GETHANDLEPARENT
title: DXGKCB_GETHANDLEPARENT (d3dkmddi.h)
description: The DxgkCbGetHandleParent function retrieves the parent resource from the specified allocation.
old-location: display\dxgkcbgethandleparent.htm
ms.date: 05/10/2018
keywords: ["DXGKCB_GETHANDLEPARENT callback function"]
ms.keywords: DXGKCB_GETHANDLEPARENT, DXGKCB_GETHANDLEPARENT callback, DpFunctions_7094d9b1-3262-45b9-88de-e834878b6b2d.xml, DxgkCbGetHandleParent, DxgkCbGetHandleParent callback function [Display Devices], d3dkmddi/DxgkCbGetHandleParent, display.dxgkcbgethandleparent
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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

The <b>DxgkCbGetHandleParent</b> function retrieves the parent resource from the specified allocation.

## -parameters

### -param hAllocation

[in] A handle to an allocation. This handle must be the kernel-mode handle that the Microsoft DirectX graphics kernel subsystem (<i>Dxgkrnl.sys</i>) assigned for the allocation.

## -returns

<b>DxgkCbGetHandleParent</b> returns a graphics subsystem-specific handle to the parent resource for the allocation that is associated with the handle that the <i>hAllocation</i> parameter specifies.

If <i>DxgkCbGetHandleParent</i> returns a <b>NULL</b> handle, the DirectX graphics kernel subsystem was unable to resolve the handle to the parent resource because, for example, of the following possible reasons:



<ul>
<li>An invalid handle was received from the user-mode display driver because of a malicious attack or some other bug.</li>
<li>Allocations had lifetime issues. </li>
</ul>
If a <b>NULL</b> handle is returned, the display miniport driver should fail its currently running DDI function with STATUS_INVALID_HANDLE.

## -remarks

For <b>DxgkCbGetHandleParent</b> to return a resource handle, the handle in <i>hAllocation</i> must be an allocation handle that is associated with a resource; otherwise, <b>DxgkCbGetHandleParent</b> returns <b>NULL</b>.

