---
UID: NC:d3dumddi.PFND3DDDI_LOCKASYNC
title: PFND3DDDI_LOCKASYNC
author: windows-driver-content
description: The LockAsync function locks the specified resource or a surface within the resource.
old-location: display\lockasync.htm
tech.root: display
ms.assetid: c8f76ebe-947a-45e4-abbc-f6020da929e8
ms.date: 05/10/2018
ms.keywords: LockAsync, LockAsync callback function [Display Devices], PFND3DDDI_LOCKASYNC, PFND3DDDI_LOCKASYNC callback, UserModeDisplayDriver_Functions_da747d8a-9e58-47e7-b2eb-bd84179bde2d.xml, d3dumddi/LockAsync, display.lockasync
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
-	LockAsync
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFND3DDDI_LOCKASYNC callback function


## -description


The <i>LockAsync</i> function locks the specified resource or a surface within the resource. 


## -parameters




### -param hDevice [in]

A handle to the display device (graphics context).


### -param *








*pData* [in, out]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff543213">D3DDDIARG_LOCKASYNC</a> structure that describes the resource or surface within the resource to lock.


## -returns



<i>LockAsync</i> returns one of the following values:

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
The resource is successfully locked.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>
</td>
<td width="60%">
<i>LockAsync</i> could not allocate the required memory for it to complete.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>D3DDDIERR_WASSTILLDRAWING</b></dt>
</dl>
</td>
<td width="60%">
Renaming the allocation that corresponds to the resource that the <a href="https://msdn.microsoft.com/library/windows/hardware/ff543213">D3DDDIARG_LOCKASYNC</a> structure specifies failed. 

The driver returns this value only if the <b>Discard</b> bit-field flag was set in the <b>Flags</b> member of D3DDDIARG_LOCKASYNC.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_NOTIMPL</b></dt>
</dl>
</td>
<td width="60%">
The user-mode display driver does not support <i>LockAsync</i> for the specified resource.

</td>
</tr>
</table>
 




## -remarks



On multiple-processor computers, the Microsoft Direct3D runtime might call most functions of the user-mode display driver from a worker thread instead of from the main application thread. This multiple-processor optimization is transparent to the user-mode display driver. When the runtime uses multiple-processor optimization, it might call <i>LockAsync</i> rather than the <a href="https://msdn.microsoft.com/e2289073-d46a-4a12-8de7-30400e04cc22">Lock</a> function to lock a resource. 

A user-mode display driver optionally implements <i>LockAsync</i>; the Direct3D runtime calls <i>LockAsync</i> only if the driver implements the <i>LockAsync</i>, <a href="https://msdn.microsoft.com/6af04c22-e559-4328-a20a-034b443fddc6">UnlockAsync</a>, and <a href="https://msdn.microsoft.com/60f733e1-d376-4372-b1cc-39508b3a98e5">Rename</a> functions. However, a user-mode display driver should implement <i>LockAsync</i> and the <i>UnlockAsync</i> and <i>Rename</i> functions because applications that frequently lock dynamic resources can then achieve higher performance. 

When the Direct3D runtime uses multiple-processor optimization, it calls most user-mode display driver functions from a worker thread that the runtime manages; however, the runtime calls <i>LockAsync</i> on the application's main thread. 

