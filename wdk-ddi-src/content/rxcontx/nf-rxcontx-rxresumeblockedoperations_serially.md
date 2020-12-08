---
UID: NF:rxcontx.RxResumeBlockedOperations_Serially
title: RxResumeBlockedOperations_Serially function (rxcontx.h)
description: RxResumeBlockedOperations_Serially wakes up the next waiting thread, if any, on the serialized blocking I/O queue.
old-location: ifsk\rxresumeblockedoperations_serially.htm
tech.root: ifsk
ms.date: 04/16/2018
keywords: ["RxResumeBlockedOperations_Serially function"]
ms.keywords: RxResumeBlockedOperations_Serially, RxResumeBlockedOperations_Serially , RxResumeBlockedOperations_Serially function [Installable File System Drivers], ifsk.rxresumeblockedoperations_serially, rxcontx/RxResumeBlockedOperations_Serially, rxref_b1284b31-72f0-4e0e-9602-817080b96e16.xml
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
req.lib: 
req.dll: 
req.irql: <= APC_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - RxResumeBlockedOperations_Serially
 - rxcontx/RxResumeBlockedOperations_Serially
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - rxcontx.h
api_name:
 - RxResumeBlockedOperations_Serially
---

# RxResumeBlockedOperations_Serially function


## -description

<b>RxResumeBlockedOperations_Serially </b>wakes up the next waiting thread, if any, on the serialized blocking I/O queue.

## -parameters

### -param RxContext 

[in, out]
A pointer to the RX_CONTEXT structure of the operation being synchronized.

### -param BlockingIoQ 

[in, out]
A pointer to the blocking I/O queue.

## -remarks

<b>RxResumeBlockedOperations_Serially </b>wakes up the next work item on a serialized blocking I/O queue, if one exists. The FCB structure must still be valid because of the reference that is being held by the I/O system on the file object, thereby preventing a close operation.

A serialized blocking I/O queue is one for which the <b>FlagsForLowIo</b> member of the RX_CONTEXT structure pointed to by <i>RxContext</i> has the RXCONTEXT_FLAG4LOWIO_PIPE_SYNC_OPERATION bit set. 

<b>RxResumeBlockedOperations_Serially </b>performs this operation by calling <b>RxFsdPostRequest</b> to post the operation to a worker thread. 

The <b>RxResumeBlockedOperations_Serially </b>routine is normally not called directly by a network mini-redirector driver, but is called internally by RDBSS when processing synchronous read and write operations on a named pipe that requires a serialized queue. 

A network mini-redirector may need to call <b>RxResumeBlockedOperations_Serially</b> if an RX_CONTEXT has been placed on a synchronization queue using <b>__RxSynchronizeBlockingOperations</b> or <b>__RxSynchronizeBlockingOperationsMaybeDroppingFcbLock</b>.

## -see-also

<a href="/windows-hardware/drivers/ddi/rxprocs/nf-rxprocs-rxcompleterequest_real">RxCompleteRequest_Real</a>



<a href="/windows-hardware/drivers/ddi/rxcontx/nf-rxcontx-rxcreaterxcontext">RxCreateRxContext</a>



<a href="/windows-hardware/drivers/ddi/rxprocs/nf-rxprocs-rxdereference">RxDereference</a>



<a href="/windows-hardware/drivers/ddi/rxcontx/nf-rxcontx-rxdereferenceanddeleterxcontext_real">RxDereferenceAndDeleteRxContext_Real</a>



<a href="/windows-hardware/drivers/ddi/rxprocs/nf-rxprocs-rxfsdpostrequest">RxFsdPostRequest</a>



<a href="/windows-hardware/drivers/ddi/rxcontx/nf-rxcontx-rxinitializecontext">RxInitializeContext</a>



<a href="/windows-hardware/drivers/ddi/rxcontx/nf-rxcontx-rxpreparecontextforreuse">RxPrepareContextForReuse</a>



<a href="/windows-hardware/drivers/ddi/rxcontx/nf-rxcontx-__rxsynchronizeblockingoperations">__RxSynchronizeBlockingOperations</a>



<a href="/windows-hardware/drivers/ifs/--rxsynchronizeblockingoperationsmaybedroppingfcblock">__RxSynchronizeBlockingOperationsMaybeDroppingFcbLock</a>
