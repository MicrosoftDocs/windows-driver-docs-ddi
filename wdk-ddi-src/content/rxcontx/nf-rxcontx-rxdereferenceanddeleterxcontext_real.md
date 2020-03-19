---
UID: NF:rxcontx.RxDereferenceAndDeleteRxContext_Real
title: RxDereferenceAndDeleteRxContext_Real function (rxcontx.h)
description: RxDereferenceAndDeleteRxContext_Real dereferences an RX_CONTEXT data structure and if the ReferenceCount member goes to zero, then it deallocates and removes the specified RX_CONTEXT structure from the RDBSS in-memory data structures.
old-location: ifsk\rxdereferenceanddeleterxcontext_real.htm
tech.root: ifsk
ms.assetid: a2a2bb57-6f5c-4bc9-8564-ab0db2efd872
ms.date: 04/16/2018
keywords: ["RxDereferenceAndDeleteRxContext_Real function"]
ms.keywords: RxDereferenceAndDeleteRxContext_Real, RxDereferenceAndDeleteRxContext_Real function [Installable File System Drivers], ifsk.rxdereferenceanddeleterxcontext_real, rxcontx/RxDereferenceAndDeleteRxContext_Real, rxref_d3ea173c-343f-4fbf-b07b-be17816e1b2e.xml
f1_keywords:
 - "rxcontx/RxDereferenceAndDeleteRxContext_Real"
req.header: rxcontx.h
req.include-header: Rxprocs.h  rxcontx.h
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- rxcontx.h
api_name:
- RxDereferenceAndDeleteRxContext_Real
product:
- Windows
targetos: Windows
req.typenames: 
---

# RxDereferenceAndDeleteRxContext_Real function


## -description


<b>RxDereferenceAndDeleteRxContext_Real</b> dereferences an RX_CONTEXT data structure and if the <b>ReferenceCount</b> member goes to zero, then it deallocates and removes the specified RX_CONTEXT structure from the RDBSS in-memory data structures. 


## -parameters




### -param RxContext [in]

A pointer to the RX_CONTEXT structure to be removed.


## -remarks



<b>RxDereferenceAndDeleteRxContext_Real</b> is called by routines other than <b>RxCompleteRequest</b> during asynchronous requests that touch the <i>RxContext</i> parameter in either the initiating thread or in some other thread. Thus, the RX_CONTEXT data structure is reference counted and finalized on the last dereference.

If the <b>ReferenceCount</b> member of the RX_CONTEXT structure pointed to by the <i>RxContext</i> parameter is not zero after being derefenced (decremented) by the <b>RxDereferenceAndDeleteRxContext_Real</b> routine, then <b>RxDereferenceAndDeleteRxContext_Real</b> causes the system to ASSERT on checked builds. 

The <b>RxDereferenceAndDeleteRxContext_Real</b> routine makes a number of specific checks before removing an RX_CONTEXT. These checks include the following:

<ul>
<li>
If the <b>AcquireReleaseFcbTrackerX</b> member is 0, then <b>RxDereferenceAndDeleteRxContext_Real</b> causes the system to ASSERT on checked builds.

</li>
<li>
If the <b>NumberOfActiveContexts</b> member of the associated RDBSS_DEVICE_OBJECT structure pointed to <b><i>RxContext</i></b><b>->RxDeviceObject</b> is not zero after being dereferenced (decremented) and the <b>StartStopContext.pStopContext</b> member of the associated RDBSS_DEVICE_OBJECT structure is not <b>NULL</b>, then <b>RxDereferenceAndDeleteRxContext_Real</b> will signal the SyncEvent on the RX_CONTEXT structure in the <b>StartStopContext.pStopContext</b> member.

</li>
</ul>
If the RX_CONTEXT structure was allocated from non-page pool memory (the <b>Flags</b> member of the RX_CONTEXT structure has the RX_CONTEXT_FLAG_FROM_POOL option set), then the RX_CONTEXT structure pointed to by the <i>RxContext</i> parameter will be returned to an internal RDBSS lookaside list or to non-paged pool memory. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/rxcontx/ns-rxcontx-_rx_context">RX_CONTEXT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/rxprocs/nf-rxprocs-rxcompleterequest">RxCompleteRequest</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/rxprocs/nf-rxprocs-rxcompleterequest_real">RxCompleteRequest_Real</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/rxcontx/nf-rxcontx-rxcreaterxcontext">RxCreateRxContext</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/rxprocs/nf-rxprocs-rxdereference">RxDereference</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/rxcontx/nf-rxcontx-rxinitializecontext">RxInitializeContext</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/rxcontx/nf-rxcontx-rxpreparecontextforreuse">RxPrepareContextForReuse</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/rxcontx/nf-rxcontx-rxresumeblockedoperations_serially">RxResumeBlockedOperations_Serially</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/rxcontx/nf-rxcontx-__rxsynchronizeblockingoperations">__RxSynchronizeBlockingOperations</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/--rxsynchronizeblockingoperationsmaybedroppingfcblock">__RxSynchronizeBlockingOperationsMaybeDroppingFcbLock</a>
 

 

