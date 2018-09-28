---
UID: NF:d3dkmthk.D3DKMTWaitForSynchronizationObject
title: D3DKMTWaitForSynchronizationObject function
author: windows-driver-content
description: The D3DKMTWaitForSynchronizationObject function inserts a wait for the specified synchronization objects in the specified context stream.
old-location: display\d3dkmtwaitforsynchronizationobject.htm
ms.assetid: 6b622b61-ec39-4ffb-b744-2b33ac560af6
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: D3DKMTWaitForSynchronizationObject, D3DKMTWaitForSynchronizationObject function [Display Devices], OpenGL_Functions_bdec46cd-1e3b-427f-8c65-df2d31171bc5.xml, d3dkmthk/D3DKMTWaitForSynchronizationObject, display.d3dkmtwaitforsynchronizationobject
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
-	D3DKMTWaitForSynchronizationObject
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# D3DKMTWaitForSynchronizationObject function


## -description


The <b>D3DKMTWaitForSynchronizationObject</b> function inserts a wait for the specified synchronization objects in the specified context stream.


## -parameters




### -param D3DKMT_WAITFORSYNCHRONIZATIONOBJECT






*pData* [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff548430">D3DKMT_WAITFORSYNCHRONIZATIONOBJECT</a> structure that describes the synchronization objects and context stream that the wait is set up for.


## -returns



<b>D3DKMTWaitForSynchronizationObject</b> returns one of the following values:

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




<a href="https://msdn.microsoft.com/library/windows/hardware/ff548430">D3DKMT_WAITFORSYNCHRONIZATIONOBJECT</a>
 

 

