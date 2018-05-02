---
UID: NF:d3dkmthk.D3DKMTCreateSynchronizationObject2
title: D3DKMTCreateSynchronizationObject2 function
author: windows-driver-content
description: The D3DKMTCreateSynchronizationObject2 function creates a kernel-mode synchronization object.
old-location: display\d3dkmtcreatesynchronizationobject2.htm
old-project: display
ms.assetid: 45849844-a466-4e62-957a-bfe33a464b5a
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: D3DKMTCreateSynchronizationObject2, D3DKMTCreateSynchronizationObject2 function [Display Devices], OpenGL_Functions_ba9aa4a0-19e6-40d2-8a17-d22c8756c555.xml, d3dkmthk/D3DKMTCreateSynchronizationObject2, display.d3dkmtcreatesynchronizationobject2
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Universal
req.target-min-winverclnt: D3DKMTCreateSynchronizationObject2 is supported beginning with the Windows 7 operating system.
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
-	D3DKMTCreateSynchronizationObject2
product:
- Windows
targetos: Windows
req.typenames: 
---

# D3DKMTCreateSynchronizationObject2 function


## -description


The <b>D3DKMTCreateSynchronizationObject2</b> function creates a kernel-mode synchronization object.


## -parameters




### -param Arg1

TBD




#### - pData [in, out]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff547854">D3DKMT_CREATESYNCHRONIZATIONOBJECT2</a> structure that describes a synchronization object.


## -returns



<b>D3DKMTCreateSynchronizationObject2</b> returns one of the following values:

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
The kernel-mode synchronization object was successfully created.

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
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NO_MEMORY</b></dt>
</dl>
</td>
<td width="60%">

<a href="https://msdn.microsoft.com/library/windows/hardware/ff546879">D3DKMTCreateSynchronizationObject2</a> could not complete because of insufficient memory.

</td>
</tr>
</table>
 

This function might also return other <b>NTSTATUS</b> values.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff547854">D3DKMT_CREATESYNCHRONIZATIONOBJECT2</a>
 

 

