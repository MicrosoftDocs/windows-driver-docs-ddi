---
UID: NS:d3dumddi.D3DDDICB_WAITFORSYNCHRONIZATIONOBJECTFROMCPU
title: D3DDDICB_WAITFORSYNCHRONIZATIONOBJECTFROMCPU
author: windows-driver-content
description: D3DDDICB_WAITFORSYNCHRONIZATIONOBJECTFROMCPU is used with pfnWaitForSynchronizationObjectFromCpuCb to wait for a monitored fence to reach a certain value.
old-location: display\d3dddicb_waitforsynchronizationobjectfromcpu.htm
tech.root: display
ms.assetid: 0F5BEDBF-6871-4343-88D1-85E7620171EF
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: D3DDDICB_WAITFORSYNCHRONIZATIONOBJECTFROMCPU, D3DDDICB_WAITFORSYNCHRONIZATIONOBJECTFROMCPU structure [Display Devices], WaitAny, d3dumddi/D3DDDICB_WAITFORSYNCHRONIZATIONOBJECTFROMCPU, display.d3dddicb_waitforsynchronizationobjectfromcpu
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dumddi.h
api_name:
-	D3DDDICB_WAITFORSYNCHRONIZATIONOBJECTFROMCPU
product:
- Windows
targetos: Windows
req.typenames: D3DDDICB_WAITFORSYNCHRONIZATIONOBJECTFROMCPU
---

# D3DDDICB_WAITFORSYNCHRONIZATIONOBJECTFROMCPU structure


## -description


<b>D3DDDICB_WAITFORSYNCHRONIZATIONOBJECTFROMCPU</b> is used with <a href="https://msdn.microsoft.com/304A5BCE-19E6-4F92-B840-FD3BE1CFB856">pfnWaitForSynchronizationObjectFromCpuCb</a> to wait for a monitored fence to reach a certain value.


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

[in] A <a href="https://msdn.microsoft.com/library/windows/hardware/dn914421">D3DDDI_WAITFORSYNCHRONIZATIONOBJECTFROMCPU_FLAGS</a> structure describing the operation.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="WaitAny"></a><a id="waitany"></a><a id="WAITANY"></a><dl>
<dt><b>WaitAny</b></dt>
<dt>FALSE</dt>
</dl>
</td>
<td width="60%">
The wait condition is considered to be satisfied when all input synchronization objects are signaled to the corresponding input fence values or greater.

</td>
</tr>
<tr>
<td width="40%"><a id="WaitAny"></a><a id="waitany"></a><a id="WAITANY"></a><dl>
<dt><b>WaitAny</b></dt>
<dt>TRUE</dt>
</dl>
</td>
<td width="60%">
The wait condition is considered to be satisfied when any of the input synchronization objects is signaled to the corresponding input fence value or greater.

</td>
</tr>
</table>
 


## -see-also




<a href="https://msdn.microsoft.com/304A5BCE-19E6-4F92-B840-FD3BE1CFB856">pfnWaitForSynchronizationObjectFromCpuCb</a>
 

 

