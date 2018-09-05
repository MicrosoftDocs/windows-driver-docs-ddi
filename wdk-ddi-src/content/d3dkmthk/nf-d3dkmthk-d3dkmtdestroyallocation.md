---
UID: NF:d3dkmthk.D3DKMTDestroyAllocation
title: D3DKMTDestroyAllocation function
author: windows-driver-content
description: The D3DKMTDestroyAllocation function releases a resource, a list of allocations, or both.
old-location: display\d3dkmtdestroyallocation.htm
ms.assetid: 249ca05c-406d-4d47-a266-222f7be1a883
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: D3DKMTDestroyAllocation, D3DKMTDestroyAllocation function [Display Devices], OpenGL_Functions_ecc5579c-3b0a-4c2c-9978-9f2591444c03.xml, d3dkmthk/D3DKMTDestroyAllocation, display.d3dkmtdestroyallocation
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
-	D3DKMTDestroyAllocation
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# D3DKMTDestroyAllocation function


## -description


The <b>D3DKMTDestroyAllocation</b> function releases a resource, a list of allocations, or both.


## -parameters




### -param D3DKMT_DESTROYALLOCATION






#### - pData [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff547868">D3DKMT_DESTROYALLOCATION</a> structure that contains information for releasing allocations.


## -returns



<b>D3DKMTDestroyAllocation</b> returns one of the following values:

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
Allocations were successfully released.

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




<a href="https://msdn.microsoft.com/library/windows/hardware/ff547868">D3DKMT_DESTROYALLOCATION</a>
 

 

