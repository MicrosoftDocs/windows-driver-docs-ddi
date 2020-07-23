---
UID: NS:d3dumddi.D3DDDICB_WAITFORSYNCHRONIZATIONOBJECTFROMGPU
title: D3DDDICB_WAITFORSYNCHRONIZATIONOBJECTFROMGPU (d3dumddi.h)
description: D3DDDICB_WAITFORSYNCHRONIZATIONOBJECTFROMGPU is used with pfnWaitForSynchronizationObjectFromGpuCb to wait for a monitored fence to reach a certain value.
old-location: display\d3dddicb_waitforsynchronizationobjectfromgpu.htm
tech.root: display
ms.assetid: 2A441CEE-C138-4FF0-8865-04ABFB0F029C
ms.date: 05/10/2018
keywords: ["D3DDDICB_WAITFORSYNCHRONIZATIONOBJECTFROMGPU structure"]
ms.keywords: D3DDDICB_WAITFORSYNCHRONIZATIONOBJECTFROMGPU, D3DDDICB_WAITFORSYNCHRONIZATIONOBJECTFROMGPU structure [Display Devices], d3dumddi/D3DDDICB_WAITFORSYNCHRONIZATIONOBJECTFROMGPU, display.d3dddicb_waitforsynchronizationobjectfromgpu
f1_keywords:
 - "d3dumddi/D3DDDICB_WAITFORSYNCHRONIZATIONOBJECTFROMGPU"
 - "D3DDDICB_WAITFORSYNCHRONIZATIONOBJECTFROMGPU"
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
- d3dumddi.h
api_name:
- D3DDDICB_WAITFORSYNCHRONIZATIONOBJECTFROMGPU
targetos: Windows
req.typenames: D3DDDICB_WAITFORSYNCHRONIZATIONOBJECTFROMGPU
---

# D3DDDICB_WAITFORSYNCHRONIZATIONOBJECTFROMGPU structure


## -description


<b>D3DDDICB_WAITFORSYNCHRONIZATIONOBJECTFROMGPU</b> is used with <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_waitforsynchronizationobjectfromgpucb">pfnWaitForSynchronizationObjectFromGpuCb</a> to wait for a monitored fence to reach a certain value.


## -struct-fields




### -field hContext

[in] A kernel-mode handle to the context stream in which a wait for the synchronization events in the array that the <b>ObjectHandleArray</b> member specifies is inserted.


### -field ObjectCount

[in] The number of synchronization events in the <b>ObjectHandleArray</b> array and fence values in <b>MonitoredFenceValueArray</b> arrays.


### -field ObjectHandleArray

[in] An array of kernel-mode handles to the synchronization events that the context that is specified by the <b>hContext</b> member waits for.


### -field MonitoredFenceValueArray

[in] An array of 64-bit monitored fence values to wait for, each value corresponding to a synchronization object in <b>ObjectHandleArray</b>.


### -field FenceValue

[in] Fence value to wait for when the input object is of type <b>D3DDDI_FENCE</b>.


### -field Reserved

This member is reserved and should be set to zero.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_waitforsynchronizationobjectfromgpucb">pfnWaitForSynchronizationObjectFromGpuCb</a>
 

 

