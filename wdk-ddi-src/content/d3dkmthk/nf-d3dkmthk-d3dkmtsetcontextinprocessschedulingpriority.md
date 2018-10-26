---
UID: NF:d3dkmthk.D3DKMTSetContextInProcessSchedulingPriority
title: D3DKMTSetContextInProcessSchedulingPriority function
author: windows-driver-content
description: Called by an in-process (in-proc) Microsoft Direct3D composition device to set the scheduling priority for a device context that is in the same process as other device contexts.
old-location: display\d3dkmtsetcontextinprocessschedulingpriority.htm
ms.assetid: ebac0d06-53cb-4a84-9af9-f8aa9a6eccb6
ms.date: 05/10/2018
ms.keywords: D3DKMTSetContextInProcessSchedulingPriority, D3DKMTSetContextInProcessSchedulingPriority function [Display Devices], d3dkmthk/D3DKMTSetContextInProcessSchedulingPriority, display.d3dkmtsetcontextinprocessschedulingpriority
ms.topic: function
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Universal
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
api_name:
-	D3DKMTSetContextInProcessSchedulingPriority
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# D3DKMTSetContextInProcessSchedulingPriority function


## -description


Called by an in-process (in-proc) Microsoft Direct3D composition device to set the scheduling priority for a device context that is in the same process as other device contexts.


## -parameters




### -param D3DKMT_SETCONTEXTINPROCESSSCHEDULINGPRIORITY

[in] A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/hh780270">D3DKMT_SETCONTEXTINPROCESSSCHEDULINGPRIORITY</a> structure that describes parameters for setting the scheduling priority for a device context.


## -returns



Returns one of the following values:

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
 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh780246">D3DKMTGetContextInProcessSchedulingPriority</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh780270">D3DKMT_SETCONTEXTINPROCESSSCHEDULINGPRIORITY</a>
 

 

