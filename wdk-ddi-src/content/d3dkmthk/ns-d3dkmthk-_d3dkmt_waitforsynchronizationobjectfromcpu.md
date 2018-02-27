---
UID: NS:d3dkmthk._D3DKMT_WAITFORSYNCHRONIZATIONOBJECTFROMCPU
title: "_D3DKMT_WAITFORSYNCHRONIZATIONOBJECTFROMCPU"
author: windows-driver-content
description: D3DKMT_WAITFORSYNCHRONIZATIONOBJECTFROMCPU is used with D3DKMTWaitForSynchronizationObjectFromCpu to wait for a monitored fence to reach a certain value.
old-location: display\d3dkmt_waitforsynchronizationobjectfromcpu.htm
old-project: display
ms.assetid: 76091965-D87B-4429-85A8-EC8085C773D7
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: D3DKMT_WAITFORSYNCHRONIZATIONOBJECTFROMCPU, D3DKMT_WAITFORSYNCHRONIZATIONOBJECTFROMCPU structure [Display Devices], WaitAny, _D3DKMT_WAITFORSYNCHRONIZATIONOBJECTFROMCPU, d3dkmthk/D3DKMT_WAITFORSYNCHRONIZATIONOBJECTFROMCPU, display.d3dkmt_waitforsynchronizationobjectfromcpu
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	D3dkmthk.h
apiname:
-	D3DKMT_WAITFORSYNCHRONIZATIONOBJECTFROMCPU
product: Windows
targetos: Windows
req.typenames: D3DKMT_WAITFORSYNCHRONIZATIONOBJECTFROMCPU
---

# _D3DKMT_WAITFORSYNCHRONIZATIONOBJECTFROMCPU structure


## -description


<b>D3DKMT_WAITFORSYNCHRONIZATIONOBJECTFROMCPU</b> is used with <a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtwaitforsynchronizationobjectfromcpu.md">D3DKMTWaitForSynchronizationObjectFromCpu</a> to wait for a monitored fence to reach a certain value.


## -syntax


````
typedef struct _D3DKMT_WAITFORSYNCHRONIZATIONOBJECTFROMCPU {
  D3DKMT_HANDLE                                    hDevice;
  UINT                                             ObjectCount;
  const D3DKMT_HANDLE                              *ObjectHandleArray;
  const UINT64                                     *FenceValueArray;
  HANDLE                                           hAsyncEvent;
  D3DDDI_WAITFORSYNCHRONIZATIONOBJECTFROMCPU_FLAGS Flags;
} D3DKMT_WAITFORSYNCHRONIZATIONOBJECTFROMCPU;
````


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

<a href="..\d3dukmdt\ns-d3dukmdt-_d3dddi_waitforsynchronizationobjectfromcpu_flags.md">D3DDDI_WAITFORSYNCHRONIZATIONOBJECTFROMCPU_FLAGS</a>



<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtwaitforsynchronizationobjectfromcpu.md">D3DKMTWaitForSynchronizationObjectFromCpu</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMT_WAITFORSYNCHRONIZATIONOBJECTFROMCPU structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

