---
UID: NC:d3dkmddi.DXGKDDI_GETSTANDARDALLOCATIONDRIVERDATA
title: DXGKDDI_GETSTANDARDALLOCATIONDRIVERDATA (d3dkmddi.h)
description: The DxgkDdiGetStandardAllocationDriverData function returns a description of a standard allocation type.
old-location: display\dxgkddigetstandardallocationdriverdata.htm
ms.assetid: 38a9859f-ed9f-41a5-9bf1-c734480499ea
ms.date: 05/10/2018
ms.keywords: DXGKDDI_GETSTANDARDALLOCATIONDRIVERDATA, DXGKDDI_GETSTANDARDALLOCATIONDRIVERDATA callback, DmFunctions_e28fa3aa-909e-4dd0-8ae7-1355e0aa69cf.xml, DxgkDdiGetStandardAllocationDriverData, DxgkDdiGetStandardAllocationDriverData callback function [Display Devices], d3dkmddi/DxgkDdiGetStandardAllocationDriverData, display.dxgkddigetstandardallocationdriverdata
ms.topic: callback
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
 - "d3dkmddi/DxgkDdiGetStandardAllocationDriverData"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dkmddi.h
api_name:
 - DxgkDdiGetStandardAllocationDriverData
product:
 - Windows
---

# DXGKDDI_GETSTANDARDALLOCATIONDRIVERDATA callback function

## -description

The <i>DxgkDdiGetStandardAllocationDriverData</i> function returns a description of a standard allocation type.

## -parameters

### -param hAdapter

[in] A handle to a context block that is associated with a display adapter. The display miniport driver previously provided this handle to the Microsoft DirectX graphics kernel subsystem in the <i>MiniportDeviceContext</i> output parameter of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_add_device">DxgkDdiAddDevice</a> function.

### -param pGetStandardAllocationDriverData

[in/out] A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgkarg_getstandardallocationdriverdata">DXGKARG_GETSTANDARDALLOCATIONDRIVERDATA</a> structure that describes a standard allocation.

## -returns

<i>DxgkDdiGetStandardAllocationDriverData</i> returns one of the following values:

|Return code|Description|
|--- |--- |
|STATUS_SUCCESS|DxgkDdiGetStandardAllocationDriverData successfully returned a description of the standard allocation type.|
|STATUS_NO_MEMORY|DxgkDdiGetStandardAllocationDriverData could not allocate memory that was required for it to complete.|

## -remarks

<i>Standard allocation types</i> are allocations that must be created in kernel mode without communication from the user-mode display driver. The DirectX graphics kernel subsystem calls the <i>DxgkDdiGetStandardAllocationDriverData</i> function to generate a description of the standard allocation type that the <i>pGetStandardAllocationDriverData</i> parameter specifies. The display miniport driver returns the description of the allocation type in the <b>pAllocationPrivateDriverData</b> and <b>pResourcePrivateDriverData</b> members of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgkarg_getstandardallocationdriverdata">DXGKARG_GETSTANDARDALLOCATIONDRIVERDATA</a> structure that the <i>pGetStandardAllocationDriverData</i> parameter points to. The DirectX graphics kernel subsystem subsequently passes the description to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_createallocation">DxgkDdiCreateAllocation</a> function to actually create the allocation.

Beginning with Windows 7, if a display miniport driver processes a call to the <i>DxgkDdiGetStandardAllocationDriverData</i> function to create allocations for GDI hardware acceleration, the driver should set the pitch of the allocation for CPU visible allocations, <i>pGetStandardAllocationDriverData-></i><b>pCreateGdiSurfaceData</b><i>-></i><b>Pitch</b>.

<i>DxgkDdiGetStandardAllocationDriverData</i> should be made pageable.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgkarg_getstandardallocationdriverdata">DXGKARG_GETSTANDARDALLOCATIONDRIVERDATA</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_add_device">DxgkDdiAddDevice</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_createallocation">DxgkDdiCreateAllocation</a>

