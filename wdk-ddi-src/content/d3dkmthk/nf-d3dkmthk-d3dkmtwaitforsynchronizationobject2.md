---
UID: NF:d3dkmthk.D3DKMTWaitForSynchronizationObject2
title: D3DKMTWaitForSynchronizationObject2 function
author: windows-driver-content
description: The D3DKMTWaitForSynchronizationObject2 function inserts a wait for the specified synchronization objects in the specified context stream.
old-location: display\d3dkmtwaitforsynchronizationobject2.htm
tech.root: display
ms.assetid: 692d3336-d9cd-438b-a52c-ae4c55070227
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: D3DKMTWaitForSynchronizationObject2, D3DKMTWaitForSynchronizationObject2 function [Display Devices], OpenGL_Functions_4453dc1e-8824-494e-9a74-2d3628f1ff81.xml, d3dkmthk/D3DKMTWaitForSynchronizationObject2, display.d3dkmtwaitforsynchronizationobject2
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Universal
req.target-min-winverclnt: D3DKMTWaitForSynchronizationObject2 is supported beginning with the Windows 7 operating system.
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
-	D3DKMTWaitForSynchronizationObject2
product:
- Windows
targetos: Windows
req.typenames: 
---

# D3DKMTWaitForSynchronizationObject2 function


## -description


The <b>D3DKMTWaitForSynchronizationObject2</b> function inserts a wait for the specified synchronization objects in the specified context stream.


## -parameters




### -param D3DKMT_WAITFORSYNCHRONIZATIONOBJECT2

TBD




#### - pData [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff548436">D3DKMT_WAITFORSYNCHRONIZATIONOBJECT2</a> structure that describes the synchronization objects and context stream that the wait is set up for.


## -returns



<b>D3DKMTWaitForSynchronizationObject2</b> returns one of the following values:

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
The wait was successfully set up.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_DEVICE_REMOVED</b></dt>
</dl>
</td>
<td width="60%">
The graphics adapter was stopped or the display context was reset.

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




<a href="https://msdn.microsoft.com/library/windows/hardware/ff548436">D3DKMT_WAITFORSYNCHRONIZATIONOBJECT2</a>
 

 

