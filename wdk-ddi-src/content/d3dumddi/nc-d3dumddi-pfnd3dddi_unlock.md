---
UID: NC:d3dumddi.PFND3DDDI_UNLOCK
title: PFND3DDDI_UNLOCK (d3dumddi.h)
description: The Unlock function unlocks a resource or a surface within the resource that was previously locked by the Lock function.
old-location: display\unlock.htm
tech.root: display
ms.assetid: 23cc9c64-99d4-4602-a1b0-234fe7fcc3da
ms.date: 05/10/2018
ms.keywords: PFND3DDDI_UNLOCK, PFND3DDDI_UNLOCK callback, Unlock, Unlock callback function [Display Devices], UserModeDisplayDriver_Functions_20b0d6f7-4bda-4d0f-9c3a-27d4011d2591.xml, d3dumddi/Unlock, display.unlock
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
targetos: Windows
req.typenames: 
f1_keywords:
 - "d3dumddi/Unlock"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dumddi.h
api_name:
 - Unlock
product:
 - Windows
---

# PFND3DDDI_UNLOCK callback function

## -description

The <i>Unlock</i> function unlocks a resource or a surface within the resource that was previously locked by the <i>Lock</i> function.

## -parameters

### -param hDevice

A handle to the display device (graphics context).

### -param Arg2

*pData* [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/ns-d3dumddi-_d3dddiarg_unlock">D3DDDIARG_UNLOCK</a> structure that describes the resource or surface within the resource to unlock.

## -returns

<i>Unlock</i> returns one of the following values:

| **Return code** | **Description** | 
|:--|:--|
| **S_OK** | The resource is successfully unlocked. | 
| **E_OUTOFMEMORY** | Unlock could not allocate the required memory for it to complete. | 
| **E_INVALIDARG** | The resource that [D3DDDIARG_UNLOCK](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/ns-d3dumddi-_d3dddiarg_unlock) describes was not locked by a previous call to the driver's [Lock](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/nc-d3dumddi-pfnd3dddi_lock)  function. |

## -remarks

These comments are analogous to the description in the Remarks section of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/nc-d3dumddi-pfnd3dddi_lock">Lock</a> reference page.

The user-mode display driver must call the Microsoft Direct3D runtime's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/nc-d3dumddi-pfnd3dddi_unlockcb">pfnUnlockCb</a> function after <i>Unlock</i> is called. In this <b>pfnUnlockCb</b> call, the user-mode display driver passes an allocation handle. Before calling <b>pfnUnlockCb</b>, the user-mode display driver must first map the surface to an appropriate allocation. 

The runtime calls the user-mode display driver's <i>Unlock</i> function to unlock preallocated system memory surfaces as well. The runtime sets the <b>NotifyOnly</b> bit-field flag in the <b>Flags</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/ns-d3dumddi-_d3dddiarg_unlock">D3DDDIARG_UNLOCK</a> structure that is pointed to by <i>pData</i> to differentiate <i>Unlock</i> calls that unlock preallocated system memory from other <i>Unlock</i> calls. If the user-mode display driver's <i>Lock</i> function called <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/nc-d3dumddi-pfnd3dddi_lockcb">pfnLockCb</a> to lock the system memory allocation that corresponds to the surface, it must also call <b>pfnUnlockCb</b>. Not calling <b>pfnUnlockCb</b>  stops the coordination between the runtime, the user-mode display driver, and the display miniport driver.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/ns-d3dumddi-_d3dddiarg_unlock">D3DDDIARG_UNLOCK</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/ns-d3dumddi-_d3dddi_devicefuncs">D3DDDI_DEVICEFUNCS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/nc-d3dumddi-pfnd3dddi_lock">Lock</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/nc-d3dumddi-pfnd3dddi_lockcb">pfnLockCb</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/nc-d3dumddi-pfnd3dddi_unlockcb">pfnUnlockCb</a>

