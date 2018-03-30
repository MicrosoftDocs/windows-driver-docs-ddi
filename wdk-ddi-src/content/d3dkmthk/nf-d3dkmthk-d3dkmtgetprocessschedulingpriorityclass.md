---
UID: NF:d3dkmthk.D3DKMTGetProcessSchedulingPriorityClass
title: D3DKMTGetProcessSchedulingPriorityClass function
author: windows-driver-content
description: The D3DKMTGetProcessSchedulingPriorityClass function retrieves the scheduling priority for a process.
old-location: display\d3dkmtgetprocessschedulingpriorityclass.htm
old-project: display
ms.assetid: 994df4be-d0ce-4f64-91f5-b5516ce947ec
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3DKMTGetProcessSchedulingPriorityClass, D3DKMTGetProcessSchedulingPriorityClass function [Display Devices], OpenGL_Functions_7af39e72-516e-440a-b4be-f0b3f82156d0.xml, d3dkmthk/D3DKMTGetProcessSchedulingPriorityClass, display.d3dkmtgetprocessschedulingpriorityclass
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
-	D3DKMTGetProcessSchedulingPriorityClass
product: Windows
targetos: Windows
req.typenames: D3DKMT_DRIVERVERSION
---

# D3DKMTGetProcessSchedulingPriorityClass function


## -description


The <b>D3DKMTGetProcessSchedulingPriorityClass</b> function retrieves the scheduling priority for a process.


## -parameters




### -param

TBD




#### - hProcess [in]

A handle to the process for which scheduling priority is set.


#### - pPriority [out]

A pointer to a variable that receives a <a href="https://msdn.microsoft.com/library/windows/hardware/ff548248">D3DKMT_SCHEDULINGPRIORITYCLASS</a>-typed value that indicates the priority level for the process.


## -returns



<b>D3DKMTGetProcessSchedulingPriorityClass</b> returns one of the following values:

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




<a href="https://msdn.microsoft.com/library/windows/hardware/ff547182">D3DKMTSetProcessSchedulingPriorityClass</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548248">D3DKMT_SCHEDULINGPRIORITYCLASS</a>
 

 

