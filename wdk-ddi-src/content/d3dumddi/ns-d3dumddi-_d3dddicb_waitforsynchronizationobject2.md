---
UID: NS:d3dumddi._D3DDDICB_WAITFORSYNCHRONIZATIONOBJECT2
title: _D3DDDICB_WAITFORSYNCHRONIZATIONOBJECT2 (d3dumddi.h)
description: Describes the parameters that are required to set up the wait in a call to the pfnWaitForSynchronizationObject2Cb function.
old-location: display\d3dddicb_waitforsynchronizationobject2.htm
tech.root: display
ms.assetid: b5dbd1f3-4475-41d2-879a-34618b28b485
ms.date: 05/10/2018
ms.keywords: D3DDDICB_WAITFORSYNCHRONIZATIONOBJECT2, D3DDDICB_WAITFORSYNCHRONIZATIONOBJECT2 structure [Display Devices], _D3DDDICB_WAITFORSYNCHRONIZATIONOBJECT2, d3dumddi/D3DDDICB_WAITFORSYNCHRONIZATIONOBJECT2, display.d3dddicb_waitforsynchronizationobject2
ms.topic: struct
f1_keywords:
 - "d3dumddi/D3DDDICB_WAITFORSYNCHRONIZATIONOBJECT2"
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
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
- HeaderDef
api_location:
- D3dumddi.h
api_name:
- D3DDDICB_WAITFORSYNCHRONIZATIONOBJECT2
product:
- Windows
targetos: Windows
req.typenames: D3DDDICB_WAITFORSYNCHRONIZATIONOBJECT2
---

# _D3DDDICB_WAITFORSYNCHRONIZATIONOBJECT2 structure


## -description


Describes the parameters that are required to set up the wait in a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_waitforsynchronizationobject2cb">pfnWaitForSynchronizationObject2Cb</a> function.


## -struct-fields




### -field hContext

[in] A handle to a Direct3D context that waits for the synchronization objects in the array that the <b>ObjectHandleArray</b> member specifies to occur.


### -field ObjectCount

[in] The number of synchronization objects in the <b>ObjectHandleArray</b> array.

<b>ObjectHandleArray</b> must be set to 1 if the GPU synchronization object is of type <b>D3DDDI_FENCE</b>—namely, the <b>Type</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dukmdt/ns-d3dukmdt-_d3dddi_synchronizationobjectinfo2">D3DDDI_SYNCHRONIZATIONOBJECTINFO2</a> structure has a value of <b>D3DDDI_FENCE</b>.


### -field ObjectHandleArray

[in] An array of handles to the GPU synchronization objects that are to be signaled. The <b>D3DDDI_MAX_OBJECT_WAITED_ON</b> constant, which is defined as 32, indicates the maximum number of synchronization objects that the context can wait for.

All synchronization objects must be created on a logical adapter that has its context specified by the <b>hContext</b> member.


### -field FenceValue

[in] A 64-bit value that specifies the current fence value of the GPU synchronization object that is to be waited on.

This value applies only if the GPU synchronization object is of type <b>D3DDDI_FENCE</b>—namely, the <b>Type</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dukmdt/ns-d3dukmdt-_d3dddi_synchronizationobjectinfo2">D3DDDI_SYNCHRONIZATIONOBJECTINFO2</a> structure has a value of <b>D3DDDI_FENCE</b>.


## -remarks



Synchronization objects of type <b>D3DDDI_CPU_NOTIFICATION</b> cannot be used to wait on calls to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_waitforsynchronizationobject2cb">pfnWaitForSynchronizationObject2Cb</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dukmdt/ns-d3dukmdt-_d3dddi_synchronizationobjectinfo2">D3DDDI_SYNCHRONIZATIONOBJECTINFO2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_waitforsynchronizationobject2cb">pfnWaitForSynchronizationObject2Cb</a>
 

 

