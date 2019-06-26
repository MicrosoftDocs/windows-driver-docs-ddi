---
UID: NC:d3dumddi.PFND3DDDI_CREATESYNCHRONIZATIONOBJECT2CB
title: PFND3DDDI_CREATESYNCHRONIZATIONOBJECT2CB (d3dumddi.h)
description: Creates a GPU synchronization object that a device context can signal and wait for. Used by WDDM 1.2 and later user-mode display drivers.
old-location: display\pfncreatesynchronizationobject2cb.htm
tech.root: display
ms.assetid: 9B0F058C-B71F-4A4F-A053-F9381A5FD3A8
ms.date: 05/10/2018
ms.keywords: PFND3DDDI_CREATESYNCHRONIZATIONOBJECT2CB, PFND3DDDI_CREATESYNCHRONIZATIONOBJECT2CB callback, d3dumddi/pfnCreateSynchronizationObject2Cb, display.pfncreatesynchronizationobject2cb, pfnCreateSynchronizationObject2Cb, pfnCreateSynchronizationObject2Cb callback function [Display Devices]
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- d3dumddi.h
api_name:
- pfnCreateSynchronizationObject2Cb
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFND3DDDI_CREATESYNCHRONIZATIONOBJECT2CB callback function


## -description


Creates a GPU synchronization object that a device context can signal and wait for. Used by WDDM 1.2 and later user-mode display drivers.


## -parameters




### -param hDevice [in]

A handle to the display device (that is, the graphics context) that will own the synchronization object that <i>pfnCreateSynchronizationObject2Cb</i> creates.


### -param *








*pData* [in, out]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/ns-d3dumddi-_d3dddicb_createsynchronizationobject2">D3DDDICB_CREATESYNCHRONIZATIONOBJECT2</a> structure that describes the synchronization object to create.


## -returns

Returns one of the following values:

|Return code|Description|
|--- |--- |
|S_OK|The synchronization object was successfully created.|
|E_OUTOFMEMORY|The function could not allocate memory that was required for it to complete.|
|E_INVALIDARG|Parameters were validated and determined to be incorrect.|
 

This function might also return other HRESULT values.




## -remarks



The <i>pfnCreateSynchronizationObject2Cb</i> function returns a kernel-mode handle to the newly created synchronization object in the <b>hSyncObject</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/ns-d3dumddi-_d3dddicb_createsynchronizationobject2">D3DDDICB_CREATESYNCHRONIZATIONOBJECT2</a> structure that the <i>pData</i> parameter points to. The user-mode display driver passes this handle in calls to the following functions:

<ul>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/nc-d3dumddi-pfnd3dddi_destroysynchronizationobjectcb">pfnDestroySynchronizationObjectCb</a>


</li>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/nc-d3dumddi-pfnd3dddi_signalsynchronizationobjectcb">pfnSignalSynchronizationObjectCb</a>


</li>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/nc-d3dumddi-pfnd3dddi_signalsynchronizationobject2cb">pfnSignalSynchronizationObject2Cb</a>


</li>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/nc-d3dumddi-pfnd3dddi_waitforsynchronizationobjectcb">pfnWaitForSynchronizationObjectCb</a>


</li>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/nc-d3dumddi-pfnd3dddi_waitforsynchronizationobject2cb">pfnWaitForSynchronizationObject2Cb</a>


</li>
</ul>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/ns-d3dumddi-_d3dddicb_createsynchronizationobject2">D3DDDICB_CREATESYNCHRONIZATIONOBJECT2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/ns-d3dumddi-_d3dddi_devicecallbacks">D3DDDI_DEVICECALLBACKS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/nc-d3dumddi-pfnd3dddi_destroysynchronizationobjectcb">pfnDestroySynchronizationObjectCb</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/nc-d3dumddi-pfnd3dddi_signalsynchronizationobject2cb">pfnSignalSynchronizationObject2Cb</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/nc-d3dumddi-pfnd3dddi_waitforsynchronizationobject2cb">pfnWaitForSynchronizationObject2Cb</a>
 

 

