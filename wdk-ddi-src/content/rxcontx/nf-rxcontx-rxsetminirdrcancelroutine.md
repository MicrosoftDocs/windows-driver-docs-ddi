---
UID: NF:rxcontx.RxSetMinirdrCancelRoutine
title: RxSetMinirdrCancelRoutine function (rxcontx.h)
description: RxSetMinirdrCancelRoutine is called by a network mini-redirector driver to set up a network mini-redirector cancel routine for an RX_CONTEXT structure.
old-location: ifsk\rxsetminirdrcancelroutine.htm
tech.root: ifsk
ms.assetid: 5b74b4c4-d1a3-4587-900a-b54eebfeb553
ms.date: 04/16/2018
ms.keywords: RxSetMinirdrCancelRoutine, RxSetMinirdrCancelRoutine routine [Installable File System Drivers], ifsk.rxsetminirdrcancelroutine, rxcontx/RxSetMinirdrCancelRoutine, rxref_5883f8a0-cc54-4efe-bb98-13239c78abff.xml
f1_keywords:
 - "rxcontx/RxSetMinirdrCancelRoutine"
req.header: rxcontx.h
req.include-header: Mrx.h, Rxcontx.h
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
- RxSetMinirdrCancelRoutine
product:
- Windows
targetos: Windows
req.typenames: 
---

# RxSetMinirdrCancelRoutine function


## -description


<b>RxSetMinirdrCancelRoutine</b> is called by a network mini-redirector driver to set up a network mini-redirector cancel routine for an RX_CONTEXT structure.


## -parameters




### -param RxContext [in, out]

A pointer to the RX_CONTEXT structure. 


### -param MRxCancelRoutine [in]

A pointer to a cancel routine. 


## -returns



<b>RxSetMinirdrCancelRoutine</b> returns STATUS_SUCCESS on success or one of the following error values on failure: 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_CANCELLED</b></dt>
</dl>
</td>
<td width="60%">
The <i>RxContext</i> parameter was already canceled. The error will be returned if the <b>Flags</b> member of <i>RxContext</i> has the RX_CONTEXT_FLAG_CANCELLED bit set. 

</td>
</tr>
</table>
 




## -remarks



The <b>RxSetMinirdrCancelRoutine</b> routine sets the <b>MRxCancelRoutine</b> member of the <i>RxContext</i> parameter to the value of the <i>MRxCancelRoutine</i> parameter. This operation is protected by a spinlock.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/rxcontx/ns-rxcontx-_rx_context">RX_CONTEXT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/rxprocs/nf-rxprocs-rxcompleterequest">RxCompleteRequest</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/rxprocs/nf-rxprocs-rxcompleterequest_real">RxCompleteRequest_Real</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/rxcontx/nf-rxcontx-rxcreaterxcontext">RxCreateRxContext</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/rxprocs/nf-rxprocs-rxdereference">RxDereference</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/rxcontx/nf-rxcontx-rxdereferenceanddeleterxcontext_real">RxDereferenceAndDeleteRxContext_Real</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/rxcontx/nf-rxcontx-rxinitializecontext">RxInitializeContext</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/rxcontx/nf-rxcontx-rxpreparecontextforreuse">RxPrepareContextForReuse</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/rxcontx/nf-rxcontx-rxresumeblockedoperations_serially">RxResumeBlockedOperations_Serially</a>
 

 

