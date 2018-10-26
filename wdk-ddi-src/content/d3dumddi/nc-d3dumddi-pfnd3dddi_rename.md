---
UID: NC:d3dumddi.PFND3DDDI_RENAME
title: PFND3DDDI_RENAME
author: windows-driver-content
description: The Rename function informs a user-mode display driver to start using the renamed allocation that the LockAsync function previously returned for the specified resource.
old-location: display\rename.htm
tech.root: display
ms.assetid: 60f733e1-d376-4372-b1cc-39508b3a98e5
ms.date: 05/10/2018
ms.keywords: PFND3DDDI_RENAME, PFND3DDDI_RENAME callback, Rename, Rename callback function [Display Devices], UserModeDisplayDriver_Functions_50916fb2-ea0e-4143-8588-909a4cd07bec.xml, d3dumddi/Rename, display.rename
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3dumddi.h
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
-	d3dumddi.h
api_name:
-	Rename
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFND3DDDI_RENAME callback function


## -description


The <i>Rename</i> function informs a user-mode display driver to start using the renamed allocation that the <a href="https://msdn.microsoft.com/c8f76ebe-947a-45e4-abbc-f6020da929e8">LockAsync</a> function previously returned for the specified resource.


## -parameters




### -param hDevice [in]

A handle to a display device (that is, the graphics context).


### -param *








*pData* [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff543262">D3DDDIARG_RENAME</a> structure that describes the resource or surface within a resource to rename with a new allocation.


## -returns



<i>Rename</i> returns one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
The resource is successfully renamed.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>
</td>
<td width="60%">
<i>Rename</i> could not allocate the required memory for it to complete.

</td>
</tr>
</table>
 




## -remarks



On multiple-processor computers, the Microsoft Direct3D runtime calls the user-mode display driver's <i>Rename</i> function from a worker thread instead of from the main application thread. The runtime calls <i>Rename</i>, at most, once for each successful call to the driver's <a href="https://msdn.microsoft.com/c8f76ebe-947a-45e4-abbc-f6020da929e8">LockAsync</a> function with the <b>Discard</b> bit-field flag set in the <b>Flags</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff543213">D3DDDIARG_LOCKASYNC</a> structure that the <i>pData</i> parameter of <i>LockAsync</i> points to. 

<i>Rename</i> informs the driver to start using the renamed allocation that is specified by the <b>hCookie</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff543262">D3DDDIARG_RENAME</a> structure that the <i>pData</i> parameter of <i>Rename</i> points to. The <b>hCookie</b> handle was previously returned by the <a href="https://msdn.microsoft.com/c8f76ebe-947a-45e4-abbc-f6020da929e8">LockAsync</a> function if the <b>Discard</b> bit-field flag was set for the locked resource. 

After <i>Rename</i> returns successfully (with S_OK), the user-mode display driver should use the allocation that <b>hCookie</b> specifies for all rendering operations that reference the resource that the <b>hResource</b> and <b>SubResourceIndex</b> members of D3DDDIARG_RENAME specify.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff543213">D3DDDIARG_LOCKASYNC</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543262">D3DDDIARG_RENAME</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544519">D3DDDI_DEVICEFUNCS</a>



<a href="https://msdn.microsoft.com/c8f76ebe-947a-45e4-abbc-f6020da929e8">LockAsync</a>



<a href="https://msdn.microsoft.com/60f733e1-d376-4372-b1cc-39508b3a98e5">Rename</a>
 

 

