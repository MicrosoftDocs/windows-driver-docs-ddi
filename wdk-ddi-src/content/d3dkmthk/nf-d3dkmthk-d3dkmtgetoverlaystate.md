---
UID: NF:d3dkmthk.D3DKMTGetOverlayState
title: D3DKMTGetOverlayState function
author: windows-driver-content
description: The D3DKMTGetOverlayState function retrieves the status about an overlay.
old-location: display\d3dkmtgetoverlaystate.htm
tech.root: display
ms.assetid: 6e3db876-c9f9-4de9-a0e2-5911132b72be
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: D3DKMTGetOverlayState, D3DKMTGetOverlayState function [Display Devices], OpenGL_Functions_f2301345-c6d8-42bf-82f9-f8f97d29674f.xml, d3dkmthk/D3DKMTGetOverlayState, display.d3dkmtgetoverlaystate
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Universal
req.target-min-winverclnt: D3DKMTGetOverlayState is supported beginning with the Windows 7 operating system.
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
-	D3DKMTGetOverlayState
product:
- Windows
targetos: Windows
req.typenames: 
---

# D3DKMTGetOverlayState function


## -description


The <b>D3DKMTGetOverlayState</b> function retrieves the status about an overlay.


## -parameters




### -param Arg1

TBD




#### - pData [in, out]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff548049">D3DKMT_GETOVERLAYSTATE</a> structure that describes parameters to retrieve status about an overlay. 


## -returns



<b>D3DKMTGetOverlayState</b> returns one of the following values:

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
The status about an overlay was successfully retrieved. 

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
</table>
 

This function might also return other <b>NTSTATUS</b> values.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff548049">D3DKMT_GETOVERLAYSTATE</a>
 

 

