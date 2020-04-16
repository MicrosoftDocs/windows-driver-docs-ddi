---
UID: NC:d3dumddi.PFND3DDDI_UNLOCKCB
title: PFND3DDDI_UNLOCKCB (d3dumddi.h)
description: The pfnUnlockCb function unlocks an allocation that was locked by a call to the pfnLockCb function.
old-location: display\pfnunlockcb.htm
tech.root: display
ms.assetid: 6684f350-da27-478d-ab7b-36e395f7df8d
ms.date: 05/10/2018
keywords: ["PFND3DDDI_UNLOCKCB callback function"]
ms.keywords: D3Druntime_Functions_8911e13b-cbfc-4620-bdb2-0dd6a558e88c.xml, PFND3DDDI_UNLOCKCB, PFND3DDDI_UNLOCKCB callback, d3dumddi/pfnUnlockCb, display.pfnunlockcb, pfnUnlockCb, pfnUnlockCb callback function [Display Devices]
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
 - "d3dumddi/pfnUnlockCb"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dumddi.h
api_name:
 - pfnUnlockCb
product:
 - Windows
---

# PFND3DDDI_UNLOCKCB callback function

## -description

The <b>pfnUnlockCb</b> function unlocks an allocation that was locked by a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_lockcb">pfnLockCb</a> function.

## -parameters

### -param hDevice

A handle to the display device (graphics context).

### -param Arg2

*pData* [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddicb_unlock">D3DDDICB_UNLOCK</a> structure that describes the allocation to unlock.

## -returns

<b>pfnUnlockCb</b> returns one of the following values:

|Return code|Description|
|--- |--- |
|S_OK|The allocation was successfully unlocked.|
|E_OUTOFMEMORY|pfnUnlockCb could not complete because of insufficient memory. (This error occurs when the system is in an extreme low memory situation and there is not sufficient space to allocate the array of pages.)|
|E_INVALIDARG|Parameters were validated and determined to be incorrect.|
 

This function might also return other HRESULT values.

## -remarks

The user-mode display driver must call the <b>pfnUnlockCb</b> function to unlock an allocation that was previously locked in a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_lockcb">pfnLockCb</a> function. If the driver does not call <b>pfnUnlockCb</b>, coordination between the Microsoft Direct3D runtime, the user-mode display driver, and the display miniport driver is lost. 

The user-mode display driver typically calls <b>pfnUnlockCb</b> in response to a call to its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_unlock">Unlock</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_resourceunmap">ResourceUnmap</a> function (or other variations of <i>ResourceUnmap</i> such as <i>DynamicIABufferUnmap</i>) to unlock a resource or a surface within the resource. Before returning from the <i>Unlock</i> or <i>ResourceUnmap</i> call, the user-mode display driver must first map the resource or surface to the appropriate allocation and then call <b>pfnUnlockCb</b> to unlock the allocation. 

The user-mode display driver can also call <b>pfnUnlockCb</b> in response to a call to its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_destroydevice">DestroyDevice</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_destroydevice">DestroyDevice(D3D10)</a> function to free all of the resources that it allocated for the device. In the lifetime of a device, every call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_lockcb">pfnLockCb</a> to lock an allocation must be paired with a call to the <b>pfnUnlockCb</b> function to unlock the allocation. 

The user-mode display driver can unlock multiple allocations in one call to <b>pfnUnlockCb</b> by setting the <b>NumAllocations</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddicb_unlock">D3DDDICB_UNLOCK</a> structure to the number of allocations in the array that is specified by the <b>phAllocations</b> member of D3DDDICB_UNLOCK. 

The user-mode display driver should call <b>pfnUnlockCb</b> to unlock all of the allocations that are referred to in the command stream before calling the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_rendercb">pfnRenderCb</a> function. The driver could have allocations locked to support--for example, the <b>NoOverwrite</b> bit-field flag. If the driver does not unlock all of these allocations, the video memory manager might be required to place these allocations in AGP memory. 

The user-mode display driver should not call <b>pfnUnlockCb</b> to unlock an allocation that an application could be using. The driver is notified that the application is no longer reading from or writing to the allocation when the driver receives a call to its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_unlock">Unlock</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_resourceunmap">ResourceUnmap</a> function on the corresponding resource. 


#### Examples

The following code example shows how to unlock an allocation.

```cpp
HRESULT CD3DContext::SyncEnginesUsingLock(VOID) {
    HRESULT hr;
    D3DDDICB_LOCK   lockCB;
    D3DDDICB_UNLOCK Unlock;

    memset(&lockCB, 0, sizeof(D3DDDICB_LOCK));
    lockCB.hAllocation = m_HandleUsedInLastSubmit;
    lockCB.PrivateDriverData = 0;                       
    hr = m_d3dCallbacks.pfnLockCb(m_hD3D, &lockCB);
    if (FAILED(hr)) {
        DBG_BREAK;
        return hr;
    }
    Unlock.NumAllocations = 1;
    Unlock.phAllocations = &m_HandleUsedInLastSubmit;
    m_d3dCallbacks.pfnUnlockCb(m_hD3D, &Unlock);   
    return hr;
}
```

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddicb_unlock">D3DDDICB_UNLOCK</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddi_devicecallbacks">D3DDDI_DEVICECALLBACKS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_destroydevice">DestroyDevice</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_destroydevice">DestroyDevice(D3D10)</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_resourceunmap">ResourceUnmap</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_unlock">Unlock</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_lockcb">pfnLockCb</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_rendercb">pfnRenderCb</a>

