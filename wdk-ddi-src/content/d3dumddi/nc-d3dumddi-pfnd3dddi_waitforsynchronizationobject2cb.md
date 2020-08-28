---
UID: NC:d3dumddi.PFND3DDDI_WAITFORSYNCHRONIZATIONOBJECT2CB
title: PFND3DDDI_WAITFORSYNCHRONIZATIONOBJECT2CB (d3dumddi.h)
description: Inserts a wait command for the specified synchronization objects in the specified context command stream. Used by Windows Display Driver Model (WDDM) 1.2 and later user-mode display drivers.
old-location: display\pfnwaitforsynchronizationobject2cb.htm
tech.root: display
ms.assetid: 4542C49F-C26C-45BE-B961-C5F65BDA78CF
ms.date: 05/10/2018
keywords: ["PFND3DDDI_WAITFORSYNCHRONIZATIONOBJECT2CB callback function"]
ms.keywords: PFND3DDDI_WAITFORSYNCHRONIZATIONOBJECT2CB, PFND3DDDI_WAITFORSYNCHRONIZATIONOBJECT2CB callback, d3dumddi/pfnWaitForSynchronizationObject2Cb, display.pfnwaitforsynchronizationobject2cb, pfnWaitForSynchronizationObject2Cb, pfnWaitForSynchronizationObject2Cb callback function [Display Devices]
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
targetos: Windows
req.typenames: 
f1_keywords:
 - PFND3DDDI_WAITFORSYNCHRONIZATIONOBJECT2CB
 - d3dumddi/PFND3DDDI_WAITFORSYNCHRONIZATIONOBJECT2CB
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dumddi.h
api_name:
 - pfnWaitForSynchronizationObject2Cb
product:
 - Windows
---

# PFND3DDDI_WAITFORSYNCHRONIZATIONOBJECT2CB callback function


## -description

Inserts a wait command for the specified synchronization objects in the specified context command stream. Used by Windows Display Driver Model (WDDM) 1.2 and later user-mode display drivers.

## -parameters

### -param hDevice

A handle to a display device (that is, the graphics context).

### -param Arg2

*pData* [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddicb_waitforsynchronizationobject2">D3DDDICB_WAITFORSYNCHRONIZATIONOBJECT2</a> structure that describes the synchronization objects and context DMA stream that are required to set up the wait.

## -returns

Returns one of the following values:

| **Return code** | **Description** | 
|:--|:--|
| **S_OK** | The wait was successfully set up. | 
| **E_INVALIDARG** | Parameters were validated and determined to be incorrect. | 
 

This function might also return other HRESULT values.

## -remarks

The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_createsynchronizationobject2cb">pfnCreateSynchronizationObject2Cb</a> function returns a kernel-mode handle to the newly created synchronization object in the <b>hSyncObject</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddicb_createsynchronizationobject2">D3DDDICB_CREATESYNCHRONIZATIONOBJECT2</a> structure that the <i>pData</i> parameter points to. The user-mode display driver passes this handle in calls to the following functions:

<ul>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_destroysynchronizationobjectcb">pfnDestroySynchronizationObjectCb</a>


</li>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_signalsynchronizationobject2cb">pfnSignalSynchronizationObject2Cb</a>


</li>
<li>
<i>pfnWaitForSynchronizationObject2Cb</i>

</li>
</ul>
Do not call this function if the synchronization object is of type <b>D3DDDI_CPU_NOTIFICATION</b>—namely, the <b>Type</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dukmdt/ns-d3dukmdt-_d3dddi_synchronizationobjectinfo2">D3DDDI_SYNCHRONIZATIONOBJECTINFO2</a> structure has a value of <b>D3DDDI_CPU_NOTIFICATION</b>.<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_destroysynchronizationobjectcb">pfnDestroySynchronizationObjectCb</a>

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddicb_createsynchronizationobject2">D3DDDICB_CREATESYNCHRONIZATIONOBJECT2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddi_devicecallbacks">D3DDDI_DEVICECALLBACKS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dukmdt/ns-d3dukmdt-_d3dddi_synchronizationobjectinfo2">D3DDDI_SYNCHRONIZATIONOBJECTINFO2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_createsynchronizationobject2cb">pfnCreateSynchronizationObject2Cb</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_destroysynchronizationobjectcb">pfnDestroySynchronizationObjectCb</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_signalsynchronizationobject2cb">pfnSignalSynchronizationObject2Cb</a>

