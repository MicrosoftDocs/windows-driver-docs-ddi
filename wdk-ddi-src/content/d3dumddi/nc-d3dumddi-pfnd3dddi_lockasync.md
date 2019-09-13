---
UID: NC:d3dumddi.PFND3DDDI_LOCKASYNC
title: PFND3DDDI_LOCKASYNC (d3dumddi.h)
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
targetos: Windows
req.typenames: 
f1_keywords:
 - "d3dumddi/LockAsync"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dumddi.h
api_name:
 - LockAsync
product:
 - Windows
---

# PFND3DDDI_LOCKASYNC callback function

## -description

The <i>LockAsync</i> function locks the specified resource or a surface within the resource.

## -parameters

### -param hDevice

A handle to the display device (graphics context).

### -param Arg2

*pData* [in, out]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/ns-d3dumddi-_d3dddiarg_lockasync">D3DDDIARG_LOCKASYNC</a> structure that describes the resource or surface within the resource to lock.

## -returns

<i>LockAsync</i> returns one of the following values:

| **Return code** | **Description** | 
|:--|:--|
| **S_OK** | The resource is successfully locked. | 
| **E_OUTOFMEMORY** | LockAsync could not allocate the required memory for it to complete. | 
| **D3DDDIERR_WASSTILLDRAWING** | Renaming the allocation that corresponds to the resource that the [D3DDDIARG_LOCKASYNC](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/ns-d3dumddi-_d3dddiarg_lockasync)  structure specifies failed.<br/>The driver returns this value only if the Discard bit-field flag was set in the Flags member of D3DDDIARG_LOCKASYNC. | 
| **E_NOTIMPL** | The user-mode display driver does not support LockAsync for the specified resource. |

## -remarks

On multiple-processor computers, the Microsoft Direct3D runtime might call most functions of the user-mode display driver from a worker thread instead of from the main application thread. This multiple-processor optimization is transparent to the user-mode display driver. When the runtime uses multiple-processor optimization, it might call <i>LockAsync</i> rather than the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/nc-d3dumddi-pfnd3dddi_lock">Lock</a> function to lock a resource. 

A user-mode display driver optionally implements <i>LockAsync</i>; the Direct3D runtime calls <i>LockAsync</i> only if the driver implements the <i>LockAsync</i>, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/nc-d3dumddi-pfnd3dddi_unlockasync">UnlockAsync</a>, and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/nc-d3dumddi-pfnd3dddi_rename">Rename</a> functions. However, a user-mode display driver should implement <i>LockAsync</i> and the <i>UnlockAsync</i> and <i>Rename</i> functions because applications that frequently lock dynamic resources can then achieve higher performance. 

When the Direct3D runtime uses multiple-processor optimization, it calls most user-mode display driver functions from a worker thread that the runtime manages; however, the runtime calls <i>LockAsync</i> on the application's main thread. 

If a user-mode display driver exposes a DDI version of 0x0000000B or greater (the driver returns this value in the DriverVersion member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/ns-d3d10umddi-d3d10ddiarg_openadapter">D3D10DDIARG_OPENADAPTER</a> structure in a call to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/nc-d3dumddi-pfnd3dddi_openadapter">OpenAdapter</a> function), the Direct3D runtime will call LockAsync in a reentrant manner. When the runtime calls LockAsync in a reentrant manner, one thread can execute inside LockAsync while another thread that references the same display device executes inside of another user-mode display driver function. Additionally, on this type of driver, the runtime will call LockAsync for system memory surfaces. If the <b>Discard</b> bit-field flag is set in the <b>Flags</b> member of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/ns-d3dumddi-_d3dddiarg_lockasync">D3DDDIARG_LOCKASYNC</a>, the driver should attempt to rename the allocation that corresponds to the resource. Typically, to rename an allocation, the driver calls the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/nc-d3dumddi-pfnd3dddi_lockcb">pfnLockCb</a> function with the allocation handle that corresponds to the resource to be locked. 

The driver should set the <b>Discard</b> bit-field flag in the <b>Flags</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/ns-d3dumddi-_d3dddicb_lock">D3DDDICB_LOCK</a> structure when the driver calls <b>pfnLockCb</b>. The driver should set the <b>NoExistingReference</b> bit-field flag of D3DDDICB_LOCK when the driver calls <b>pfnLockCb</b> only if the <b>NoExistingReferences</b> bit-field flag is set to <b>TRUE</b> in the <b>Flags</b> member of D3DDDIARG_LOCKASYNC, and the driver has no internally queued references to the resource. 

If the driver fails to rename the allocation, the driver's <i>LockAsync</i> function should return the failure back to the runtime, and the driver should not flush its command buffer. If the renaming succeeds, the driver should return pointers to resource memory, pitch, and slice pitch and a handle to the resource that represents the renamed allocation in the members of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/ns-d3dumddi-_d3dddiarg_lockasync">D3DDDIARG_LOCKASYNC</a>. The driver should not update its internal tracking structures with the new allocation handle that <b>pfnLockCb</b> returns. Instead, the driver should wait until its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/nc-d3dumddi-pfnd3dddi_rename">Rename</a> function is called. 

If the <b>NoOverwrite</b> bit-field flag is set in the <b>Flags</b> member of D3DDDIARG_LOCKASYNC, the driver should lock the corresponding allocation with no-overwrite semantics. The driver should call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/nc-d3dumddi-pfnd3dddi_lockcb">pfnLockCb</a> with the <b>IgnoreSync</b> bit-field flag set in the <b>Flags</b> member of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/ns-d3dumddi-_d3dddicb_lock">D3DDDICB_LOCK</a> and should then return pointers to resource memory, pitch, and slice pitch to the Direct3D runtime in the members of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/ns-d3dumddi-_d3dddiarg_lockasync">D3DDDIARG_LOCKASYNC</a>. If the driver returns success (S_OK) from a call to its <i>LockAsync</i> with the <b>NoOverwrite</b> bit-field flag set, it might be called to render with a locked surface. The driver should return success from a call to its <i>LockAsync</i> with <b>NoOverwrite</b> set only for surfaces that can be rendered while locked. The video memory manager requires that the allocations that correspond to the surfaces must be supported in AGP or aperture segments; otherwise, calls to the <b>pfnRenderCb</b> function fail when the command buffer references a locked allocation.

In summary, the driver should fail calls to its <i>LockAsync</i> function if renaming fails or if no-overwrite semantics are not supported for the resource. However, the Direct3D runtime will recover from these failures. For all other situations, drivers should return success from <i>LockAsync</i> to improve performance on multiple-processor computers.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/nc-d3dumddi-pfnd3dddi_createresource">CreateResource</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dukmdt/ns-d3dukmdt-_d3dddiarg_createresource">D3DDDIARG_CREATERESOURCE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/ns-d3dumddi-_d3dddiarg_lockasync">D3DDDIARG_LOCKASYNC</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/ns-d3dumddi-_d3dddicb_lock">D3DDDICB_LOCK</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/ns-d3dumddi-_d3dddi_devicefuncs">D3DDDI_DEVICEFUNCS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/nc-d3dumddi-pfnd3dddi_lock">Lock</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/nc-d3dumddi-pfnd3dddi_rename">Rename</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/nc-d3dumddi-pfnd3dddi_unlockasync">UnlockAsync</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/nc-d3dumddi-pfnd3dddi_lockcb">pfnLockCb</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/nc-d3dumddi-pfnd3dddi_rendercb">pfnRenderCb</a>

