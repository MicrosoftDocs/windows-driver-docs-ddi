---
UID: NF:rxcontx.RxResumeBlockedOperations_Serially
title: RxResumeBlockedOperations_Serially function
author: windows-driver-content
description: RxResumeBlockedOperations_Serially wakes up the next waiting thread, if any, on the serialized blocking I/O queue.
old-location: ifsk\rxresumeblockedoperations_serially.htm
old-project: ifsk
ms.assetid: 8418ed17-39f0-4a3b-9eb5-453c7cc2ae98
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: RxResumeBlockedOperations_Serially function [Installable File System Drivers], rxref_b1284b31-72f0-4e0e-9602-817080b96e16.xml, ifsk.rxresumeblockedoperations_serially, rxcontx/RxResumeBlockedOperations_Serially, RxResumeBlockedOperations_Serially
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: rxcontx.h
req.include-header: Rxcontx.h
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
-	rxcontx.h
apiname: 
-	RxResumeBlockedOperations_Serially
product: Windows
targetos: Windows
req.typenames: *LPRILWRITEPHONEBOOKENTRYPARAMS, RILWRITEPHONEBOOKENTRYPARAMS
req.product: Windows 10 or later.
---

# RxResumeBlockedOperations_Serially function


## -description


<b>RxResumeBlockedOperations_Serially </b>wakes up the next waiting thread, if any, on the serialized blocking I/O queue.


## -syntax


````
VOID RxResumeBlockedOperations_Serially(
  _Inout_ PRX_CONTEXT RxContext,
  _Inout_ PLIST_ENTRY BlockingIoQ
);
````


## -parameters




### -param RxContext [in, out]

A pointer to the RX_CONTEXT structure of the operation being synchronized. 


### -param BlockingIoQ [in, out]

A pointer to the blocking I/O queue. 


## -returns


None 



## -remarks


<b>RxResumeBlockedOperations_Serially </b>wakes up the next work item on a serialized blocking I/O queue, if one exists. The FCB structure must still be valid because of the reference that is being held by the I/O system on the file object, thereby preventing a close operation.

A serialized blocking I/O queue is one for which the <b>FlagsForLowIo</b> member of the RX_CONTEXT structure pointed to by <i>RxContext</i> has the RXCONTEXT_FLAG4LOWIO_PIPE_SYNC_OPERATION bit set. 

<b>RxResumeBlockedOperations_Serially </b>performs this operation by calling <b>RxFsdPostRequest</b> to post the operation to a worker thread. 

The <b>RxResumeBlockedOperations_Serially </b>routine is normally not called directly by a network mini-redirector driver, but is called internally by RDBSS when processing synchronous read and write operations on a named pipe that requires a serialized queue. 

A network mini-redirector may need to call <b>RxResumeBlockedOperations_Serially</b> if an RX_CONTEXT has been placed on a synchronization queue using <b>__RxSynchronizeBlockingOperations</b> or <b>__RxSynchronizeBlockingOperationsMaybeDroppingFcbLock</b>. 



## -see-also

<a href="..\rxprocs\nf-rxprocs-rxcompleterequest_real.md">RxCompleteRequest_Real</a>

<a href="..\rxprocs\nf-rxprocs-rxfsdpostrequest.md">RxFsdPostRequest</a>

<a href="..\rxcontx\nf-rxcontx-rxdereferenceanddeleterxcontext_real.md">RxDereferenceAndDeleteRxContext_Real</a>

<a href="..\rxcontx\nf-rxcontx-rxcreaterxcontext.md">RxCreateRxContext</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff557382">__RxSynchronizeBlockingOperationsMaybeDroppingFcbLock</a>

<a href="..\rxcontx\nf-rxcontx-__rxsynchronizeblockingoperations.md">__RxSynchronizeBlockingOperations</a>

<a href="..\rxcontx\nf-rxcontx-rxpreparecontextforreuse.md">RxPrepareContextForReuse</a>

<a href="..\rxprocs\nf-rxprocs-rxdereference.md">RxDereference</a>

<a href="..\rxcontx\nf-rxcontx-rxinitializecontext.md">RxInitializeContext</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RxResumeBlockedOperations_Serially  function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

