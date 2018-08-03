---
UID: NC:d3dkmthk.PFND3DKMT_CREATECONTEXT
title: PFND3DKMT_CREATECONTEXT
author: windows-driver-content
description: The D3DKMTCreateContext function creates a kernel-mode device context.
old-location: display\d3dkmtcreatecontext.htm
tech.root: display
ms.assetid: e30fd034-1268-45bf-bc9c-df33e642fd4e
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: D3DKMTCreateContext, D3DKMTCreateContext callback function [Display Devices], OpenGL_Functions_ee92f6d8-b9af-4171-a628-e686f190a370.xml, PFND3DKMT_CREATECONTEXT, PFND3DKMT_CREATECONTEXT callback, d3dkmthk/D3DKMTCreateContext, display.d3dkmtcreatecontext
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
-	D3DKMTCreateContext
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFND3DKMT_CREATECONTEXT callback function


## -description


The <b>D3DKMTCreateContext</b> function creates a kernel-mode device context.


## -parameters




### -param *








#### - pData [in, out]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff547810">D3DKMT_CREATECONTEXT</a> structure that describes the kernel-mode device context.


## -returns



<b>D3DKMTCreateContext</b> returns one of the following values:

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
The device context was successfully created.

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

<a href="https://msdn.microsoft.com/library/windows/hardware/ff546814">D3DKMTCreateContext</a> could not complete because of insufficient memory.

</td>
</tr>
</table>
 

This function might also return other <b>NTSTATUS</b> values.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff547810">D3DKMT_CREATECONTEXT</a>
 

 

