---
UID: NC:d3dkmddi.DXGKCB_UPDATECONTEXTALLOCATION
title: DXGKCB_UPDATECONTEXTALLOCATION (d3dkmddi.h)
description: DxgkCbUpdateContextAllocation is used to update the content of a context allocation.
old-location: display\dxgkcbupdatecontextallocation.htm
ms.date: 10/13/2021
keywords: ["DXGKCB_UPDATECONTEXTALLOCATION callback function"]
ms.keywords: DXGKCB_UPDATECONTEXTALLOCATION, DXGKCB_UPDATECONTEXTALLOCATION callback, DxgkCbUpdateContextAllocation, DxgkCbUpdateContextAllocation callback function [Display Devices], d3dkmddi/DxgkCbUpdateContextAllocation, display.dxgkcbupdatecontextallocation
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 10 (WDDM 2.0)
req.target-min-winversvr: Windows Server 2016
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
 - DXGKCB_UPDATECONTEXTALLOCATION
 - d3dkmddi/DXGKCB_UPDATECONTEXTALLOCATION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dkmddi.h
api_name:
 - DXGKCB_UPDATECONTEXTALLOCATION
---

# DXGKCB_UPDATECONTEXTALLOCATION callback function

## -description

**DXGKCB_UPDATECONTEXTALLOCATION** updates the content of a context allocation.

## -parameters

### -param hAdapter [in]

A handle to the display adapter.

### -param pArgs [in]

The [**DXGKARGCB_UPDATECONTEXTALLOCATION**](ns-d3dkmddi-_dxgkargcb_updatecontextallocation.md) structure that describes the operation.

## -returns

**DXGKCB_UPDATECONTEXTALLOCATION** returns STATUS_SUCCESS if the operation succeeds. Otherwise, it returns one of the error codes defined in *Ntstatus.h*.

## -remarks

*DXGKCB_XXX* functions are implemented by *Dxgkrnl*. To use this callback function, set the members of [**DXGKARGCB_UPDATECONTEXTALLOCATION**](ns-d3dkmddi-_dxgkargcb_updatecontextallocation.md) and then call **DxgkCbUpdateContextAllocation** via the [**DXGKRNL_INTERFACE**](../dispmprt/ns-dispmprt-_dxgkrnl_interface.md).

The video memory manager maps the specified allocation in the paging process address space, then calls **DXGKCB_UPDATECONTEXTALLOCATION** to trigger a context allocation update paging operation, passing the kernel-mode display driver the specified driver private data.

The call to **DXGKCB_UPDATECONTEXTALLOCATION** returns when the update to the context allocation is completed.

## -see-also

[**DXGKARGCB_UPDATECONTEXTALLOCATION**](ns-d3dkmddi-_dxgkargcb_updatecontextallocation.md)

[**DXGKRNL_INTERFACE**](../dispmprt/ns-dispmprt-_dxgkrnl_interface.md)
