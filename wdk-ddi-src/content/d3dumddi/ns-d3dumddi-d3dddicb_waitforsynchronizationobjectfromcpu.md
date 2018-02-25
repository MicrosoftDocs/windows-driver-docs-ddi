---
UID: NS:d3dumddi.D3DDDICB_WAITFORSYNCHRONIZATIONOBJECTFROMCPU
title: D3DDDICB_WAITFORSYNCHRONIZATIONOBJECTFROMCPU
author: windows-driver-content
description: D3DDDICB_WAITFORSYNCHRONIZATIONOBJECTFROMCPU is used with pfnWaitForSynchronizationObjectFromCpuCb to wait for a monitored fence to reach a certain value.
old-location: display\d3dddicb_waitforsynchronizationobjectfromcpu.htm
old-project: display
ms.assetid: 0F5BEDBF-6871-4343-88D1-85E7620171EF
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ",  , ,, 3, A, B, C, D, D3DDDICB_WAITFORSYNCHRONIZATIONOBJECTFROMCPU, D3DDDICB_WAITFORSYNCHRONIZATIONOBJECTFROMCPU structure [Display Devices], E, F, H, I, J, M, N, O, P, R, S, T, U, W, WaitAny, Y, Z, _, d3dumddi/D3DDDICB_WAITFORSYNCHRONIZATIONOBJECTFROMCPU, display.d3dddicb_waitforsynchronizationobjectfromcpu"
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dumddi.h
apiname:
-	D3DDDICB_WAITFORSYNCHRONIZATIONOBJECTFROMCPU
product: Windows
targetos: Windows
req.typenames: D3DDDICB_WAITFORSYNCHRONIZATIONOBJECTFROMCPU
---

# D3DDDICB_WAITFORSYNCHRONIZATIONOBJECTFROMCPU structure


## -description


<b>D3DDDICB_WAITFORSYNCHRONIZATIONOBJECTFROMCPU</b> is used with <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_waitforsynchronizationobjectfromcpucb.md">pfnWaitForSynchronizationObjectFromCpuCb</a> to wait for a monitored fence to reach a certain value.


## -syntax


````
typedef struct D3DDDICB_WAITFORSYNCHRONIZATIONOBJECTFROMCPU {
  UINT                                             ObjectCount;
  const D3DKMT_HANDLE                              *ObjectHandleArray;
  const UINT64                                     *FenceValueArray;
  HANDLE                                           hAsyncEvent;
  D3DDDI_WAITFORSYNCHRONIZATIONOBJECTFROMCPU_FLAGS Flags;
} D3DDDICB_WAITFORSYNCHRONIZATIONOBJECTFROMCPU;
````


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

[in] A <a href="..\d3dukmdt\ns-d3dukmdt-_d3dddi_waitforsynchronizationobjectfromcpu_flags.md">D3DDDI_WAITFORSYNCHRONIZATIONOBJECTFROMCPU_FLAGS</a> structure describing the operation.

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

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_waitforsynchronizationobjectfromcpucb.md">pfnWaitForSynchronizationObjectFromCpuCb</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDICB_WAITFORSYNCHRONIZATIONOBJECTFROMCPU structure%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

