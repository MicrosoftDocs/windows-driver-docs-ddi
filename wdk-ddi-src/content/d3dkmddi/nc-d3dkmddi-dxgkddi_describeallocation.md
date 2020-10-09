---
UID: NC:d3dkmddi.DXGKDDI_DESCRIBEALLOCATION
title: DXGKDDI_DESCRIBEALLOCATION (d3dkmddi.h)
description: The DxgkDdiDescribeAllocation function retrieves information about an existing allocation that is not otherwise available to the Microsoft DirectX graphics kernel subsystem.
old-location: display\dxgkddidescribeallocation.htm
ms.assetid: 8ee65716-496c-4b0f-baa7-34a625847d5f
ms.date: 05/10/2018
keywords: ["DXGKDDI_DESCRIBEALLOCATION callback function"]
ms.keywords: DXGKDDI_DESCRIBEALLOCATION, DXGKDDI_DESCRIBEALLOCATION callback, DmFunctions_ba74cf3f-f0be-401c-8232-0672d490221a.xml, DxgkDdiDescribeAllocation, DxgkDdiDescribeAllocation callback function [Display Devices], d3dkmddi/DxgkDdiDescribeAllocation, display.dxgkddidescribeallocation
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
 - DXGKDDI_DESCRIBEALLOCATION
 - d3dkmddi/DXGKDDI_DESCRIBEALLOCATION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dkmddi.h
api_name:
 - DxgkDdiDescribeAllocation
product:
 - Windows
---

# DXGKDDI_DESCRIBEALLOCATION callback function


## -description

The <i>DxgkDdiDescribeAllocation</i> function retrieves information about an existing allocation that is not otherwise available to the Microsoft DirectX graphics kernel subsystem.

## -parameters

### -param hAdapter

[in] A handle to a context block that is associated with a display adapter. The display miniport driver previously provided this handle to the DirectX graphics kernel subsystem in the <i>MiniportDeviceContext</i> output parameter of the <a href="/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_add_device">DxgkDdiAddDevice</a> function.

### -param pDescribeAllocation

[in/out] A pointer to a <a href="/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgkarg_describeallocation">DXGKARG_DESCRIBEALLOCATION</a> structure that describes an existing allocation.

## -returns

<i>DxgkDdiDescribeAllocation</i> returns STATUS_SUCCESS if it succeeds; otherwise, it returns one of the error codes defined in <i>Ntstatus.h</i>.

## -remarks

Because the DirectX graphics kernel subsystem does not necessarily maintain records of allocations, the graphics kernel subsystem calls <i>DxgkDdiDescribeAllocation</i> to request that the display miniport driver return information about existing allocations. Currently, the display miniport driver must be able to return this information for the following allocations:

<ul>
<li>
Allocations that are also primaries (that is, allocations that the user-mode display driver created by setting the <b>Primary</b> bit-field flag in the <b>Flags</b> member of the <a href="/windows-hardware/drivers/ddi/d3dukmdt/ns-d3dukmdt-_d3dddi_allocationinfo">D3DDDI_ALLOCATIONINFO</a> structure in a call to the <a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_allocatecb">pfnAllocateCb</a> function).

</li>
<li>
Allocations that might be the source of a presentation (that is, allocations that are represented by the <b>hSource</b> member of the <a href="/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgkarg_present">DXGKARG_PRESENT</a> structure in a call to the display miniport driver's <a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_present">DxgkDdiPresent</a> function).

</li>
</ul>
<i>DxgkDdiDescribeAllocation</i> should be made pageable.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dukmdt/ns-d3dukmdt-_d3dddi_allocationinfo">D3DDDI_ALLOCATIONINFO</a>



<a href="/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgkarg_describeallocation">DXGKARG_DESCRIBEALLOCATION</a>



<a href="/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_add_device">DxgkDdiAddDevice</a>



<a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_present">DxgkDdiPresent</a>



<a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_allocatecb">pfnAllocateCb</a>