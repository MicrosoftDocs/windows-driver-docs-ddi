---
UID: NF:d3dkmthk.D3DKMTGetContextInProcessSchedulingPriority
title: D3DKMTGetContextInProcessSchedulingPriority function
author: windows-driver-content
description: Called by an in-process (in-proc) Microsoft Direct3D composition device to retrieve the scheduling priority for a device context that is in the same process as other device contexts.
old-location: display\d3dkmtgetcontextinprocessschedulingpriority.htm
tech.root: display
ms.assetid: e2a662b6-6a16-4e63-b5a8-5701a7180f60
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: D3DKMTGetContextInProcessSchedulingPriority, D3DKMTGetContextInProcessSchedulingPriority function [Display Devices], d3dkmthk/D3DKMTGetContextInProcessSchedulingPriority, display.d3dkmtgetcontextinprocessschedulingpriority
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	D3dkmthk.h
api_name:
-	D3DKMTGetContextInProcessSchedulingPriority
product:
- Windows
targetos: Windows
req.typenames: 
---

# D3DKMTGetContextInProcessSchedulingPriority function


## -description


Called by an in-process (in-proc) Microsoft Direct3D composition device to retrieve the scheduling priority for a device context that is in the same process as other device contexts.


## -parameters




### -param Arg1






#### - pContextPriority [in, out]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/hh780256">D3DKMT_GETCONTEXTINPROCESSSCHEDULINGPRIORITY</a> structure that describes information that is required to retrieve the scheduling priority for a device context.


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
 

This function might also return other NTSTATUS values.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh780250">D3DKMTSetContextInProcessSchedulingPriority</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh780256">D3DKMT_GETCONTEXTINPROCESSSCHEDULINGPRIORITY</a>
 

 

