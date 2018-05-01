---
UID: NF:d3dkmthk.D3DKMTGetScanLine
title: D3DKMTGetScanLine function
author: windows-driver-content
description: The D3DKMTGetScanLine function determines whether the given video present source of a video present network (VidPN) is in vertical blanking mode and retrieves the current scan line.
old-location: display\d3dkmtgetscanline.htm
old-project: display
ms.assetid: 052507ec-4a26-4bb6-8876-c03a9c81f412
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: D3DKMTGetScanLine, D3DKMTGetScanLine function [Display Devices], OpenGL_Functions_3a2d269d-0867-42fb-9268-86c560531de4.xml, d3dkmthk/D3DKMTGetScanLine, display.d3dkmtgetscanline
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
-	D3DKMTGetScanLine
product: Windows
targetos: Windows
req.typenames: 
---

# D3DKMTGetScanLine function


## -description


The <b>D3DKMTGetScanLine</b> function determines whether the given video present source of a video present network (VidPN) is in vertical blanking mode and retrieves the current scan line.


## -parameters




### -param Arg1

TBD




#### - pData [in, out]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff548064">D3DKMT_GETSCANLINE</a> structure that contains the vertical blanking status of a video present source.


## -returns



<b>D3DKMTGetScanLine</b> returns one of the following values:

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
The vertical blanking status and scan line were successfully retrieved.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_DEVICE_REMOVED</b></dt>
</dl>
</td>
<td width="60%">
The graphics adapter was stopped.

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




<a href="https://msdn.microsoft.com/library/windows/hardware/ff548064">D3DKMT_GETSCANLINE</a>
 

 

