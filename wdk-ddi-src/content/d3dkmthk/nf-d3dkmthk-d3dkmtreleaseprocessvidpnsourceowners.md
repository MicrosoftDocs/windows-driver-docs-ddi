---
UID: NF:d3dkmthk.D3DKMTReleaseProcessVidPnSourceOwners
title: D3DKMTReleaseProcessVidPnSourceOwners function
author: windows-driver-content
description: The D3DKMTReleaseProcessVidPnSourceOwners function releases the video present network source owners for a process.
old-location: display\d3dkmtreleaseprocessvidpnsourceowners.htm
ms.assetid: 65fa0654-25b5-4ead-ac9e-0eb0f404259a
ms.date: 05/10/2018
ms.keywords: D3DKMTReleaseProcessVidPnSourceOwners, D3DKMTReleaseProcessVidPnSourceOwners function [Display Devices], OpenGL_Functions_8c1e2870-c803-4ca4-99f1-8f39a00983c8.xml, d3dkmthk/D3DKMTReleaseProcessVidPnSourceOwners, display.d3dkmtreleaseprocessvidpnsourceowners
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
-	D3DKMTReleaseProcessVidPnSourceOwners
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# D3DKMTReleaseProcessVidPnSourceOwners function


## -description


The <b>D3DKMTReleaseProcessVidPnSourceOwners</b> function releases the video present network source owners for a process.


## -parameters




### -param Arg1

*hProcess* 

[in] A handle to the process that video present network source owners are released from.


## -returns



<b>D3DKMTReleaseProcessVidPnSourceOwners</b> returns one of the following values:

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
The video present network source owners for a process were successfully released.

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



