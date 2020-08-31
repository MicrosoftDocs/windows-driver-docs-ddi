---
UID: NF:rxcontx.RxCreateRxContext
title: RxCreateRxContext function (rxcontx.h)
description: RxCreateRxContext allocates a new RX_CONTEXT structure and initializes the data structure.
old-location: ifsk\rxcreaterxcontext.htm
tech.root: ifsk
ms.assetid: ff39aebb-03c0-4ba4-844a-417579ed2bbf
ms.date: 04/16/2018
keywords: ["RxCreateRxContext function"]
ms.keywords: RxCreateRxContext, RxCreateRxContext function [Installable File System Drivers], ifsk.rxcreaterxcontext, rxcontx/RxCreateRxContext, rxref_ceb498ca-e985-4100-a104-8333abb41fdf.xml
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
targetos: Windows
req.typenames: 
f1_keywords:
 - RxCreateRxContext
 - rxcontx/RxCreateRxContext
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - rxcontx.h
api_name:
 - RxCreateRxContext
---

# RxCreateRxContext function


## -description

<b>RxCreateRxContext</b> allocates a new RX_CONTEXT structure and initializes the data structure.

## -parameters

### -param Irp 

[in, optional]
A pointer to the IRP to be encapsulated by this RX_CONTEXT structure.

### -param RxDeviceObject 

[in]
A pointer to the device object to which this RX_CONTEXT and IRP apply.

### -param InitialContextFlags 

[in]
The set of initial values for the <b>Flags</b> member of the RX_CONTEXT data structure to be stored in the RX_CONTEXT structure. These initial values can be any combination of the following enumerations:





#### RX_CONTEXT_FLAG_WAIT

When this value is set, the IRP should be not be posted for later execution by the file system process, but should be waited on to complete.



#### RX_CONTEXT_FLAG_MUST_SUCCEED

When this value is set, the operation must succeed. This value is not currently used by RDBSS, but it may be used by network mini-redirector drivers. 



#### RX_CONTEXT_FLAG_MUST_SUCCEED_NONBLOCKING

When this value is set, the operation must succeed for non-blocking operations. This value is not currently used by RDBSS, but it may be used by network mini-redirector drivers.

## -returns

<b>RxCreateRxContext</b> returns a pointer to an allocated RX_CONTEXT data structure on success or a <b>NULL</b> pointer on failure.

## -remarks

<b>RxCreateRxContext</b> calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/rxcontx/nf-rxcontx-rxinitializecontext">RxInitializeContext</a> to initialize the newly created RX_CONTEXT structure before returning. 

<b>RxCreateRxContext</b> allocates non-paged pool memory when creating a new RX_CONTEXT data structure and sets the following value in the Flags member of the RX_CONTEXT:



When this value is set, the RX_CONTEXT structure was allocated from non-paged pool memory.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/rxcontx/ns-rxcontx-_rx_context">RX_CONTEXT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/rxprocs/nf-rxprocs-rxcompleterequest">RxCompleteRequest</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/rxprocs/nf-rxprocs-rxcompleterequest_real">RxCompleteRequest_Real</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/rxprocs/nf-rxprocs-rxdereference">RxDereference</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/rxcontx/nf-rxcontx-rxdereferenceanddeleterxcontext_real">RxDereferenceAndDeleteRxContext_Real</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/rxcontx/nf-rxcontx-rxinitializecontext">RxInitializeContext</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/rxcontx/nf-rxcontx-rxpreparecontextforreuse">RxPrepareContextForReuse</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/rxcontx/nf-rxcontx-rxresumeblockedoperations_serially">RxResumeBlockedOperations_Serially</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/rxcontx/nf-rxcontx-__rxsynchronizeblockingoperations">__RxSynchronizeBlockingOperations</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/--rxsynchronizeblockingoperationsmaybedroppingfcblock">__RxSynchronizeBlockingOperationsMaybeDroppingFcbLock</a>

