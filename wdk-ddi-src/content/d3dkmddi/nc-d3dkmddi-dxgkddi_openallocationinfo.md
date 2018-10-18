---
UID: NC:d3dkmddi.DXGKDDI_OPENALLOCATIONINFO
title: DXGKDDI_OPENALLOCATIONINFO
author: windows-driver-content
description: The DxgkDdiOpenAllocation function binds non-device-specific allocations that the DxgkDdiCreateAllocation function created to allocations that are specific to the specified graphics context device.
old-location: display\dxgkddiopenallocation.htm
ms.assetid: 551154d7-950d-40e5-810b-8d803c1731ca
ms.date: 5/10/2018
ms.keywords: DXGKDDI_OPENALLOCATIONINFO, DXGKDDI_OPENALLOCATIONINFO callback, DmFunctions_e27ad0cd-ae79-4207-abb0-68f048452101.xml, DxgkDdiOpenAllocation, DxgkDdiOpenAllocation callback function [Display Devices], d3dkmddi/DxgkDdiOpenAllocation, display.dxgkddiopenallocation
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
-	DxgkDdiOpenAllocation
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# DXGKDDI_OPENALLOCATIONINFO callback function


## -description


The <i>DxgkDdiOpenAllocation</i> function binds non-device-specific allocations that the <a href="https://msdn.microsoft.com/a28287d6-4dfa-4db4-92df-bbcd9379a5b2">DxgkDdiCreateAllocation</a> function created to allocations that are specific to the specified graphics context device.


## -parameters




### -param hDevice [in]

[in] A handle to the graphics context device that the allocations are bound from. The display miniport driver's <a href="https://msdn.microsoft.com/a7027735-0ec4-4fad-81fb-1c3aca4ebf2d">DxgkDdiCreateDevice</a> function previously provided this handle to the Microsoft DirectX graphics kernel subsystem in the <b>hDevice</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff557570">DXGKARG_CREATEDEVICE</a> structure. 


### -param pOpenAllocation [in]

[in] A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff557609">DXGKARG_OPENALLOCATION</a> structure that contains information about binding allocations.


## -returns



<i>DxgkDdiOpenAllocation</i> returns one of the following values:

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
<i>DxgkDdiOpenAllocation</i> successfully bound allocations to the graphics context device that the <i>hDevice</i> parameter specified.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
Parameters that were passed to <i>DxgkDdiOpenAllocation</i> contained errors that prevented it from completing.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NO_MEMORY</b></dt>
</dl>
</td>
<td width="60%">
<i>DxgkDdiOpenAllocation</i> could not allocate memory that was required for it to complete.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_GRAPHICS_DRIVER_MISMATCH</b></dt>
</dl>
</td>
<td width="60%">
The display miniport driver is not compatible with the user-mode display driver that initiated the call to <i>DxgkDdiOpenAllocation</i> (that is, supplied private data to the display miniport driver). 

</td>
</tr>
</table>
 




## -remarks



The DirectX graphics kernel subsystem calls the display miniport driver's <i>DxgkDdiOpenAllocation</i> function to bind nondevice-specific allocations that the <a href="https://msdn.microsoft.com/a28287d6-4dfa-4db4-92df-bbcd9379a5b2">DxgkDdiCreateAllocation</a> function created to allocations that are specific to the graphics context device that the <i>hDevice</i> parameter specifies. The display miniport driver binds allocations to a device so the driver can keep track of allocation data that is specific to a device. 

The display miniport driver can bind an allocation to any device that any process (on the same graphics adapter) created and not just to a device in the creating process. 

When <i>DxgkDdiOpenAllocation</i> returns STATUS_SUCCESS, the driver sets the <b>hDeviceSpecificAllocation</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff561983">DXGK_OPENALLOCATIONINFO</a> structure for each allocation to a non-NULL value. The DXGK_OPENALLOCATIONINFO structure for each allocation is an element of the array that the <b>pOpenAllocation</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff557609">DXGKARG_OPENALLOCATION</a> structure specifies.  

The driver can modify the allocation private driver data that is passed in the <b>pPrivateDriverData</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff561983">DXGK_OPENALLOCATIONINFO</a> structure only when the allocation is created (which is indicated when the <b>Create</b> bit-field flag in the <b>Flags</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff557609">DXGKARG_OPENALLOCATION</a> structure is set). The driver should determine that it can only read the allocation private driver data when the allocation is opened (that is, when the <b>Create</b> bit-field flag is not set).

<i>DxgkDdiOpenAllocation</i> should be made pageable.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff557570">DXGKARG_CREATEDEVICE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557609">DXGKARG_OPENALLOCATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561983">DXGK_OPENALLOCATIONINFO</a>



<a href="https://msdn.microsoft.com/a28287d6-4dfa-4db4-92df-bbcd9379a5b2">DxgkDdiCreateAllocation</a>



<a href="https://msdn.microsoft.com/a7027735-0ec4-4fad-81fb-1c3aca4ebf2d">DxgkDdiCreateDevice</a>
 

 

