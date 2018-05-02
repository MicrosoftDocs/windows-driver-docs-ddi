---
UID: NF:d3dkmthk.D3DKMTReleaseKeyedMutex
title: D3DKMTReleaseKeyedMutex function
author: windows-driver-content
description: The D3DKMTReleaseKeyedMutex function releases a keyed mutex object.
old-location: display\d3dkmtreleasekeyedmutex.htm
old-project: display
ms.assetid: c2a50621-fa84-4525-86f7-845e886203fe
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: D3DKMTReleaseKeyedMutex, D3DKMTReleaseKeyedMutex function [Display Devices], OpenGL_Functions_16fd3037-2615-49c0-8500-7c93bcda3c9f.xml, d3dkmthk/D3DKMTReleaseKeyedMutex, display.d3dkmtreleasekeyedmutex
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Universal
req.target-min-winverclnt: D3DKMTReleaseKeyedMutex is supported beginning with the Windows 7 operating system.
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
-	API-MS-Win-DX-D3DKmt-l1-1-0.dll
-	API-MS-Win-DX-D3DKmt-l1-1-1.dll
-	API-MS-Win-DX-D3DKMT-L1-1-2.dll
api_name:
-	D3DKMTReleaseKeyedMutex
product:
- Windows
targetos: Windows
req.typenames: 
---

# D3DKMTReleaseKeyedMutex function


## -description


The <b>D3DKMTReleaseKeyedMutex</b> function releases a keyed mutex object.


## -parameters




### -param Arg1

TBD




#### - pData [in, out]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff548234">D3DKMT_RELEASEKEYEDMUTEX</a> structure that specifies the keyed mutex object to release. 


## -returns



<b>D3DKMTReleaseKeyedMutex</b> returns one of the following values:

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
The keyed mutex object was successfully released. 

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

<a href="https://msdn.microsoft.com/library/windows/hardware/ff547129">D3DKMTReleaseKeyedMutex</a> could not complete because of insufficient memory.

</td>
</tr>
</table>
 

This function might also return other NTSTATUS values.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff548234">D3DKMT_RELEASEKEYEDMUTEX</a>
 

 

