---
UID: NF:d3dkmthk.D3DKMTSetDisplayPrivateDriverFormat
title: D3DKMTSetDisplayPrivateDriverFormat function
author: windows-driver-content
description: The D3DKMTSetDisplayPrivateDriverFormat function changes the private-format attribute of a video present source.
old-location: display\d3dkmtsetdisplayprivatedriverformat.htm
ms.assetid: 4b720076-161f-47b4-b410-f9554e502a53
ms.date: 05/10/2018
ms.keywords: D3DKMTSetDisplayPrivateDriverFormat, D3DKMTSetDisplayPrivateDriverFormat function [Display Devices], OpenGL_Functions_742fb584-0b9d-4650-a0a6-64f3e3f55dff.xml, d3dkmthk/D3DKMTSetDisplayPrivateDriverFormat, display.d3dkmtsetdisplayprivatedriverformat
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
-	D3DKMTSetDisplayPrivateDriverFormat
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# D3DKMTSetDisplayPrivateDriverFormat function


## -description


The <b>D3DKMTSetDisplayPrivateDriverFormat</b> function changes the private-format attribute of a video present source.


## -parameters




### -param D3DKMT_SETDISPLAYPRIVATEDRIVERFORMAT






*pData* [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff548290">D3DKMT_SETDISPLAYPRIVATEDRIVERFORMAT</a> structure that describes how to format a video present source.


## -returns



<b>D3DKMTSetDisplayPrivateDriverFormat</b> returns one of the following values:

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
The video present source was successfully changed.

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
Before the call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff547171">D3DKMTSetDisplayPrivateDriverFormat</a>, the device did not acquire exclusive ownership of the view. Therefore, the device could not change the private-format attribute of the video present source.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NOT_SUPPORTED</b></dt>
</dl>
</td>
<td width="60%">
The display miniport driver does not support the <a href="https://msdn.microsoft.com/053fdf22-20c3-4b57-94f4-0613857abfa7">DxgkDdiSetDisplayPrivateDriverFormat</a> function. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_UNSUCCESSFUL</b></dt>
</dl>
</td>
<td width="60%">
The display miniport driver could not change the private-format attribute of the view for the video present source. 

</td>
</tr>
</table>
 

This function might also return other NTSTATUS values.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff548290">D3DKMT_SETDISPLAYPRIVATEDRIVERFORMAT</a>



<a href="https://msdn.microsoft.com/053fdf22-20c3-4b57-94f4-0613857abfa7">DxgkDdiSetDisplayPrivateDriverFormat</a>
 

 

