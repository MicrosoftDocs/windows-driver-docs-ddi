---
UID: NC:d3dumddi.PFND3DDDI_CREATESYNCHRONIZATIONOBJECTCB
title: PFND3DDDI_CREATESYNCHRONIZATIONOBJECTCB (d3dumddi.h)
description: The pfnCreateSynchronizationObjectCb function creates a synchronization object that a device context can signal and wait for.
old-location: display\pfncreatesynchronizationobjectcb.htm
tech.root: display
ms.assetid: 1b87d3cc-685a-4768-b4fd-dbe0a0cbec37
ms.date: 05/10/2018
keywords: ["PFND3DDDI_CREATESYNCHRONIZATIONOBJECTCB callback function"]
ms.keywords: D3Druntime_Functions_6c4f40ee-12b2-47a8-bbec-8591b730bef5.xml, PFND3DDDI_CREATESYNCHRONIZATIONOBJECTCB, PFND3DDDI_CREATESYNCHRONIZATIONOBJECTCB callback, d3dumddi/pfnCreateSynchronizationObjectCb, display.pfncreatesynchronizationobjectcb, pfnCreateSynchronizationObjectCb, pfnCreateSynchronizationObjectCb callback function [Display Devices]
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
 - PFND3DDDI_CREATESYNCHRONIZATIONOBJECTCB
 - d3dumddi/PFND3DDDI_CREATESYNCHRONIZATIONOBJECTCB
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dumddi.h
api_name:
 - pfnCreateSynchronizationObjectCb
product:
 - Windows
---

# PFND3DDDI_CREATESYNCHRONIZATIONOBJECTCB callback function


## -description

The <b>pfnCreateSynchronizationObjectCb</b> function creates a synchronization object that a device context can signal and wait for.

## -parameters

### -param hDevice

A handle to the display device (that is, the graphics context) that will own the synchronization object that <b>pfnCreateSynchronizationObjectCb</b> creates.

### -param Arg2

*pData* [in, out]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddicb_createsynchronizationobject">D3DDDICB_CREATESYNCHRONIZATIONOBJECT</a> structure that describes the synchronization object to create.

## -returns

<b>pfnCreateSynchronizationObjectCb</b> returns one of the following values:

|Return code|Description|
|--- |--- |
|S_OK|The synchronization object was successfully created.|
|E_OUTOFMEMORY|pfnCreateSynchronizationObjectCb could not allocate memory that was required for it to complete.|
|E_INVALIDARG|Parameters were validated and determined to be incorrect.|
 

This function might also return other HRESULT values.

## -remarks

The <b>pfnCreateSynchronizationObjectCb</b> function returns a kernel-mode handle to the newly created synchronization object in the <b>hSyncObject</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddicb_createsynchronizationobject">D3DDDICB_CREATESYNCHRONIZATIONOBJECT</a> structure that the <i>pData</i> parameter points to. The user-mode display driver passes this handle in calls to the following functions:

<ul>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_destroysynchronizationobjectcb">pfnDestroySynchronizationObjectCb</a>


</li>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_signalsynchronizationobjectcb">pfnSignalSynchronizationObjectCb</a>


</li>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_waitforsynchronizationobjectcb">pfnWaitForSynchronizationObjectCb</a>


</li>
</ul>

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddicb_createsynchronizationobject">D3DDDICB_CREATESYNCHRONIZATIONOBJECT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddi_devicecallbacks">D3DDDI_DEVICECALLBACKS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_destroysynchronizationobjectcb">pfnDestroySynchronizationObjectCb</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_signalsynchronizationobjectcb">pfnSignalSynchronizationObjectCb</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_waitforsynchronizationobjectcb">pfnWaitForSynchronizationObjectCb</a>

