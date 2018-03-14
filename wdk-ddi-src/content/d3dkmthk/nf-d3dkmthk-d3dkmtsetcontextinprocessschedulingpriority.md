---
UID: NF:d3dkmthk.D3DKMTSetContextInProcessSchedulingPriority
title: D3DKMTSetContextInProcessSchedulingPriority function
author: windows-driver-content
description: Called by an in-process (in-proc) Microsoft Direct3D composition device to set the scheduling priority for a device context that is in the same process as other device contexts.
old-location: display\d3dkmtsetcontextinprocessschedulingpriority.htm
old-project: display
ms.assetid: ebac0d06-53cb-4a84-9af9-f8aa9a6eccb6
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3DKMTSetContextInProcessSchedulingPriority, D3DKMTSetContextInProcessSchedulingPriority function [Display Devices], d3dkmthk/D3DKMTSetContextInProcessSchedulingPriority, display.d3dkmtsetcontextinprocessschedulingpriority
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
-	D3DKMTSetContextInProcessSchedulingPriority
product: Windows
targetos: Windows
req.typenames: D3DKMT_DRIVERVERSION
---

# D3DKMTSetContextInProcessSchedulingPriority function


## -description


Called by an in-process (in-proc) Microsoft Direct3D composition device to set the scheduling priority for a device context that is in the same process as other device contexts.


## -syntax


````
_Check_return_ NTSTATUS APIENTRY D3DKMTSetContextInProcessSchedulingPriority(
  _In_ const D3DKMT_SETCONTEXTINPROCESSSCHEDULINGPRIORITY *pContextPriority
);
````


## -parameters




### -param D3DKMT_SETCONTEXTINPROCESSSCHEDULINGPRIORITY

TBD




#### - pContextPriority [in]

A pointer to a <a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_setcontextinprocessschedulingpriority.md">D3DKMT_SETCONTEXTINPROCESSSCHEDULINGPRIORITY</a> structure that describes parameters for setting the scheduling priority for a device context.


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

<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtgetcontextinprocessschedulingpriority.md">D3DKMTGetContextInProcessSchedulingPriority</a>



<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_setcontextinprocessschedulingpriority.md">D3DKMT_SETCONTEXTINPROCESSSCHEDULINGPRIORITY</a>



 

 


