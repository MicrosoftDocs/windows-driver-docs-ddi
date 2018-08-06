---
UID: NF:d3dkmthk.D3DKMTSetDisplayMode
title: D3DKMTSetDisplayMode function
author: windows-driver-content
description: The D3DKMTSetDisplayMode function sets the allocation that is used to scan out to the display.
old-location: display\d3dkmtsetdisplaymode.htm
tech.root: display
ms.assetid: bf51b8dc-82e8-420e-bc3d-7cb9e8d72b9f
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: D3DKMTSetDisplayMode, D3DKMTSetDisplayMode function [Display Devices], OpenGL_Functions_dc92e1c9-5873-42b6-a8f8-f6827091dac4.xml, d3dkmthk/D3DKMTSetDisplayMode, display.d3dkmtsetdisplaymode
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Universal
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
req.lib: Gdi32.lib
req.dll: Gdi32.dll
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	Gdi32.dll
-	API-MS-Win-dx-d3dkmt-l1-1-0.dll
-	API-MS-Win-dx-d3dkmt-l1-1-1.dll
-	API-MS-Win-DX-D3DKMT-L1-1-2.dll
api_name:
-	D3DKMTSetDisplayMode
product:
- Windows
targetos: Windows
req.typenames: 
---

# D3DKMTSetDisplayMode function


## -description


The <i>D3DKMTSetDisplayMode</i> function sets the allocation that is used to scan out to the display.


## -parameters




### -param D3DKMT_SETDISPLAYMODE






#### - pData [in, out]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff548275">D3DKMT_SETDISPLAYMODE</a> structure that describes the allocation that is used to scan out.


## -returns



<i>D3DKMTSetDisplayMode</i> returns one of the following values:

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
The display mode was successfully set.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_DEVICE_REMOVED</b></dt>
</dl>
</td>
<td width="60%">
The graphics adapter was stopped or the display device was reset.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
Parameters were validated and determined to be incorrect.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_GRAPHICS_NOT_EXCLUSIVE_MODE_OWNER</b></dt>
</dl>
</td>
<td width="60%">

        Before the call to 
      <a href="https://msdn.microsoft.com/library/windows/hardware/ff547169">D3DKMTSetDisplayMode</a>, the device did not acquire exclusive ownership of the view; therefore, the device could not set the display mode.
       

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>D3DDDIERR_INCOMPATIBLEPRIVATEFORMAT</b></dt>
</dl>
</td>
<td width="60%">
The OpenGL installable client driver (ICD) must convert the format of the surface that is associated with the allocation that the <b>hPrimaryAllocation</b> member of <a href="https://msdn.microsoft.com/library/windows/hardware/ff548275">D3DKMT_SETDISPLAYMODE</a> specifies into the format attribute that the <b>PrivateDriverFormatAttribute</b> member of D3DKMT_SETDISPLAYMODE specifies. The ICD should then call 
      <a href="https://msdn.microsoft.com/library/windows/hardware/ff547169">D3DKMTSetDisplayMode</a> again. The ICD could allocate a new allocation, perform a conversion bit-block transfer (bitblt) from the old primary to the new, and then destroy the old primary as long as the ICD uses the new allocation handle for this allocation for all subsequent operations. The ICD should repeat this process until 
      <i>D3DKMTSetDisplayMode</i> returns a different return value. 

</td>
</tr>
</table>
 

This function might also return other NTSTATUS values.




## -remarks



Before the OpenGL ICD calls 
      <i>D3DKMTSetDisplayMode</i> to set a new display mode that uses an extended format, a multiple-sampling method, or both, the ICD must ensure that the current GDI display mode has the same resolution as the new display mode; otherwise, 
      <i>D3DKMTSetDisplayMode</i> returns <b>STATUS_INVALID_PARAMETER</b>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff548275">D3DKMT_SETDISPLAYMODE</a>
 

 

