---
UID: NF:d3dkmthk.D3DKMTCreateSynchronizationObject
title: D3DKMTCreateSynchronizationObject function
author: windows-driver-content
description: The D3DKMTCreateSynchronizationObject function creates a kernel-mode synchronization object.
old-location: display\d3dkmtcreatesynchronizationobject.htm
old-project: display
ms.assetid: c91686dc-1c6a-4d21-84e8-fd8a2803ff4e
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: D3DKMTCreateSynchronizationObject, D3DKMTCreateSynchronizationObject function [Display Devices], OpenGL_Functions_505065c6-f259-4518-adb8-f7d0fa6b56a5.xml, d3dkmthk/D3DKMTCreateSynchronizationObject, display.d3dkmtcreatesynchronizationobject
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
-	D3DKMTCreateSynchronizationObject
product:
- Windows
targetos: Windows
req.typenames: 
---

# D3DKMTCreateSynchronizationObject function


## -description


The <b>D3DKMTCreateSynchronizationObject</b> function creates a kernel-mode synchronization object.


## -parameters




### -param Arg1

TBD




#### - pData [in, out]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff547849">D3DKMT_CREATESYNCHRONIZATIONOBJECT</a> structure that describes a synchronization object.


## -returns



<b>D3DKMTCreateSynchronizationObject</b> returns one of the following values:

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

<a href="https://msdn.microsoft.com/library/windows/hardware/ff546869">D3DKMTCreateSynchronizationObject</a> could not complete because of insufficient memory.

</td>
</tr>
</table>
 

This function might also return other <b>NTSTATUS</b> values.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff547849">D3DKMT_CREATESYNCHRONIZATIONOBJECT</a>
 

 

