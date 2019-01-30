---
UID: NS:d3dkmthk._D3DKMT_WAITFORSYNCHRONIZATIONOBJECTFROMCPU
title: "_D3DKMT_WAITFORSYNCHRONIZATIONOBJECTFROMCPU" (d3dkmthk.h)
description: D3DKMT_WAITFORSYNCHRONIZATIONOBJECTFROMCPU is used with D3DKMTWaitForSynchronizationObjectFromCpu to wait for a monitored fence to reach a certain value.
old-location: display\d3dkmt_waitforsynchronizationobjectfromcpu.htm
ms.assetid: 76091965-D87B-4429-85A8-EC8085C773D7
ms.date: 05/10/2018
ms.keywords: D3DKMT_WAITFORSYNCHRONIZATIONOBJECTFROMCPU, D3DKMT_WAITFORSYNCHRONIZATIONOBJECTFROMCPU structure [Display Devices], WaitAny, _D3DKMT_WAITFORSYNCHRONIZATIONOBJECTFROMCPU, d3dkmthk/D3DKMT_WAITFORSYNCHRONIZATIONOBJECTFROMCPU, display.d3dkmt_waitforsynchronizationobjectfromcpu
ms.topic: struct
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	D3dkmthk.h
api_name:
-	D3DKMT_WAITFORSYNCHRONIZATIONOBJECTFROMCPU
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3DKMT_WAITFORSYNCHRONIZATIONOBJECTFROMCPU
---

# _D3DKMT_WAITFORSYNCHRONIZATIONOBJECTFROMCPU structure


## -description


<b>D3DKMT_WAITFORSYNCHRONIZATIONOBJECTFROMCPU</b> is used with <a href="https://msdn.microsoft.com/library/windows/hardware/dn906789">D3DKMTWaitForSynchronizationObjectFromCpu</a> to wait for a monitored fence to reach a certain value.


## -struct-fields




### -field hDevice

[in] The device handle to wait on.


### -field ObjectCount

[in] The number of synchronization objects in the <b>ObjectHandleArray</b> and fence values in the <b>FenceValueArray</b>. 


### -field ObjectHandleArray

[in] An array of kernel-mode handles to the synchronization events to wait for.


### -field FenceValueArray

[in] An array of 64-bit monitored fence values to wait for, each corresponding to an object in the <b>ObjectHandleArray</b>.


### -field hAsyncEvent

[in] When not <b>NULL</b>, specifies the event to be signaled when the wait condition is satisfied. When <b>NULL</b>, the call will not return until the wait condition is satisfied.


### -field Flags

[in] A <a href="https://msdn.microsoft.com/library/windows/hardware/dn914421">D3DDDI_WAITFORSYNCHRONIZATIONOBJECTFROMCPU_FLAGS</a> structure describing the operation.

|Value|Meaning|
|--- |--- |
|WaitAny
FALSE|The wait condition is considered to be satisfied when all input synchronization objects are signaled to the corresponding input fence values or greater.|
|WaitAny
TRUE|The wait condition is considered to be satisfied when any of the input synchronization objects is signaled to the corresponding input fence value or greater.|
 
## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/dn914421">D3DDDI_WAITFORSYNCHRONIZATIONOBJECTFROMCPU_FLAGS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn906789">D3DKMTWaitForSynchronizationObjectFromCpu</a>
 

 

