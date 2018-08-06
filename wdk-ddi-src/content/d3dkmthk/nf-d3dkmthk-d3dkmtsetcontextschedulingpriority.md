---
UID: NF:d3dkmthk.D3DKMTSetContextSchedulingPriority
title: D3DKMTSetContextSchedulingPriority function
author: windows-driver-content
description: The D3DKMTSetContextSchedulingPriority function sets the scheduling priority for a device context.
old-location: display\d3dkmtsetcontextschedulingpriority.htm
tech.root: display
ms.assetid: 781d5a78-a3e2-4cac-868d-c4ae8b39b2fc
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: D3DKMTSetContextSchedulingPriority, D3DKMTSetContextSchedulingPriority function [Display Devices], OpenGL_Functions_f9314ed6-8aad-4c55-b42a-f1223dada5bc.xml, d3dkmthk/D3DKMTSetContextSchedulingPriority, display.d3dkmtsetcontextschedulingpriority
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
-	D3DKMTSetContextSchedulingPriority
product:
- Windows
targetos: Windows
req.typenames: 
---

# D3DKMTSetContextSchedulingPriority function


## -description


The <b>D3DKMTSetContextSchedulingPriority</b> function sets the scheduling priority for a device context.


## -parameters




### -param D3DKMT_SETCONTEXTSCHEDULINGPRIORITY






#### - pData [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff548267">D3DKMT_SETCONTEXTSCHEDULINGPRIORITY</a> structure that describes parameters for setting the scheduling priority for a device context.


## -returns



<b>D3DKMTSetContextSchedulingPriority</b> returns one of the following values:

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
The scheduling priority was successfully set.

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




<a href="https://msdn.microsoft.com/library/windows/hardware/ff548267">D3DKMT_SETCONTEXTSCHEDULINGPRIORITY</a>
 

 

