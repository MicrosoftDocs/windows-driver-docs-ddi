---
UID: NC:mrx.PMRX_CHANGE_BUFFERING_STATE_CALLDOWN
title: PMRX_CHANGE_BUFFERING_STATE_CALLDOWN
author: windows-driver-content
description: TheMRxCompleteBufferingStateChangeRequest routine is called by RDBSS to notify the network mini-redirector that a buffering state change request has been completed.
old-location: ifsk\mrxcompletebufferingstatechangerequest.htm
tech.root: ifsk
ms.assetid: 1484dcca-e29c-495d-917c-1debefc91409
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: MRxCompleteBufferingStateChangeRequest, MRxCompleteBufferingStateChangeRequest routine [Installable File System Drivers], PMRX_CHANGE_BUFFERING_STATE_CALLDOWN, ifsk.mrxcompletebufferingstatechangerequest, mrx/MRxCompleteBufferingStateChangeRequest, mrxref_5ac31893-1998-454a-a0c9-07d32e60d8db.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: mrx.h
req.include-header: Mrx.h
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	mrx.h
api_name:
-	MRxCompleteBufferingStateChangeRequest
product:
- Windows
targetos: Windows
req.typenames: 
---

# PMRX_CHANGE_BUFFERING_STATE_CALLDOWN callback function


## -description


The<i>MRxCompleteBufferingStateChangeRequest</i> routine is called by <a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/the-rdbss-driver-and-library">RDBSS</a> to notify the network mini-redirector that a buffering state change request has been completed. 


## -parameters




### -param RxContext [in, out]

A pointer to the RX_CONTEXT structure. This parameter contains the IRP that is requesting the operation.


### -param SrvOpen [in, out]

A pointer to a context parameter for use by the network mini-redirector callback routine.


### -param MRxContext [in]

A pointer to the SRV_OPEN structure and the associated FCB structure to be changed.


## -returns



<i>MRxCompleteBufferingStateChangeRequest</i> returns STATUS_SUCCESS on success or an appropriate NTSTATUS value, such as the following: 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NOT_SUPPORTED</b></dt>
</dl>
</td>
<td width="60%">
An option in the  buffering request change is not supported. 

</td>
</tr>
</table>
 




## -remarks



Before calling <i>MRxCompleteBufferingStateChangeRequest</i>, RDBSS:

<ul>
<li>
Acquires an exclusive lock on the FCB structure. 

</li>
<li>
Sets the <b>FcbState</b> member of <b>SrvOpen-&gt;Fcb</b> to FCB_STATE_BUFFERSTATE_CHANGING. 

</li>
<li>
Modifies the following members in the RX_CONTEXT structure pointed to by the <i>RxContext</i> parameter:<dl>
<dd>
<b>pRelevantSrvOpen</b> is set to the SRV_OPEN structure.

</dd>
<dd>
<b>pFcb</b> is set to the FCB structure.

</dd>
<dd>
<b>pFobx</b> is set to the FOBX structure.

</dd>
</dl>


</li>
</ul>
If lock buffering is enabled, <i>MRxCompleteBufferingStateChangeRequest</i> will need to flush out the byte-range locks to the server. The list of locked regions is passed to the network mini-redirector in the <b>LowIoContext.ParamsFor.Locks.LockList</b> member of the RX_CONTEXT structure.

The Server Message Block (SMB) redirector uses <i>MRxCompleteBufferingStateChangeRequest</i> to send an oplock break response or to close the handle on an oplock break if the file is no longer in use. Byte range locks that need to be flushed out to the server are passed to the network mini-redirector in the <b>LowIoContext.ParamsFor.Locks.LockList</b> member of the RX_CONTEXT structure. The new oplock level is passed in the <i>MrxContext</i> parameter.

RDBSS ignores the return value from <i>MRxCompleteBufferingStateChangeRequest</i>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff549856">MRxComputeNewBufferingState</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550687">MRxGetConnectionId</a>
 

 

