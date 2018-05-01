---
UID: NF:d3dkmthk.D3DKMTCreateKeyedMutex
title: D3DKMTCreateKeyedMutex function
author: windows-driver-content
description: The D3DKMTCreateKeyedMutex function creates a keyed mutex object.
old-location: display\d3dkmtcreatekeyedmutex.htm
old-project: display
ms.assetid: ae9e4771-ba8d-4472-aeb8-04c3f3c59efa
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: D3DKMTCreateKeyedMutex, D3DKMTCreateKeyedMutex callback function [Display Devices], OpenGL_Functions_a8475da1-40bf-4669-9da8-f6bb09c3f905.xml, PFND3DKMT_CREATEKEYEDMUTEX, PFND3DKMT_CREATEKEYEDMUTEX callback, d3dkmthk/D3DKMTCreateKeyedMutex, display.d3dkmtcreatekeyedmutex
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Universal
req.target-min-winverclnt: D3DKMTCreateKeyedMutex is supported beginning with the Windows 7 operating system.
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	d3dkmthk.h
api_name:
-	D3DKMTCreateKeyedMutex
product: Windows
targetos: Windows
req.typenames: 
---

# D3DKMTCreateKeyedMutex function


## -description


The <b>D3DKMTCreateKeyedMutex</b> function creates a keyed mutex object.


## -parameters




### -param Arg1

TBD




#### - pData [in, out]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff547834">D3DKMT_CREATEKEYEDMUTEX</a> structure that describes a keyed mutex object to create. 


## -returns



<b>D3DKMTCreateKeyedMutex</b> returns one of the following values:

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
The keyed mutex object was successfully created. 

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

<a href="https://msdn.microsoft.com/library/windows/hardware/ff546845">D3DKMTCreateKeyedMutex</a> could not complete because of insufficient memory.

</td>
</tr>
</table>
 

This function might also return other <b>NTSTATUS</b> values.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff547834">D3DKMT_CREATEKEYEDMUTEX</a>
 

 

