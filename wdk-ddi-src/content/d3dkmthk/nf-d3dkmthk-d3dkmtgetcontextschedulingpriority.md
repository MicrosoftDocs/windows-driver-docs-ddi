---
UID: NF:d3dkmthk.D3DKMTGetContextSchedulingPriority
title: D3DKMTGetContextSchedulingPriority function
author: windows-driver-content
description: The D3DKMTGetContextSchedulingPriority function retrieves the scheduling priority for a device context.
old-location: display\d3dkmtgetcontextschedulingpriority.htm
tech.root: display
ms.assetid: db4968d3-c23b-417f-9c91-552923dce1ea
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: D3DKMTGetContextSchedulingPriority, D3DKMTGetContextSchedulingPriority function [Display Devices], OpenGL_Functions_2f186385-7f1b-445e-93f9-594dea4feeb4.xml, d3dkmthk/D3DKMTGetContextSchedulingPriority, display.d3dkmtgetcontextschedulingpriority
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
-	D3DKMTGetContextSchedulingPriority
product:
- Windows
targetos: Windows
req.typenames: 
---

# D3DKMTGetContextSchedulingPriority function


## -description


The <b>D3DKMTGetContextSchedulingPriority</b> function retrieves the scheduling priority for a device context.


## -parameters




### -param Arg1






#### - pData [in, out]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff548027">D3DKMT_GETCONTEXTSCHEDULINGPRIORITY</a> structure that describes parameters for retrieving the scheduling priority for a device context.


## -returns



<b>D3DKMTGetContextSchedulingPriority</b> returns one of the following values:

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
The scheduling priority was successfully retrieved.

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




<a href="https://msdn.microsoft.com/library/windows/hardware/ff548027">D3DKMT_GETCONTEXTSCHEDULINGPRIORITY</a>
 

 

