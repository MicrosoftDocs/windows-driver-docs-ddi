---
UID: NF:mrxfcb.RxAcquireSharedFcbResourceInMRx
title: RxAcquireSharedFcbResourceInMRx function
author: windows-driver-content
description: RxAcquireSharedFcbResourceInMRx acquires the FCB resource for a network mini-redirector driver in shared mode.
old-location: ifsk\rxacquiresharedfcbresourceinmrx.htm
old-project: ifsk
ms.assetid: 5ef976a7-5be6-414b-a558-75c107f75d61
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: mrxfcb/RxAcquireSharedFcbResourceInMRx, RxAcquireSharedFcbResourceInMRx routine [Installable File System Drivers], rxref_8be6c6b8-c906-4071-b1a1-7687f044dcb7.xml, ifsk.rxacquiresharedfcbresourceinmrx, RxAcquireSharedFcbResourceInMRx
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: <= APC_LEVEL
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	HeaderDef
apilocation: 
-	mrxfcb.h
apiname: 
-	RxAcquireSharedFcbResourceInMRx
product: Windows
targetos: Windows
req.typenames: SetDSMCounters_IN, *PSetDSMCounters_IN
---

# RxAcquireSharedFcbResourceInMRx function


## -description


<b>RxAcquireSharedFcbResourceInMRx</b> acquires the FCB resource for a network mini-redirector driver in shared mode. This routine will wait for the FCB resource to be free if it was previously acquired exclusively and does not return control until the shared resource has been acquired. 


## -syntax


````
NTSTATUS RxAcquireSharedFcbResourceInMRx(
  _Inout_ PMRX_FCB pFcb
);
````


## -parameters




### -param Fcb

TBD



#### - pFcb [in, out]

A pointer to the FCB. This parameter is required and cannot be <b>NULL</b>. 


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

<a href="..\mrxfcb\nf-mrxfcb-rxreleasefcbresourceforthreadinmrx.md">RxReleaseFcbResourceForThreadInMRx</a>

<a href="..\mrxfcb\nf-mrxfcb-rxacquireexclusivefcbresourceinmrx.md">RxAcquireExclusiveFcbResourceInMRx</a>

<a href="..\mrxfcb\nf-mrxfcb-rxacquiresharedfcbresourceinmrxex.md">RxAcquireSharedFcbResourceInMRxEx</a>

<a href="..\mrxfcb\nf-mrxfcb-rxreleasefcbresourceinmrx.md">RxReleaseFcbResourceInMRx</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RxAcquireSharedFcbResourceInMRx routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

