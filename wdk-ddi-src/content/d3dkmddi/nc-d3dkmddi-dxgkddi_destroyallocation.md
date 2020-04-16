---
UID: NC:d3dkmddi.DXGKDDI_DESTROYALLOCATION
title: DXGKDDI_DESTROYALLOCATION (d3dkmddi.h)
description: The DxgkDdiDestroyAllocation function releases allocations.
old-location: display\dxgkddidestroyallocation.htm
ms.assetid: cade544a-f9c6-4635-ab57-d09d694ca315
ms.date: 05/10/2018
keywords: ["DXGKDDI_DESTROYALLOCATION callback function"]
ms.keywords: DXGKDDI_DESTROYALLOCATION, DXGKDDI_DESTROYALLOCATION callback, DmFunctions_4139c309-b149-436b-9ed1-89c0c26f5425.xml, DxgkDdiDestroyAllocation, DxgkDdiDestroyAllocation callback function [Display Devices], d3dkmddi/DxgkDdiDestroyAllocation, display.dxgkddidestroyallocation
req.header: d3dkmddi.h
req.include-header: 
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
req.irql: PASSIVE_LEVEL
targetos: Windows
tech.root: display
req.typenames: 
f1_keywords:
 - "d3dkmddi/DxgkDdiDestroyAllocation"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dkmddi.h
api_name:
 - DxgkDdiDestroyAllocation
product:
 - Windows
---

# DXGKDDI_DESTROYALLOCATION callback function

## -description

The <i>DxgkDdiDestroyAllocation</i> function releases allocations.

## -parameters

### -param hAdapter

[in] A handle to a context block that is associated with a display adapter. The display miniport driver previously provided this handle to the Microsoft DirectX graphics kernel subsystem in the <i>MiniportDeviceContext</i> output parameter of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_add_device">DxgkDdiAddDevice</a> function.

### -param pDestroyAllocation

[in] A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgkarg_destroyallocation">DXGKARG_DESTROYALLOCATION</a> structure that contains information for releasing allocations.

## -returns

<i>DxgkDdiDestroyAllocation</i> returns STATUS_SUCCESS, or an appropriate error result if the allocations are not successfully released.

## -remarks

When the user-mode display driver calls the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_deallocatecb">pfnDeallocateCb</a> function, the DirectX graphics kernel subsystem (which is part of <i>Dxgkrnl.sys</i>) calls the display miniport driver's <i>DxgkDdiDestroyAllocation</i> function to release the allocations. The display miniport driver should clean up its internal data structures and references to the allocations. The Microsoft Direct3D runtime initiates calls to the video memory manager (which is also part of <i>Dxgkrnl.sys</i>), which then calls the GPU scheduler (which is also part of <i>Dxgkrnl.sys</i>) to synchronize before video memory is actually released. 

The display miniport driver can release the entire resource as well as allocations. To determine whether the resource should be released, the display miniport driver can check whether the <b>DestroyResource</b> flag is set in the <b>Flags</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgkarg_destroyallocation">DXGKARG_DESTROYALLOCATION</a> structure that the <i>pDestroyAllocation</i> parameter points to. To release the resource, the display miniport driver must clean up the handle that the <b>hResource</b> member of DXGKARG_DESTROYALLOCATION specifies. If the display miniport driver does not release the resource, the driver can change the value in <b>hResource</b> if necessary.

<i>DxgkDdiDestroyAllocation</i> should be made pageable.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgkarg_destroyallocation">DXGKARG_DESTROYALLOCATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_add_device">DxgkDdiAddDevice</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_deallocatecb">pfnDeallocateCb</a>

