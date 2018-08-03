---
UID: NC:d3dumddi.PFND3DDDI_UNLOCKASYNC
title: PFND3DDDI_UNLOCKASYNC
author: windows-driver-content
description: The UnlockAsync function unlocks a resource or a surface within the resource that the LockAsync function previously locked.
old-location: display\unlockasync.htm
tech.root: display
ms.assetid: 6af04c22-e559-4328-a20a-034b443fddc6
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: PFND3DDDI_UNLOCKASYNC, PFND3DDDI_UNLOCKASYNC callback, UnlockAsync, UnlockAsync callback function [Display Devices], UserModeDisplayDriver_Functions_f2270e47-4bf2-4486-8e6b-919daabd7c48.xml, d3dumddi/UnlockAsync, display.unlockasync
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
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
-	UnlockAsync
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFND3DDDI_UNLOCKASYNC callback function


## -description


The <i>UnlockAsync</i> function unlocks a resource or a surface within the resource that the <a href="https://msdn.microsoft.com/c8f76ebe-947a-45e4-abbc-f6020da929e8">LockAsync</a> function previously locked.


## -parameters




### -param hDevice [in]

 A handle to a display device (that is, the graphics context).


### -param *








#### - pData [in]

 A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff543395">D3DDDIARG_UNLOCKASYNC</a> structure that describes the resource or surface within the resource to unlock.


## -returns



<i>UnlockAsync</i> returns one of the following values:

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
The resource is successfully unlocked.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>
</td>
<td width="60%">
<i>UnlockAsync</i> could not allocate the required memory for it to complete.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_INVALIDARG</b></dt>
</dl>
</td>
<td width="60%">
The resource that <a href="https://msdn.microsoft.com/library/windows/hardware/ff543395">D3DDDIARG_UNLOCKASYNC</a> describes was not locked by a previous call to the driver's <a href="https://msdn.microsoft.com/c8f76ebe-947a-45e4-abbc-f6020da929e8">LockAsync</a> function. 

</td>
</tr>
</table>
 




## -remarks



A user-mode display driver should call the <a href="https://msdn.microsoft.com/6684f350-da27-478d-ab7b-36e395f7df8d">pfnUnlockCb</a> function with the appropriate allocation handle after the <i>UnlockAsync</i> function is called. 

A user-mode display driver optionally implements <i>UnlockAsync</i>; the Microsoft Direct3D runtime calls <i>UnlockAsync</i> only if the driver implements the <a href="https://msdn.microsoft.com/c8f76ebe-947a-45e4-abbc-f6020da929e8">LockAsync</a>, <i>UnlockAsync</i>, and <a href="https://msdn.microsoft.com/60f733e1-d376-4372-b1cc-39508b3a98e5">Rename</a> functions. 

Like <a href="https://msdn.microsoft.com/c8f76ebe-947a-45e4-abbc-f6020da929e8">LockAsync</a>, <i>UnlockAsync</i> is called on the main application thread while most other calls to the user-mode display driver functions are made on a worker thread (on multiple-processor computers). 

If a user-mode display driver exposes a DDI version of 0x0000000B or greater (the driver returns this value in the <b>DriverVersion</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff541724">D3D10DDIARG_OPENADAPTER</a> structure in a call to the driver's <a href="https://msdn.microsoft.com/41dc9ee4-e9bc-4ebd-9b90-6446ded6ea16">OpenAdapter</a> function), the Direct3D runtime will call <i>UnlockAsync</i> in a reentrant manner. When the runtime calls <i>UnlockAsync</i> in a reentrant manner, one thread can execute inside <i>UnlockAsync</i> while another thread that references the same display device executes inside of another user-mode display driver function. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff543395">D3DDDIARG_UNLOCKASYNC</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544519">D3DDDI_DEVICEFUNCS</a>



<a href="https://msdn.microsoft.com/c8f76ebe-947a-45e4-abbc-f6020da929e8">LockAsync</a>



<a href="https://msdn.microsoft.com/60f733e1-d376-4372-b1cc-39508b3a98e5">Rename</a>



<a href="https://msdn.microsoft.com/6684f350-da27-478d-ab7b-36e395f7df8d">pfnUnlockCb</a>
 

 

