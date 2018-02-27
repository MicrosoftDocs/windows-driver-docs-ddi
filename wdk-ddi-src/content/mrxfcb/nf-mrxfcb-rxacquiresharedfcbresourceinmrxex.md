---
UID: NF:mrxfcb.RxAcquireSharedFcbResourceInMRxEx
title: RxAcquireSharedFcbResourceInMRxEx function
author: windows-driver-content
description: RxAcquireSharedFcbResourceInMRxEx acquires the FCB resource for a network mini-redirector driver in shared mode.
old-location: ifsk\rxacquiresharedfcbresourceinmrxex.htm
old-project: ifsk
ms.assetid: bf8390db-7e42-4860-8cf6-df3459f16cea
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RxAcquireSharedFcbResourceInMRxEx, RxAcquireSharedFcbResourceInMRxEx routine [Installable File System Drivers], ifsk.rxacquiresharedfcbresourceinmrxex, mrxfcb/RxAcquireSharedFcbResourceInMRxEx, rxref_2b8fc5d6-96e5-45a0-897a-f55964e6cc8a.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: mrxfcb.h
req.include-header: Mrxfcb.h
req.target-type: Desktop
req.target-min-winverclnt: The RxAcquireSharedFcbResourceInMRxEx routine is only available on Windows Server 2003 Service Pack 1 and later.
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
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	mrxfcb.h
api_name:
-	RxAcquireSharedFcbResourceInMRxEx
product: Windows
targetos: Windows
req.typenames: SetDSMCounters_IN, *PSetDSMCounters_IN
---

# RxAcquireSharedFcbResourceInMRxEx function


## -description


<b>RxAcquireSharedFcbResourceInMRxEx</b> acquires the FCB resource for a network mini-redirector driver in shared mode. This routine will wait for the FCB resource to be free if it was previously acquired exclusively and does not return control until the shared resource has been acquired. 


## -syntax


````
NTSTATUS RxAcquireSharedFcbResourceInMRxEx(
  _In_ PRX_CONTEXT pRxContext,
       PMRX_FCB    pFcb
);
````


## -parameters




### -param pRxContext [in]

A pointer to the RX_CONTEXT. This parameter supplies the context of the operation for special treatment by internal RDBSS tracking if this feature is enabled. 


### -param Fcb

TBD




#### - pFcb

A pointer to the FCB. This parameter is required and cannot be <b>NULL</b>. 


## -returns



<b>RxAcquireSharedFcbResourceInMRxEx</b> returns STATUS_SUCCESS on success or one of the following error codes on failure: 

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

<b>RxAcquireSharedFcbResourceInMRxEx</b> will wait for the FCB resource to be free if it was previously acquired exclusively and does not return control until the shared resource has been acquired. This routine acquires the FCB resource even if the RX_CONTEXT associated with this FCB has been canceled.

An FCB resource acquired with <b>RxAcquireSharedFcbResourceInMRxEx </b>should be released by calling <b>RxReleaseFcbResourceInMRx</b> or <b>RxReleaseFcbResourceForThreadInMRx</b>. 




## -see-also

<a href="..\mrxfcb\nf-mrxfcb-rxreleasefcbresourceinmrx.md">RxReleaseFcbResourceInMRx</a>



<a href="..\mrxfcb\nf-mrxfcb-rxreleasefcbresourceforthreadinmrx.md">RxReleaseFcbResourceForThreadInMRx</a>



<a href="..\mrxfcb\nf-mrxfcb-rxacquireexclusivefcbresourceinmrx.md">RxAcquireExclusiveFcbResourceInMRx</a>



<b>RxAcquireSharedFcbResourceInMRx</b>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RxAcquireSharedFcbResourceInMRxEx routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

