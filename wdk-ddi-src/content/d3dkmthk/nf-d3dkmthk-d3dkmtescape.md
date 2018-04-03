---
UID: NF:d3dkmthk.D3DKMTEscape
title: D3DKMTEscape function
author: windows-driver-content
description: The D3DKMTEscape function exchanges information with the display miniport driver.
old-location: display\d3dkmtescape.htm
old-project: display
ms.assetid: 60b105df-2085-40bc-9d95-0f6b317a565e
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3DKMTEscape, D3DKMTEscape function [Display Devices], OpenGL_Functions_ad391641-4fb5-425a-839f-7b257f26849a.xml, d3dkmthk/D3DKMTEscape, display.d3dkmtescape
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
-	D3DKMTEscape
product:
- Windows
targetos: Windows
req.typenames: D3DKMT_DRIVERVERSION
---

# D3DKMTEscape function


## -description


The <b>D3DKMTEscape</b> function exchanges information with the display miniport driver.


## -parameters




### -param D3DKMT_ESCAPE

TBD




#### - pData [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff547970">D3DKMT_ESCAPE</a> structure that describes the exchanged information.


## -returns



<b>D3DKMTEscape</b> returns one of the following values:

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
Information was successfully shared.

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

<a href="https://msdn.microsoft.com/library/windows/hardware/ff546940">D3DKMTEscape</a> could not complete because of insufficient memory.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_PRIVILEGED_INSTRUCTION</b></dt>
</dl>
</td>
<td width="60%">

<a href="https://msdn.microsoft.com/library/windows/hardware/ff546940">D3DKMTEscape</a> detected nonprivileged instructions (that is, instructions that access memory beyond the privilege of the current CPU process).

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_ILLEGAL_INSTRUCTION</b></dt>
</dl>
</td>
<td width="60%">

<a href="https://msdn.microsoft.com/library/windows/hardware/ff546940">D3DKMTEscape</a> detected instructions that cannot be supported by graphics hardware.

</td>
</tr>
</table>
 

This function might also return other <b>NTSTATUS</b> values.




## -remarks



The OpenGL ICD calls <b>D3DKMTEscape</b> to exchange data directly with the display miniport driver. For testing purposes, the OpenGL ICD can also call <b>D3DKMTEscape</b> to control the video memory manager and graphics processing unit (GPU) scheduler (which are part of <i>Dxgkrnl.sys</i>) and the behavior of the operating system's Timeout Detection and Recovery (TDR) process. 

Hardware vendors can use <b>D3DKMTEscape</b> in their OpenGL ICDs as an extension mechanism. However, vendors should report necessary extensions to Microsoft so the extensions can be natively supported by the operating system.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff547970">D3DKMT_ESCAPE</a>
 

 

