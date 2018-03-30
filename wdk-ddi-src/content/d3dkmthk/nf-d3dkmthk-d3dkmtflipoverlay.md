---
UID: NF:d3dkmthk.D3DKMTFlipOverlay
title: D3DKMTFlipOverlay function
author: windows-driver-content
description: The D3DKMTFlipOverlay function changes the allocation to display on the overlay.
old-location: display\d3dkmtflipoverlay.htm
old-project: display
ms.assetid: 09424b92-bf55-4348-8b6a-f632a0dc9b2f
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3DKMTFlipOverlay, D3DKMTFlipOverlay function [Display Devices], OpenGL_Functions_37a9811c-26a3-46f3-aba1-39dc9526f282.xml, d3dkmthk/D3DKMTFlipOverlay, display.d3dkmtflipoverlay
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
-	D3DKMTFlipOverlay
product: Windows
targetos: Windows
req.typenames: D3DKMT_DRIVERVERSION
---

# D3DKMTFlipOverlay function


## -description


The <b>D3DKMTFlipOverlay</b> function changes the allocation to display on the overlay.


## -parameters




### -param D3DKMT_FLIPOVERLAY

TBD




#### - pData [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff548002">D3DKMT_FLIPOVERLAY</a> structure that describes how to change the display on the overlay.


## -returns



<b>D3DKMTFlipOverlay</b> returns one of the following values:

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
The kernel-mode overlay object was successfully flipped.

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
<dt><b>STATUS_NO_MEMORY</b></dt>
</dl>
</td>
<td width="60%">

<a href="https://msdn.microsoft.com/library/windows/hardware/ff546949">D3DKMTFlipOverlay</a> could not complete because of insufficient memory.

</td>
</tr>
</table>
 

This function might also return other <b>NTSTATUS</b> values.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff548002">D3DKMT_FLIPOVERLAY</a>
 

 

