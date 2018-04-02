---
UID: NC:d3dkmddi.DXGKDDI_GETSTANDARDALLOCATIONDRIVERDATA
title: DXGKDDI_GETSTANDARDALLOCATIONDRIVERDATA
author: windows-driver-content
description: The DxgkDdiGetStandardAllocationDriverData function returns a description of a standard allocation type.
old-location: display\dxgkddigetstandardallocationdriverdata.htm
old-project: display
ms.assetid: 38a9859f-ed9f-41a5-9bf1-c734480499ea
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: DXGKDDI_GETSTANDARDALLOCATIONDRIVERDATA, DmFunctions_e28fa3aa-909e-4dd0-8ae7-1355e0aa69cf.xml, DxgkDdiGetStandardAllocationDriverData, DxgkDdiGetStandardAllocationDriverData callback function [Display Devices], d3dkmddi/DxgkDdiGetStandardAllocationDriverData, display.dxgkddigetstandardallocationdriverdata
ms.prod: windows-hardware
ms.technology: windows-devices
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	d3dkmddi.h
api_name:
-	DxgkDdiGetStandardAllocationDriverData
product: Windows
targetos: Windows
req.typenames: DD_MULTISAMPLEQUALITYLEVELSDATA
---

# DXGKDDI_GETSTANDARDALLOCATIONDRIVERDATA callback


## -description


The <i>DxgkDdiGetStandardAllocationDriverData</i> function returns a description of a standard allocation type.


## -parameters




### -param hAdapter [in]

[in] A handle to a context block that is associated with a display adapter. The display miniport driver previously provided this handle to the Microsoft DirectX graphics kernel subsystem in the <i>MiniportDeviceContext</i> output parameter of the <a href="https://msdn.microsoft.com/5fd4046f-54c3-4dfc-8d51-0d9ebcde0bea">DxgkDdiAddDevice</a> function.


### -param pGetStandardAllocationDriverData [in, out]

[in/out] A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff557598">DXGKARG_GETSTANDARDALLOCATIONDRIVERDATA</a> structure that describes a standard allocation.


## -returns



<i>DxgkDdiGetStandardAllocationDriverData</i> returns one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
<i>DxgkDdiGetStandardAllocationDriverData</i> successfully returned a description of the standard allocation type.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NO_MEMORY</b></dt>
</dl>
</td>
<td width="60%">
<i>DxgkDdiGetStandardAllocationDriverData</i> could not allocate memory that was required for it to complete.

</td>
</tr>
</table>
 




## -remarks



<i>Standard allocation types</i> are allocations that must be created in kernel mode without communication from the user-mode display driver. The DirectX graphics kernel subsystem calls the <i>DxgkDdiGetStandardAllocationDriverData</i> function to generate a description of the standard allocation type that the <i>pGetStandardAllocationDriverData</i> parameter specifies. The display miniport driver returns the description of the allocation type in the <b>pAllocationPrivateDriverData</b> and <b>pResourcePrivateDriverData</b> members of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff557598">DXGKARG_GETSTANDARDALLOCATIONDRIVERDATA</a> structure that the <i>pGetStandardAllocationDriverData</i> parameter points to. The DirectX graphics kernel subsystem subsequently passes the description to the <a href="https://msdn.microsoft.com/a28287d6-4dfa-4db4-92df-bbcd9379a5b2">DxgkDdiCreateAllocation</a> function to actually create the allocation.

Beginning with Windows 7, if a display miniport driver processes a call to the <i>DxgkDdiGetStandardAllocationDriverData</i> function to create allocations for GDI hardware acceleration, the driver should set the pitch of the allocation for CPU visible allocations, <i>pGetStandardAllocationDriverData-&gt;</i><b>pCreateGdiSurfaceData</b><i>-&gt;</i><b>Pitch</b>.

<i>DxgkDdiGetStandardAllocationDriverData</i> should be made pageable.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff557598">DXGKARG_GETSTANDARDALLOCATIONDRIVERDATA</a>



<a href="https://msdn.microsoft.com/5fd4046f-54c3-4dfc-8d51-0d9ebcde0bea">DxgkDdiAddDevice</a>



<a href="https://msdn.microsoft.com/a28287d6-4dfa-4db4-92df-bbcd9379a5b2">DxgkDdiCreateAllocation</a>
 

 

