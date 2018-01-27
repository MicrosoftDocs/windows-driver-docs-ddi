---
UID: NF:rxprocs.RxCompleteRequest
title: RxCompleteRequest function
author: windows-driver-content
description: RxCompleteRequest completes the IRP request associated with an RX_CONTEXT structure.
old-location: ifsk\rxcompleterequest.htm
old-project: ifsk
ms.assetid: f5e9219b-0697-427e-b92e-7cd647a0e0b6
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: ifsk.rxcompleterequest, RxCompleteRequest function [Installable File System Drivers], rxprocs/RxCompleteRequest, RxCompleteRequest, rxref_12eec336-4619-430c-a36c-ddbe855b8865.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: <= APC_LEVEL
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	HeaderDef
apilocation: 
-	rxprocs.h
apiname: 
-	RxCompleteRequest
product: Windows
targetos: Windows
req.typenames: *PRX_CONTEXT, RX_CONTEXT
req.product: Windows 10 or later.
---

# RxCompleteRequest function


## -description


<b>RxCompleteRequest</b> completes the IRP request associated with an RX_CONTEXT structure.


## -syntax


````
NTSTATUS RxCompleteRequest(
   PRX_CONTEXT RxContext,
   NTSTATUS    Status
);
````


## -parameters




### -param pContext

TBD


### -param Status

The status value to return when the IRP request is complete. This is the value that will be stored in the <b>IoStatus.Status</b> member of the associated IRP on completion.


#### - RxContext

A pointer to the RX_CONTEXT. This parameter contains the IRP requesting the operation to complete. 


## -returns


<b>RxCompleteRequest</b> returns the value of the <i>Status</i> parameter.



## -remarks


The <b>RxCompleteRequest</b> routine is not normally called by network mini-redirector drivers directly. RDBSS calls this routine internally to complete an I/O request packet. 

<b>RxCompleteRequest</b> internally calls <b>RxCompleteRequest_Real</b> to complete the request. Before calling <b>RxCompleteRequest_Real</b>, the <b>RxCompleteRequest</b> routine checks the value of the <b>LoudCompletionString</b> member in the RX_CONTEXT structure pointed to by the <i>RxContext</i> parameter and prints extra debugging information if <i>Status</i> is not equal to STATUS_SUCCESS. 



## -see-also

<a href="..\rxcontx\nf-rxcontx-rxresumeblockedoperations_serially.md">RxResumeBlockedOperations_Serially</a>

<a href="..\rxprocs\nf-rxprocs-rxcompleterequest_real.md">RxCompleteRequest_Real</a>

<a href="..\rxcontx\nf-rxcontx-rxdereferenceanddeleterxcontext_real.md">RxDereferenceAndDeleteRxContext_Real</a>

<a href="..\rxcontx\nf-rxcontx-rxcreaterxcontext.md">RxCreateRxContext</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff557382">__RxSynchronizeBlockingOperationsMaybeDroppingFcbLock</a>

<a href="..\rxcontx\nf-rxcontx-__rxsynchronizeblockingoperations.md">__RxSynchronizeBlockingOperations</a>

<a href="..\rxcontx\nf-rxcontx-rxpreparecontextforreuse.md">RxPrepareContextForReuse</a>

<a href="..\rxprocs\nf-rxprocs-rxdereference.md">RxDereference</a>

<a href="..\rxcontx\nf-rxcontx-rxinitializecontext.md">RxInitializeContext</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RxCompleteRequest function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

