---
UID: NF:d3dkmthk.D3DKMTCreateContext
title: D3DKMTCreateContext function
author: windows-driver-content
description: The D3DKMTCreateContext function creates a kernel-mode device context.
old-location: display\d3dkmtcreatecontext.htm
old-project: display
ms.assetid: e30fd034-1268-45bf-bc9c-df33e642fd4e
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3DKMTCreateContext, D3DKMTCreateContext callback function [Display Devices], OpenGL_Functions_ee92f6d8-b9af-4171-a628-e686f190a370.xml, PFND3DKMT_CREATECONTEXT, d3dkmthk/D3DKMTCreateContext, display.d3dkmtcreatecontext
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
req.lib: NtosKrnl.exe
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
product: Windows
targetos: Windows
req.typenames: D3DKMT_DRIVERVERSION
---

# D3DKMTCreateContext function


## -description


The <b>D3DKMTCreateContext</b> function creates a kernel-mode device context.


## -syntax


````
NTSTATUS D3DKMTCreateContext(
  _Inout_ D3DKMT_CREATECONTEXT *pData
);
````


## -parameters






#### - pData [in, out]

A pointer to a <a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_createcontext.md">D3DKMT_CREATECONTEXT</a> structure that describes the kernel-mode device context.


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

<a href="..\d3dkmthk\nc-d3dkmthk-pfnd3dkmt_createcontext.md">D3DKMTCreateContext</a> could not complete because of insufficient memory.

</td>
</tr>
</table>
 

This function might also return other <b>NTSTATUS</b> values.




## -see-also

<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_createcontext.md">D3DKMT_CREATECONTEXT</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DKMT_CREATECONTEXT callback function%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

