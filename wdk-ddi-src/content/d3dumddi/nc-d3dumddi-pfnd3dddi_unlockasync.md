---
UID: NC:d3dumddi.PFND3DDDI_UNLOCKASYNC
title: PFND3DDDI_UNLOCKASYNC (d3dumddi.h)
description: The UnlockAsync function unlocks a resource or a surface within the resource that the LockAsync function previously locked.
old-location: display\unlockasync.htm
tech.root: display
ms.assetid: 6af04c22-e559-4328-a20a-034b443fddc6
ms.date: 05/10/2018
ms.keywords: PFND3DDDI_UNLOCKASYNC, PFND3DDDI_UNLOCKASYNC callback, UnlockAsync, UnlockAsync callback function [Display Devices], UserModeDisplayDriver_Functions_f2270e47-4bf2-4486-8e6b-919daabd7c48.xml, d3dumddi/UnlockAsync, display.unlockasync
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
 - "d3dumddi/UnlockAsync"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dumddi.h
api_name:
 - UnlockAsync
product:
 - Windows
---

# PFND3DDDI_UNLOCKASYNC callback function

## -description

The <i>UnlockAsync</i> function unlocks a resource or a surface within the resource that the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_lockasync">LockAsync</a> function previously locked.

## -parameters

### -param hDevice

A handle to a display device (that is, the graphics context).

### -param Arg2

*pData* [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_unlockasync">D3DDDIARG_UNLOCKASYNC</a> structure that describes the resource or surface within the resource to unlock.

## -returns

<i>UnlockAsync</i> returns one of the following values:

| **Return code** | **Description** | 
|:--|:--|
| **S_OK** | The resource is successfully unlocked. | 
| **E_OUTOFMEMORY** | UnlockAsync could not allocate the required memory for it to complete. | 
| **E_INVALIDARG** | The resource that [D3DDDIARG_UNLOCKASYNC](https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_unlockasync)  describes was not locked by a previous call to the driver's [LockAsync](https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_lockasync)  function. |

## -remarks

A user-mode display driver should call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_unlockcb">pfnUnlockCb</a> function with the appropriate allocation handle after the <i>UnlockAsync</i> function is called. 

A user-mode display driver optionally implements <i>UnlockAsync</i>; the Microsoft Direct3D runtime calls <i>UnlockAsync</i> only if the driver implements the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_lockasync">LockAsync</a>, <i>UnlockAsync</i>, and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_rename">Rename</a> functions. 

Like <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_lockasync">LockAsync</a>, <i>UnlockAsync</i> is called on the main application thread while most other calls to the user-mode display driver functions are made on a worker thread (on multiple-processor computers). 

If a user-mode display driver exposes a DDI version of 0x0000000B or greater (the driver returns this value in the <b>DriverVersion</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddiarg_openadapter">D3D10DDIARG_OPENADAPTER</a> structure in a call to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_openadapter">OpenAdapter</a> function), the Direct3D runtime will call <i>UnlockAsync</i> in a reentrant manner. When the runtime calls <i>UnlockAsync</i> in a reentrant manner, one thread can execute inside <i>UnlockAsync</i> while another thread that references the same display device executes inside of another user-mode display driver function.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_unlockasync">D3DDDIARG_UNLOCKASYNC</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddi_devicefuncs">D3DDDI_DEVICEFUNCS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_lockasync">LockAsync</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_rename">Rename</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_unlockcb">pfnUnlockCb</a>

