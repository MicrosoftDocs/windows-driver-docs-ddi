---
UID: NF:d3dkmthk.D3DKMTSetProcessSchedulingPriorityClass
title: D3DKMTSetProcessSchedulingPriorityClass function
author: windows-driver-content
description: The D3DKMTSetProcessSchedulingPriorityClass function sets the scheduling priority for a process.
old-location: display\d3dkmtsetprocessschedulingpriorityclass.htm
old-project: display
ms.assetid: 1c0177da-5e5f-4e3e-aef2-05d8079bfb95
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: D3DKMTSetProcessSchedulingPriorityClass, D3DKMTSetProcessSchedulingPriorityClass function [Display Devices], OpenGL_Functions_757bbe38-6623-4438-8af3-a2282bec6c78.xml, d3dkmthk/D3DKMTSetProcessSchedulingPriorityClass, display.d3dkmtsetprocessschedulingpriorityclass
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
-	D3DKMTSetProcessSchedulingPriorityClass
product: Windows
targetos: Windows
req.typenames: 
---

# D3DKMTSetProcessSchedulingPriorityClass function


## -description


The <b>D3DKMTSetProcessSchedulingPriorityClass</b> function sets the scheduling priority for a process.


## -parameters




### -param

TBD




#### - Priority [in]

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff548248">D3DKMT_SCHEDULINGPRIORITYCLASS</a>-typed value that indicates the priority level to set for the process.


#### - hProcess [in]

A handle to the process that scheduling priority is set for.


## -returns



<b>D3DKMTSetProcessSchedulingPriorityClass</b> returns one of the following values:

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




<a href="https://msdn.microsoft.com/library/windows/hardware/ff546992">D3DKMTGetProcessSchedulingPriorityClass</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548248">D3DKMT_SCHEDULINGPRIORITYCLASS</a>
 

 

