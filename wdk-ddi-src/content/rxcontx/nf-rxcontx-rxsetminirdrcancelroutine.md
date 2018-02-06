---
UID: NF:rxcontx.RxSetMinirdrCancelRoutine
title: RxSetMinirdrCancelRoutine function
author: windows-driver-content
description: RxSetMinirdrCancelRoutine is called by a network mini-redirector driver to set up a network mini-redirector cancel routine for an RX_CONTEXT structure.
old-location: ifsk\rxsetminirdrcancelroutine.htm
old-project: ifsk
ms.assetid: 5b74b4c4-d1a3-4587-900a-b54eebfeb553
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: RxSetMinirdrCancelRoutine routine [Installable File System Drivers], rxref_5883f8a0-cc54-4efe-bb98-13239c78abff.xml, rxcontx/RxSetMinirdrCancelRoutine, RxSetMinirdrCancelRoutine, ifsk.rxsetminirdrcancelroutine
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: "<= APC_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	rxcontx.h
apiname:
-	RxSetMinirdrCancelRoutine
product: Windows
targetos: Windows
req.typenames: RILWRITEPHONEBOOKENTRYPARAMS, *LPRILWRITEPHONEBOOKENTRYPARAMS
req.product: Windows 10 or later.
---

# RxSetMinirdrCancelRoutine function


## -description


<b>RxSetMinirdrCancelRoutine</b> is called by a network mini-redirector driver to set up a network mini-redirector cancel routine for an RX_CONTEXT structure.


## -syntax


````
NTSTATUS RxSetMinirdrCancelRoutine(
  _Inout_ PRX_CONTEXT   RxContext,
  _In_    PMRX_CALLDOWN MRxCancelRoutine
);
````


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

<a href="..\rxcontx\nf-rxcontx-rxdereferenceanddeleterxcontext_real.md">RxDereferenceAndDeleteRxContext_Real</a>

<a href="..\rxprocs\nf-rxprocs-rxcompleterequest_real.md">RxCompleteRequest_Real</a>

<a href="..\rxcontx\nf-rxcontx-rxinitializecontext.md">RxInitializeContext</a>

<a href="..\rxcontx\ns-rxcontx-_rx_context.md">RX_CONTEXT</a>

<a href="..\rxcontx\nf-rxcontx-rxresumeblockedoperations_serially.md">RxResumeBlockedOperations_Serially</a>

<a href="..\rxprocs\nf-rxprocs-rxcompleterequest.md">RxCompleteRequest</a>

<a href="..\rxprocs\nf-rxprocs-rxdereference.md">RxDereference</a>

<a href="..\rxcontx\nf-rxcontx-rxcreaterxcontext.md">RxCreateRxContext</a>

<a href="..\rxcontx\nf-rxcontx-rxpreparecontextforreuse.md">RxPrepareContextForReuse</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RxSetMinirdrCancelRoutine routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

