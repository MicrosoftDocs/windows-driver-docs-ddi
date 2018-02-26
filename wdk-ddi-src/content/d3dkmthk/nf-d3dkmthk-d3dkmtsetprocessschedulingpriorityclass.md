---
UID: NF:d3dkmthk.D3DKMTSetProcessSchedulingPriorityClass
title: D3DKMTSetProcessSchedulingPriorityClass function
author: windows-driver-content
description: The D3DKMTSetProcessSchedulingPriorityClass function sets the scheduling priority for a process.
old-location: display\d3dkmtsetprocessschedulingpriorityclass.htm
old-project: display
ms.assetid: 1c0177da-5e5f-4e3e-aef2-05d8079bfb95
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: ",  , 3, C, D, D3DKMTSetProcessSchedulingPriorityClass, D3DKMTSetProcessSchedulingPriorityClass function [Display Devices], K, M, OpenGL_Functions_757bbe38-6623-4438-8af3-a2282bec6c78.xml, P, S, T, a, c, d, d3dkmthk/D3DKMTSetProcessSchedulingPriorityClass, display.d3dkmtsetprocessschedulingpriorityclass, e, g, h, i, l, n, o, r, s, t, u, y"
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	Gdi32.dll
-	API-MS-Win-dx-d3dkmt-l1-1-0.dll
-	API-MS-Win-dx-d3dkmt-l1-1-1.dll
-	API-MS-Win-DX-D3DKMT-L1-1-2.dll
apiname:
-	D3DKMTSetProcessSchedulingPriorityClass
product: Windows
targetos: Windows
req.typenames: D3DKMT_DRIVERVERSION
---

# D3DKMTSetProcessSchedulingPriorityClass function


## -description


The <b>D3DKMTSetProcessSchedulingPriorityClass</b> function sets the scheduling priority for a process.


## -syntax


````
NTSTATUS APIENTRY D3DKMTSetProcessSchedulingPriorityClass(
  _In_ HANDLE                         hProcess,
  _In_ D3DKMT_SCHEDULINGPRIORITYCLASS Priority
);
````


## -parameters




### -param

TBD




#### - hProcess [in]

A handle to the process that scheduling priority is set for.


#### - Priority [in]

A <a href="..\d3dkmthk\ne-d3dkmthk-_d3dkmt_schedulingpriorityclass.md">D3DKMT_SCHEDULINGPRIORITYCLASS</a>-typed value that indicates the priority level to set for the process.


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

<a href="..\d3dkmthk\ne-d3dkmthk-_d3dkmt_schedulingpriorityclass.md">D3DKMT_SCHEDULINGPRIORITYCLASS</a>



<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtgetprocessschedulingpriorityclass.md">D3DKMTGetProcessSchedulingPriorityClass</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMTSetProcessSchedulingPriorityClass function%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

