---
UID: NF:rxcontx.RxPrepareContextForReuse
title: RxPrepareContextForReuse function (rxcontx.h)
description: RxPrepareContextForReuse prepares an RX_CONTEXT data structure for reuse by resetting all of the operation-specific allocations and acquisitions that have been made (the ReferenceCount member to the RX_CONTEXT structure is set to zero).
old-location: ifsk\rxpreparecontextforreuse.htm
tech.root: ifsk
ms.assetid: 16b4bd82-0ffc-40c7-8cd2-f73a2a588ac8
ms.date: 04/16/2018
keywords: ["RxPrepareContextForReuse function"]
ms.keywords: RxPrepareContextForReuse, RxPrepareContextForReuse function [Installable File System Drivers], ifsk.rxpreparecontextforreuse, rxcontx/RxPrepareContextForReuse, rxref_34eae0cd-faff-47e7-8313-aca1361edc68.xml
f1_keywords:
 - "rxcontx/RxPrepareContextForReuse"
 - "RxPrepareContextForReuse"
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
- RxPrepareContextForReuse
targetos: Windows
req.typenames: 
---

# RxPrepareContextForReuse function


## -description


<b>RxPrepareContextForReuse</b> prepares an RX_CONTEXT data structure for reuse by resetting all of the operation-specific allocations and acquisitions that have been made (the <b>ReferenceCount</b> member to the RX_CONTEXT structure is set to zero). Parameters that have been obtained from the IRP are not modified. 


## -parameters




### -param RxContext [in, out]

A pointer to the RX_CONTEXT structure.


## -remarks



The <b>RxPrepareContextForReuse</b> routine checks that several operation-specific members in the RX_CONTEXT structure are <b>NULL</b> before setting the <b>ReferenceCount</b> member to zero. These operation-specific tests that must be met include the following:

<ul>
<li>
If the <b>MajorFunction</b> member of the associated IRP is IRP_MJ_CREATE, then the <b>Create.CanonicalNameBuffer</b> member must be <b>NULL</b>.

</li>
<li>
If the <b>MajorFunction</b> member of the associated IRP is IRP_MJ_READ or IRP_MJ_WRITE, then the <b>RxContextSerializationQLinks.Flink</b> and <b>RxContextSerializationQLinks.Blink</b> members must be <b>NULL</b>.

</li>
</ul>
If either of the above conditions are not met, <b>RxPrepareContextForReuse</b> causes the system to ASSERT on checked builds.

The <b>RxPrepareContextForReuse </b>routine would normally only be used by network mini-redirector drivers that reinitialize RX_CONTEXT structures directly. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/rxprocs/nf-rxprocs-rxcompleterequest">RxCompleteRequest</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/rxprocs/nf-rxprocs-rxcompleterequest_real">RxCompleteRequest_Real</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/rxcontx/nf-rxcontx-rxcreaterxcontext">RxCreateRxContext</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/rxprocs/nf-rxprocs-rxdereference">RxDereference</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/rxcontx/nf-rxcontx-rxdereferenceanddeleterxcontext_real">RxDereferenceAndDeleteRxContext_Real</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/rxcontx/nf-rxcontx-rxinitializecontext">RxInitializeContext</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/rxcontx/nf-rxcontx-rxresumeblockedoperations_serially">RxResumeBlockedOperations_Serially</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/rxcontx/nf-rxcontx-__rxsynchronizeblockingoperations">__RxSynchronizeBlockingOperations</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/--rxsynchronizeblockingoperationsmaybedroppingfcblock">__RxSynchronizeBlockingOperationsMaybeDroppingFcbLock</a>
 

 

