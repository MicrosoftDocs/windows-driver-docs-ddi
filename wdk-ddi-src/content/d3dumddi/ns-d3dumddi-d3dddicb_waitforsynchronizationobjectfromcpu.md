---
UID: NS:d3dumddi.D3DDDICB_WAITFORSYNCHRONIZATIONOBJECTFROMCPU
title: D3DDDICB_WAITFORSYNCHRONIZATIONOBJECTFROMCPU (d3dumddi.h)
description: D3DDDICB_WAITFORSYNCHRONIZATIONOBJECTFROMCPU is used with pfnWaitForSynchronizationObjectFromCpuCb to wait for a monitored fence to reach a certain value.
old-location: display\d3dddicb_waitforsynchronizationobjectfromcpu.htm
tech.root: display
ms.assetid: 0F5BEDBF-6871-4343-88D1-85E7620171EF
ms.date: 05/10/2018
ms.keywords: D3DDDICB_WAITFORSYNCHRONIZATIONOBJECTFROMCPU, D3DDDICB_WAITFORSYNCHRONIZATIONOBJECTFROMCPU structure [Display Devices], WaitAny, d3dumddi/D3DDDICB_WAITFORSYNCHRONIZATIONOBJECTFROMCPU, display.d3dddicb_waitforsynchronizationobjectfromcpu
ms.topic: struct
f1_keywords:
 - "d3dumddi/D3DDDICB_WAITFORSYNCHRONIZATIONOBJECTFROMCPU"
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
- D3DDDICB_WAITFORSYNCHRONIZATIONOBJECTFROMCPU
product:
- Windows
targetos: Windows
req.typenames: D3DDDICB_WAITFORSYNCHRONIZATIONOBJECTFROMCPU
---

# D3DDDICB_WAITFORSYNCHRONIZATIONOBJECTFROMCPU structure


## -description


<b>D3DDDICB_WAITFORSYNCHRONIZATIONOBJECTFROMCPU</b> is used with <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/nc-d3dumddi-pfnd3dddi_waitforsynchronizationobjectfromcpucb">pfnWaitForSynchronizationObjectFromCpuCb</a> to wait for a monitored fence to reach a certain value.


## -struct-fields




### -field ObjectCount

[in] The number of synchronization objects in the <b>ObjectHandleArray</b> and fence values in the <b>FenceValueArray</b>. 


### -field ObjectHandleArray

[in] An array of kernel-mode handles to the synchronization events to wait for.


### -field FenceValueArray

[in] An array of 64-bit monitored fence values to wait for, each corresponding to an object in the <b>ObjectHandleArray</b>.


### -field hAsyncEvent

[in] When not <b>NULL</b>, specifies the event to be signaled when the wait condition is satisfied. When <b>NULL</b>, the call will not return until the wait condition is satisfied.


### -field Flags

[in] A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dukmdt/ns-d3dukmdt-_d3dddi_waitforsynchronizationobjectfromcpu_flags">D3DDDI_WAITFORSYNCHRONIZATIONOBJECTFROMCPU_FLAGS</a> structure describing the operation.

| **Value** | **Meaning** | 
|:--|:--|
| **WaitAny** <br/>FALSE|The wait condition is considered to be satisfied when all input synchronization objects are signaled to the corresponding input fence values or greater. |
| **WaitAny** <br/>TRUE|The wait condition is considered to be satisfied when any of the input synchronization objects is signaled to the corresponding input fence value or greater. |


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/nc-d3dumddi-pfnd3dddi_waitforsynchronizationobjectfromcpucb">pfnWaitForSynchronizationObjectFromCpuCb</a>
 

 

