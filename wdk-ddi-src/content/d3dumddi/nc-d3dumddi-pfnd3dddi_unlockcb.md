---
UID: NC:d3dumddi.PFND3DDDI_UNLOCKCB
title: PFND3DDDI_UNLOCKCB
author: windows-driver-content
description: The pfnUnlockCb function unlocks an allocation that was locked by a call to the pfnLockCb function.
old-location: display\pfnunlockcb.htm
old-project: display
ms.assetid: 6684f350-da27-478d-ab7b-36e395f7df8d
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3Druntime_Functions_8911e13b-cbfc-4620-bdb2-0dd6a558e88c.xml, PFND3DDDI_UNLOCKCB, d3dumddi/pfnUnlockCb, display.pfnunlockcb, pfnUnlockCb, pfnUnlockCb callback function [Display Devices]
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
-	pfnUnlockCb
product: Windows
targetos: Windows
req.typenames: DXGK_PTE
---

# PFND3DDDI_UNLOCKCB callback


## -description


The <b>pfnUnlockCb</b> function unlocks an allocation that was locked by a call to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_lockcb.md">pfnLockCb</a> function. 


## -prototype


````
PFND3DDDI_UNLOCKCB pfnUnlockCb;

__checkReturn HRESULT APIENTRY pfnUnlockCb(
  _In_       HANDLE          hDevice,
  _In_ const D3DDDICB_UNLOCK *pData
)
{ ... }
````


## -parameters




### -param hDevice [in]

A handle to the display device (graphics context).


### -param *








#### - pData [in]

A pointer to a <a href="..\d3dumddi\ns-d3dumddi-_d3dddicb_unlock.md">D3DDDICB_UNLOCK</a> structure that describes the allocation to unlock.


## -returns



<b>pfnUnlockCb</b> returns one of the following values:

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
The allocation was successfully unlocked.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>
</td>
<td width="60%">
<b>pfnUnlockCb</b> could not complete because of insufficient memory. (This error occurs when the system is in an extreme low memory situation and there is not sufficient space to allocate the array of pages.)

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_INVALIDARG</b></dt>
</dl>
</td>
<td width="60%">
Parameters were validated and determined to be incorrect.

</td>
</tr>
</table>
 

This function might also return other HRESULT values.




## -remarks



The user-mode display driver must call the <b>pfnUnlockCb</b> function to unlock an allocation that was previously locked in a call to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_lockcb.md">pfnLockCb</a> function. If the driver does not call <b>pfnUnlockCb</b>, coordination between the Microsoft Direct3D runtime, the user-mode display driver, and the display miniport driver is lost. 

The user-mode display driver typically calls <b>pfnUnlockCb</b> in response to a call to its <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_unlock.md">Unlock</a> or <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_resourceunmap.md">ResourceUnmap</a> function (or other variations of <i>ResourceUnmap</i> such as <i>DynamicIABufferUnmap</i>) to unlock a resource or a surface within the resource. Before returning from the <i>Unlock</i> or <i>ResourceUnmap</i> call, the user-mode display driver must first map the resource or surface to the appropriate allocation and then call <b>pfnUnlockCb</b> to unlock the allocation. 

The user-mode display driver can also call <b>pfnUnlockCb</b> in response to a call to its <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_destroydevice.md">DestroyDevice</a> or <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_destroydevice.md">DestroyDevice(D3D10)</a> function to free all of the resources that it allocated for the device. In the lifetime of a device, every call to <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_lockcb.md">pfnLockCb</a> to lock an allocation must be paired with a call to the <b>pfnUnlockCb</b> function to unlock the allocation. 

The user-mode display driver can unlock multiple allocations in one call to <b>pfnUnlockCb</b> by setting the <b>NumAllocations</b> member of the <a href="..\d3dumddi\ns-d3dumddi-_d3dddicb_unlock.md">D3DDDICB_UNLOCK</a> structure to the number of allocations in the array that is specified by the <b>phAllocations</b> member of D3DDDICB_UNLOCK. 

The user-mode display driver should call <b>pfnUnlockCb</b> to unlock all of the allocations that are referred to in the command stream before calling the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_rendercb.md">pfnRenderCb</a> function. The driver could have allocations locked to support--for example, the <b>NoOverwrite</b> bit-field flag. If the driver does not unlock all of these allocations, the video memory manager might be required to place these allocations in AGP memory. 

The user-mode display driver should not call <b>pfnUnlockCb</b> to unlock an allocation that an application could be using. The driver is notified that the application is no longer reading from or writing to the allocation when the driver receives a call to its <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_unlock.md">Unlock</a> or <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_resourceunmap.md">ResourceUnmap</a> function on the corresponding resource. 


#### Examples

The following code example shows how to unlock an allocation.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>HRESULT CD3DContext::SyncEnginesUsingLock(VOID) {
    HRESULT hr;
    D3DDDICB_LOCK   lockCB;
    D3DDDICB_UNLOCK Unlock;

    memset(&amp;lockCB, 0, sizeof(D3DDDICB_LOCK));
    lockCB.hAllocation = m_HandleUsedInLastSubmit;
    lockCB.PrivateDriverData = 0;                       
    hr = m_d3dCallbacks.pfnLockCb(m_hD3D, &amp;lockCB);
    if (FAILED(hr)) {
        DBG_BREAK;
        return hr;
    }
    Unlock.NumAllocations = 1;
    Unlock.phAllocations = &amp;m_HandleUsedInLastSubmit;
    m_d3dCallbacks.pfnUnlockCb(m_hD3D, &amp;Unlock);   
    return hr;
}</pre>
</td>
</tr>
</table></span></div>



## -see-also

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_lockcb.md">pfnLockCb</a>



<a href="..\d3dumddi\ns-d3dumddi-_d3dddicb_unlock.md">D3DDDICB_UNLOCK</a>



<a href="..\d3dumddi\ns-d3dumddi-_d3dddi_devicecallbacks.md">D3DDDI_DEVICECALLBACKS</a>



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_resourceunmap.md">ResourceUnmap</a>



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_destroydevice.md">DestroyDevice(D3D10)</a>



<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_destroydevice.md">DestroyDevice</a>



<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_rendercb.md">pfnRenderCb</a>



<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_unlock.md">Unlock</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_UNLOCKCB callback function%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