If a user-mode display driver exposes a DDI version of 0x0000000B or greater (the driver returns this value in the DriverVersion member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff541724">D3D10DDIARG_OPENADAPTER</a> structure in a call to the driver's <a href="https://msdn.microsoft.com/41dc9ee4-e9bc-4ebd-9b90-6446ded6ea16">OpenAdapter</a> function), the Direct3D runtime will call LockAsync in a reentrant manner. When the runtime calls LockAsync in a reentrant manner, one thread can execute inside LockAsync while another thread that references the same display device executes inside of another user-mode display driver function. Additionally, on this type of driver, the runtime will call LockAsync for system memory surfaces. If the <b>Discard</b> bit-field flag is set in the <b>Flags</b> member of <a href="https://msdn.microsoft.com/library/windows/hardware/ff543213">D3DDDIARG_LOCKASYNC</a>, the driver should attempt to rename the allocation that corresponds to the resource. Typically, to rename an allocation, the driver calls the <a href="https://msdn.microsoft.com/69022797-432a-410b-8cbf-e1ef7111e7ea">pfnLockCb</a> function with the allocation handle that corresponds to the resource to be locked. 

The driver should set the <b>Discard</b> bit-field flag in the <b>Flags</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544205">D3DDDICB_LOCK</a> structure when the driver calls <b>pfnLockCb</b>. The driver should set the <b>NoExistingReference</b> bit-field flag of D3DDDICB_LOCK when the driver calls <b>pfnLockCb</b> only if the <b>NoExistingReferences</b> bit-field flag is set to <b>TRUE</b> in the <b>Flags</b> member of D3DDDIARG_LOCKASYNC, and the driver has no internally queued references to the resource. 

If the driver fails to rename the allocation, the driver's <i>LockAsync</i> function should return the failure back to the runtime, and the driver should not flush its command buffer. If the renaming succeeds, the driver should return pointers to resource memory, pitch, and slice pitch and a handle to the resource that represents the renamed allocation in the members of <a href="https://msdn.microsoft.com/library/windows/hardware/ff543213">D3DDDIARG_LOCKASYNC</a>. The driver should not update its internal tracking structures with the new allocation handle that <b>pfnLockCb</b> returns. Instead, the driver should wait until its <a href="https://msdn.microsoft.com/60f733e1-d376-4372-b1cc-39508b3a98e5">Rename</a> function is called. 

If the <b>NoOverwrite</b> bit-field flag is set in the <b>Flags</b> member of D3DDDIARG_LOCKASYNC, the driver should lock the corresponding allocation with no-overwrite semantics. The driver should call <a href="https://msdn.microsoft.com/69022797-432a-410b-8cbf-e1ef7111e7ea">pfnLockCb</a> with the <b>IgnoreSync</b> bit-field flag set in the <b>Flags</b> member of <a href="https://msdn.microsoft.com/library/windows/hardware/ff544205">D3DDDICB_LOCK</a> and should then return pointers to resource memory, pitch, and slice pitch to the Direct3D runtime in the members of <a href="https://msdn.microsoft.com/library/windows/hardware/ff543213">D3DDDIARG_LOCKASYNC</a>. If the driver returns success (S_OK) from a call to its <i>LockAsync</i> with the <b>NoOverwrite</b> bit-field flag set, it might be called to render with a locked surface. The driver should return success from a call to its <i>LockAsync</i> with <b>NoOverwrite</b> set only for surfaces that can be rendered while locked. The video memory manager requires that the allocations that correspond to the surfaces must be supported in AGP or aperture segments; otherwise, calls to the <b>pfnRenderCb</b> function fail when the command buffer references a locked allocation.

In summary, the driver should fail calls to its <i>LockAsync</i> function if renaming fails or if no-overwrite semantics are not supported for the resource. However, the Direct3D runtime will recover from these failures. For all other situations, drivers should return success from <i>LockAsync</i> to improve performance on multiple-processor computers.




## -see-also




<a href="https://msdn.microsoft.com/5b74c989-1a62-4415-a19a-dd0ba2fcff83">CreateResource</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542963">D3DDDIARG_CREATERESOURCE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543213">D3DDDIARG_LOCKASYNC</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544205">D3DDDICB_LOCK</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544519">D3DDDI_DEVICEFUNCS</a>



<a href="https://msdn.microsoft.com/e2289073-d46a-4a12-8de7-30400e04cc22">Lock</a>



<a href="https://msdn.microsoft.com/60f733e1-d376-4372-b1cc-39508b3a98e5">Rename</a>



<a href="https://msdn.microsoft.com/6af04c22-e559-4328-a20a-034b443fddc6">UnlockAsync</a>



<a href="https://msdn.microsoft.com/69022797-432a-410b-8cbf-e1ef7111e7ea">pfnLockCb</a>



<a href="https://msdn.microsoft.com/f242162e-6237-469c-b178-5a51dcf69e32">pfnRenderCb</a>
 

 

