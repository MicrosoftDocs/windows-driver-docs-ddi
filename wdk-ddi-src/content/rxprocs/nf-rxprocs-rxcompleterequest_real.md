---
UID: NF:rxprocs.RxCompleteRequest_Real
title: RxCompleteRequest_Real function (rxprocs.h)
description: RxCompleteRequest_Real completes the IRP request associated with an RX_CONTEXT structure.
old-location: ifsk\rxcompleterequest_real.htm
tech.root: ifsk
ms.assetid: 54d8fab2-bde3-4b8a-8542-075c5e30afbb
ms.date: 04/16/2018
keywords: ["RxCompleteRequest_Real function"]
ms.keywords: RxCompleteRequest_Real, RxCompleteRequest_Real function [Installable File System Drivers], ifsk.rxcompleterequest_real, rxprocs/RxCompleteRequest_Real, rxref_9d779281-7e95-45b7-a633-62a4280a6bea.xml
f1_keywords:
 - "rxprocs/RxCompleteRequest_Real"
 - "RxCompleteRequest_Real"
req.header: rxprocs.h
req.include-header: Rxprocs.h, Rxcontx.h
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
- rxprocs.h
api_name:
- RxCompleteRequest_Real
targetos: Windows
req.typenames: 
---

# RxCompleteRequest_Real function


## -description


<b>RxCompleteRequest_Real</b> completes the IRP request associated with an RX_CONTEXT structure.


## -parameters




### -param RxContext 
[in]
A pointer to the RX_CONTEXT structure associated with the IRP to complete.


### -param Irp 
[in]
A pointer to the IRP to complete.


### -param Status 
[in]
The status value to return when the IRP request is complete. This is the value that will be stored in the <b>IoStatus.Status</b> member of the associated IRP on completion.


## -remarks



The <b>RxCompleteRequest_Real</b> routine is not normally called by network mini-redirector drivers directly. RDBSS calls this routine internally to complete an I/O request packet. 

If a <b>NULL</b> value is passed in for <i>Irp</i>, then <b>RxCompleteRequest_Real</b> will log this as an error in checked builds. If a non-<b>NULL</b> value is passed in for <i>RxContex</i>t, then <b>RxCompleteRequest_Real</b> internally calls <b>RxDereferenceAndDeleteRxContext</b> with the passed in <i>RxContext</i> parameter to dereference the RX_CONTEXT structure. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/rxprocs/nf-rxprocs-rxcompleterequest">RxCompleteRequest</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/rxcontx/nf-rxcontx-rxcreaterxcontext">RxCreateRxContext</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/rxprocs/nf-rxprocs-rxdereference">RxDereference</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/rxcontx/nf-rxcontx-rxdereferenceanddeleterxcontext_real">RxDereferenceAndDeleteRxContext_Real</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/rxcontx/nf-rxcontx-rxinitializecontext">RxInitializeContext</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/rxcontx/nf-rxcontx-rxpreparecontextforreuse">RxPrepareContextForReuse</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/rxcontx/nf-rxcontx-rxresumeblockedoperations_serially">RxResumeBlockedOperations_Serially</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/rxcontx/nf-rxcontx-__rxsynchronizeblockingoperations">__RxSynchronizeBlockingOperations</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/--rxsynchronizeblockingoperationsmaybedroppingfcblock">__RxSynchronizeBlockingOperationsMaybeDroppingFcbLock</a>
 

 

