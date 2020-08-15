---
UID: NF:mrxfcb.RxAcquireSharedFcbResourceInMRxEx
title: RxAcquireSharedFcbResourceInMRxEx function (mrxfcb.h)
description: RxAcquireSharedFcbResourceInMRxEx acquires the FCB resource for a network mini-redirector driver in shared mode.
old-location: ifsk\rxacquiresharedfcbresourceinmrxex.htm
tech.root: ifsk
ms.assetid: bf8390db-7e42-4860-8cf6-df3459f16cea
ms.date: 04/16/2018
keywords: ["RxAcquireSharedFcbResourceInMRxEx function"]
ms.keywords: RxAcquireSharedFcbResourceInMRxEx, RxAcquireSharedFcbResourceInMRxEx routine [Installable File System Drivers], ifsk.rxacquiresharedfcbresourceinmrxex, mrxfcb/RxAcquireSharedFcbResourceInMRxEx, rxref_2b8fc5d6-96e5-45a0-897a-f55964e6cc8a.xml
f1_keywords:
 - "mrxfcb/RxAcquireSharedFcbResourceInMRxEx"
 - "RxAcquireSharedFcbResourceInMRxEx"
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
req.lib: 
req.dll: 
req.irql: <= APC_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- mrxfcb.h
api_name:
- RxAcquireSharedFcbResourceInMRxEx
targetos: Windows
req.typenames: 
---

# RxAcquireSharedFcbResourceInMRxEx function


## -description


<b>RxAcquireSharedFcbResourceInMRxEx</b> acquires the FCB resource for a network mini-redirector driver in shared mode. This routine will wait for the FCB resource to be free if it was previously acquired exclusively and does not return control until the shared resource has been acquired. 


## -parameters




### -param pRxContext 
[in]
A pointer to the RX_CONTEXT. This parameter supplies the context of the operation for special treatment by internal RDBSS tracking if this feature is enabled. 


### -param Fcb

<p>A pointer to the FCB. This parameter is required and cannot be <b>NULL</b>. </p>




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




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/mrxfcb/nf-mrxfcb-rxacquireexclusivefcbresourceinmrx">RxAcquireExclusiveFcbResourceInMRx</a>



<b>RxAcquireSharedFcbResourceInMRx</b>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/mrxfcb/nf-mrxfcb-rxreleasefcbresourceforthreadinmrx">RxReleaseFcbResourceForThreadInMRx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/mrxfcb/nf-mrxfcb-rxreleasefcbresourceinmrx">RxReleaseFcbResourceInMRx</a>
 

 

