---
UID: NC:d3dkmddi.DXGKDDI_FLIPOVERLAY
title: DXGKDDI_FLIPOVERLAY
author: windows-driver-content
description: The DxgkDdiFlipOverlay function displays a new allocation by using the specified overlay.
old-location: display\dxgkddiflipoverlay.htm
old-project: display
ms.assetid: 9e35a48b-1741-4ee2-8e15-6ce51ad4c0ad
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: DXGKDDI_FLIPOVERLAY, DXGKDDI_FLIPOVERLAY callback, DmFunctions_fac1657b-03ec-4d63-93d6-3458423a1fe9.xml, DxgkDdiFlipOverlay, DxgkDdiFlipOverlay callback function [Display Devices], d3dkmddi/DxgkDdiFlipOverlay, display.dxgkddiflipoverlay
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
-	DxgkDdiFlipOverlay
product: Windows
targetos: Windows
req.typenames: 
---

# DXGKDDI_FLIPOVERLAY callback function


## -description


The <i>DxgkDdiFlipOverlay</i> function displays a new allocation by using the specified overlay.


## -parameters




### -param hOverlay [in]

[in] A handle to the overlay to be flipped. The display miniport driver's <a href="https://msdn.microsoft.com/1ccdd16d-fd76-4039-b538-86c77b4e8cbb">DxgkDdiCreateOverlay</a> function previously provided this handle to the Microsoft DirectX graphics kernel subsystem in the <b>hOverlay</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff557572">DXGKARG_CREATEOVERLAY</a> structure. 


### -param pFlipOverlay [in]

[in] A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff557590">DXGKARG_FLIPOVERLAY</a> structure that describes the new allocation to display by using the overlay.


## -returns



<i>DxgkDdiFlipOverlay</i> returns one of the following values:

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
<i>DxgkDdiFlipOverlay</i> successfully displays the new allocation.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
Parameters that were passed to <i>DxgkDdiFlipOverlay</i> contained errors that prevented it from completing.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NO_MEMORY</b></dt>
</dl>
</td>
<td width="60%">
<i>DxgkDdiFlipOverlay</i> could not allocate memory that was required for it to complete.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_GRAPHICS_DRIVER_MISMATCH</b></dt>
</dl>
</td>
<td width="60%">
The display miniport driver is not compatible with the user-mode display driver that initiated the call to <i>DxgkDdiFlipOverlay</i>. 

</td>
</tr>
</table>
 




## -remarks



<i>DxgkDdiFlipOverlay</i> should be made pageable.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff557572">DXGKARG_CREATEOVERLAY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557590">DXGKARG_FLIPOVERLAY</a>



<a href="https://msdn.microsoft.com/1ccdd16d-fd76-4039-b538-86c77b4e8cbb">DxgkDdiCreateOverlay</a>
 

 

