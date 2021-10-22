---
UID: NC:d3dkmddi.DXGKCB_DESTROYCONTEXTALLOCATION
title: DXGKCB_DESTROYCONTEXTALLOCATION (d3dkmddi.h)
description: Called by a WDDM 1.2 or later display miniport driver to free a resource that was previously allocated for a GPU or device-specific context.
old-location: display\dxgkcbdestroycontextallocation.htm
ms.date: 10/13/2021
keywords: ["DXGKCB_DESTROYCONTEXTALLOCATION callback function"]
ms.keywords: DXGKCB_DESTROYCONTEXTALLOCATION, DXGKCB_DESTROYCONTEXTALLOCATION callback, DxgkCbDestroyContextAllocation, DxgkCbDestroyContextAllocation callback function [Display Devices], d3dkmddi/DxgkCbDestroyContextAllocation, display.dxgkcbdestroycontextallocation
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 8 (WDDM 1.2)
req.target-min-winversvr: Windows Server 2012
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
req.irql: PASSIVE_LEVEL
targetos: Windows
tech.root: display
req.typenames: 
f1_keywords:
 - DXGKCB_DESTROYCONTEXTALLOCATION
 - d3dkmddi/DXGKCB_DESTROYCONTEXTALLOCATION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - D3dkmddi.h
api_name:
 - DXGKCB_DESTROYCONTEXTALLOCATION
---

# DXGKCB_DESTROYCONTEXTALLOCATION callback function

## -description

**DXGKCB_DESTROYCONTEXTALLOCATION** frees a resource that was previously allocated for a GPU or device-specific context.

## -parameters

### -param hAdapter [in]

Handle to the graphics adapter for which the allocation was created. The display miniport driver receives the handle from the **DeviceHandle** member of the [**DXGKRNL_INTERFACE**](../dispmprt/ns-dispmprt-_dxgkrnl_interface.md) structure in a call to its [**DxgkDdiStartDevice**](../dispmprt/nc-dispmprt-dxgkddi_start_device.md) function.

### -param hAllocation [in]

Handle that was assigned by the DirectX graphics subsystem (*Dxgkrnl*) to the context allocation. The display miniport driver receives the handle from the **hAllocation** member of the [**DXGKARGCB_CREATECONTEXTALLOCATION**](ns-d3dkmddi-_dxgkargcb_createcontextallocation.md) structure in a call to the [**DXGKCB_CREATECONTEXTALLOCATION**](nc-d3dkmddi-dxgkcb_createcontextallocation.md) function.

## -returns

**DXGKCB_DESTROYCONTEXTALLOCATION** returns STATUS_SUCCESS if it succeeds. Otherwise, it returns one of the error codes defined in *Ntstatus.h*.

## -remarks

The display miniport driver calls [**DXGKCB_CREATECONTEXTALLOCATION**](nc-d3dkmddi-dxgkcb_createcontextallocation.md) to allocate a context resource. After such a call, the driver can call **DXGKCB_DESTROYCONTEXTALLOCATION** at any time to free the resource.

*DXGKCB_XXX* functions are implemented by *Dxgkrnl*. To use this callback function, call **DxgkCbDestroyContextAllocation** via the [**DXGKRNL_INTERFACE**](../dispmprt/ns-dispmprt-_dxgkrnl_interface.md).

## -see-also

[**DXGKARGCB_CREATECONTEXTALLOCATION**](ns-d3dkmddi-_dxgkargcb_createcontextallocation.md)

[**DXGKCB_CREATECONTEXTALLOCATION**](nc-d3dkmddi-dxgkcb_createcontextallocation.md)

[**DXGKRNL_INTERFACE**](../dispmprt/ns-dispmprt-_dxgkrnl_interface.md)
