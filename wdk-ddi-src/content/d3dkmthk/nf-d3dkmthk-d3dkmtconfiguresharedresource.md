---
UID: NF:d3dkmthk.D3DKMTConfigureSharedResource
title: D3DKMTConfigureSharedResource function
author: windows-driver-content
description: The D3DKMTConfigureSharedResource function configures a shared resource.
old-location: display\d3dkmtconfiguresharedresource.htm
tech.root: display
ms.assetid: 3664ef23-f7bc-4a94-8085-aa5a3d0ba550
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: D3DKMTConfigureSharedResource, D3DKMTConfigureSharedResource callback function [Display Devices], OpenGL_Functions_f95f6a64-49a7-4a93-a544-6d4315f12212.xml, PFND3DKMT_CONFIGURESHAREDRESOURCE, PFND3DKMT_CONFIGURESHAREDRESOURCE callback, d3dkmthk/D3DKMTConfigureSharedResource, display.d3dkmtconfiguresharedresource
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Universal
req.target-min-winverclnt: D3DKMTConfigureSharedResource is supported beginning with the Windows 7 operating system.
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
-	D3DKMTConfigureSharedResource
product:
- Windows
targetos: Windows
req.typenames: 
---

# D3DKMTConfigureSharedResource function


## -description


The <b>D3DKMTConfigureSharedResource</b> function configures a shared resource. 


## -parameters




### -param D3DKMT_CONFIGURESHAREDRESOURCE

TBD




#### - pData [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff547793">D3DKMT_CONFIGURESHAREDRESOURCE</a> structure that specifies parameters to configure the shared resource. 


## -returns



<b>D3DKMTConfigureSharedResource</b> returns one of the following values:

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
The shared resource was successfully configured. 

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

<a href="https://msdn.microsoft.com/library/windows/hardware/ff546798">D3DKMTConfigureSharedResource</a> could not complete because of insufficient memory.

</td>
</tr>
</table>
 

This function might also return other <b>NTSTATUS</b> values.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff547793">D3DKMT_CONFIGURESHAREDRESOURCE</a>
 

 

