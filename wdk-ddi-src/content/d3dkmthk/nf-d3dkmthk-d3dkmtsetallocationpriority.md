---
UID: NF:d3dkmthk.D3DKMTSetAllocationPriority
title: D3DKMTSetAllocationPriority function
author: windows-driver-content
description: The D3DKMTSetAllocationPriority function sets the priority level of a resource or list of allocations.
old-location: display\d3dkmtsetallocationpriority.htm
tech.root: display
ms.assetid: d5ad6288-6123-4665-a48e-bbae856cc160
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: D3DKMTSetAllocationPriority, D3DKMTSetAllocationPriority function [Display Devices], OpenGL_Functions_dc77467a-7ec3-4be9-96cd-8bedb5beb948.xml, d3dkmthk/D3DKMTSetAllocationPriority, display.d3dkmtsetallocationpriority
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
-	D3DKMTSetAllocationPriority
product:
- Windows
targetos: Windows
req.typenames: 
---

# D3DKMTSetAllocationPriority function


## -description


The <b>D3DKMTSetAllocationPriority</b> function sets the priority level of a resource or list of allocations.


## -parameters




### -param D3DKMT_SETALLOCATIONPRIORITY

TBD




#### - pData [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff548262">D3DKMT_SETALLOCATIONPRIORITY</a> structure that contains information for setting the priority level of a resource or list of allocations.


## -returns



<b>D3DKMTSetAllocationPriority</b> returns one of the following values:

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
Priority level for allocations was successfully set.

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
</table>
 

This function might also return other NTSTATUS values.




## -remarks



The following code example demonstrates how an OpenGL ICD can use <b>D3DKMTSetAllocationPriority</b> to set the priority level of a resource (and therefore all of the allocations that are associated with the resource).

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>VOID SetResourcePriority(D3DKMT_HANDLE hDevice, D3DKMT_HANDLE hResource, UINT uiPriority)
{
    D3DKMT_SETALLOCATIONPRIORITY SetAllocationPriorityData;

    SetAllocationPriorityData.hDevice = hDevice;
    SetAllocationPriorityData.hResource = hResource;
    SetAllocationPriorityData.phAllocationList = NULL;
    SetAllocationPriorityData.AllocationCount = 0;
    SetAllocationPriorityData.Priorities = &amp;uiPriority;    

    (*pfnKTSetAllocationPriority)(&amp;SetAllocationPriorityData);
}</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff548262">D3DKMT_SETALLOCATIONPRIORITY</a>
 

 

