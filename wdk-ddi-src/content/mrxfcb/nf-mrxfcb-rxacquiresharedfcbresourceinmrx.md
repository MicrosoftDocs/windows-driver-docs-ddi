---
UID: NF:mrxfcb.RxAcquireSharedFcbResourceInMRx
title: RxAcquireSharedFcbResourceInMRx function (mrxfcb.h)
description: RxAcquireSharedFcbResourceInMRx acquires the FCB resource for a network mini-redirector driver in shared mode.
old-location: ifsk\rxacquiresharedfcbresourceinmrx.htm
tech.root: ifsk
ms.assetid: 5ef976a7-5be6-414b-a558-75c107f75d61
ms.date: 04/16/2018
ms.keywords: RxAcquireSharedFcbResourceInMRx, RxAcquireSharedFcbResourceInMRx routine [Installable File System Drivers], ifsk.rxacquiresharedfcbresourceinmrx, mrxfcb/RxAcquireSharedFcbResourceInMRx, rxref_8be6c6b8-c906-4071-b1a1-7687f044dcb7.xml
ms.topic: function
req.header: mrxfcb.h
req.include-header: Mrxfcb.h
req.target-type: Desktop
req.target-min-winverclnt: 
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
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	mrxfcb.h
api_name:
-	RxAcquireSharedFcbResourceInMRx
product:
- Windows
targetos: Windows
req.typenames: 
---

# RxAcquireSharedFcbResourceInMRx function


## -description


<b>RxAcquireSharedFcbResourceInMRx</b> acquires the FCB resource for a network mini-redirector driver in shared mode. This routine will wait for the FCB resource to be free if it was previously acquired exclusively and does not return control until the shared resource has been acquired. 


## -parameters




### -param Fcb

<p>A pointer to the FCB. This parameter is required and cannot be <b>NULL</b>. </p>




## -returns



<b>RxAcquireSharedFcbResourceInMRx</b> returns STATUS_SUCCESS on success or one of the following error codes on failure: 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_LOCK_NOT_GRANTED</b></dt>
</dl>
</td>
<td width="60%">
The FCB resource was not acquired.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_CANCELLED</b></dt>
</dl>
</td>
<td width="60%">
The RX_CONTEXT associated with the FCB was canceled.

</td>
</tr>
</table>
 




## -remarks



The synchronization resources of interest to a network mini-redirector driver are primarily associated with the FCB. There is a paging I/O resource and a regular resource. The paging I/O resource is managed internally by RDBSS. The only resource accessible to a network mini-redirector driver is the regular resource which should be accessed using <b>RxAcquireExclusiveFcbResourceInMRx</b>, <b>RxAcquireExclusiveFcbResourceInMRxEx</b>, or <b>RxAcquireSharedFcbResourceInMRx</b>, depending on the acquired mode desired. 

<b>RxAcquireSharedFcbResourceInMRx</b> will wait for the FCB resource to be free if it was previously acquired exclusively and does not return control until the shared resource has been acquired. This routine acquires the FCB resource even if the RX_CONTEXT associated with this FCB has been canceled.

An FCB resource acquired with <b>RxAcquireSharedFcbResourceInMRx </b>should be released by calling <b>RxReleaseFcbResourceInMRx</b> or <b>RxReleaseFcbResourceForThreadInMRx</b>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff553363">RxAcquireExclusiveFcbResourceInMRx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553375">RxAcquireSharedFcbResourceInMRxEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554694">RxReleaseFcbResourceForThreadInMRx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554699">RxReleaseFcbResourceInMRx</a>
 

 

