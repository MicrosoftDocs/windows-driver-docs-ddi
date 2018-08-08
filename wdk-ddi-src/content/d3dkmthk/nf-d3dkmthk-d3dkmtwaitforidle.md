---
UID: NF:d3dkmthk.D3DKMTWaitForIdle
title: D3DKMTWaitForIdle function
author: windows-driver-content
description: The D3DKMTWaitForIdle function waits for a display device to be idle.
old-location: display\d3dkmtwaitforidle.htm
tech.root: display
ms.assetid: 6107da09-3f3d-4a89-91e4-f920061f7704
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: D3DKMTWaitForIdle, D3DKMTWaitForIdle function [Display Devices], OpenGL_Functions_80855290-d991-4e03-aa64-f0fb486c57b0.xml, d3dkmthk/D3DKMTWaitForIdle, display.d3dkmtwaitforidle
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
-	D3DKMTWaitForIdle
product:
- Windows
targetos: Windows
req.typenames: 
---

# D3DKMTWaitForIdle function


## -description


The <b>D3DKMTWaitForIdle</b> function waits for a display device to be idle. 


## -parameters




### -param D3DKMT_WAITFORIDLE






#### - pData [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff548423">D3DKMT_WAITFORIDLE</a> structure that specifies the display device to wait for. 


## -returns



<b>D3DKMTWaitForIdle</b> returns one of the following values:

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
The wait for the display device successfully occurred. 

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
 

This function might also return other NTSTATUS values.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff548423">D3DKMT_WAITFORIDLE</a>
 

 

