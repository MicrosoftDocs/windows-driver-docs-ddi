---
UID: NF:rxcontx.__RxSynchronizeBlockingOperations
title: "__RxSynchronizeBlockingOperations function"
author: windows-driver-content
description: "__RxSynchronizeBlockingOperations synchronizes blocking I/O requests to the same work queue."
old-location: ifsk\__rxsynchronizeblockingoperations.htm
old-project: ifsk
ms.assetid: e957f8bc-2ce3-4b9c-819e-ee068b39c4a0
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "__RxSynchronizeBlockingOperations, __RxSynchronizeBlockingOperations function [Installable File System Drivers], ifsk.__rxsynchronizeblockingoperations, rxcontx/__RxSynchronizeBlockingOperations, rxref_d35d9118-8942-402e-8c78-3168a2d9ad73.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: rxcontx.h
req.include-header: Rxcontx.h
req.target-type: Desktop
req.target-min-winverclnt: The __RxSynchronizeBlockingOperations routine is only available on Windows Server 2003.
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	rxcontx.h
api_name:
-	__RxSynchronizeBlockingOperations
product: Windows
targetos: Windows
req.typenames: RILWRITEPHONEBOOKENTRYPARAMS, *LPRILWRITEPHONEBOOKENTRYPARAMS
req.product: Windows 10 or later.
---

# __RxSynchronizeBlockingOperations function


## -description


<b>__RxSynchronizeBlockingOperations</b> synchronizes blocking I/O requests to the same work queue. 


## -syntax


````
NTSTATUS __RxSynchronizeBlockingOperations(
  _Inout_ PRX_CONTEXT RxContext,
  _In_    PFCB        Fcb,
  _Inout_ PLIST_ENTRY BlockingIoQ,
  _In_    BOOLEAN     DropFcbLock
);
````


## -parameters




### -param RxContext [in, out]

A pointer to the RX_CONTEXT of the operation being synchronized. 


### -param Fcb [in]

A pointer to the FCB. 


### -param BlockingIoQ [in, out]

A pointer to the LIST_ENTRY for the queue. 


### -param DropFcbLock [in]

A Boolean value that indicates if the FCB resource should be released. If this parameter is <b>TRUE</b>, then the FCB resource will be released. 


## -returns



<b>__RxSynchronizeBlockingOperations</b> returns STATUS_SUCCESS on success or an appropriate NTSTATUS value such as one of the following: 

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
The I/O request and the associated RX_CONTEXT was canceled.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_PENDING</b></dt>
</dl>
</td>
<td width="60%">
The <i>RxContext</i> was for an asynchronous operation and the <i>RxContext</i> has been added to the queue.

</td>
</tr>
</table>
 




## -remarks



The<b> __RxSynchronizeBlockingOperations</b> routine synchronizes blocking I/O requests to the same work queue. RDBSS uses <b>__RxSynchronizeBlockingOperations</b> internally to synchronize named pipe operations. The work queue is the queue referenced by the file object extension (FOBX) associated with the <i>Fcb</i>. 

A network mini-redirector may use <b>__RxSynchronizeBlockingOperations</b> to synchronize operations on a separate queue that is maintained by the network mini-redirector. 

If <i>RxContext</i> is marked for an asynchronous operation, <b>__RxSynchronizeBlockingOperations</b> will add the <i>RxContext</i> to the queue and return STATUS_PENDING. If <i>RxContext</i> is marked for a synchronous operation, <b>__RxSynchronizeBlockingOperations</b> will block and <i>RxContext</i> is resumed when a call is made to <a href="..\rxcontx\nf-rxcontx-rxresumeblockedoperations_serially.md">RxResumeBlockedOperations_Serially</a>. 

If the blocking I/O request was canceled, <b>__RxSynchronizeBlockingOperations</b> returns STATUS_CANCELLED to indicate the error.

The <b>SyncEvent</b> member of the RX_CONTEXT structure pointed to by <i>RxContext</i> must have been reset before calling <b>__RxSynchronizeBlockingOperations</b>. The FCB resource must be locked before calling <b>__RxSynchronizeBlockingOperations</b> if the <i>DropFcbLock</i> parameter is set to <b>TRUE</b>. 

The following two macros are defined on Windows Server 2003 or later for calling <b>__RxSynchronizeBlockingOperations</b>:

<b>RxSynchronizeBlockingOperations</b> - calls with the <i>DropFcbLock</i> parameter set to <b>FALSE</b>. 

<b>RxSynchronizeBlockingOperationsAndDropFcbLock</b> - calls with the <i>DropFcbLock</i> parameter set to <b>TRUE</b>. 




## -see-also

<a href="..\rxcontx\nf-rxcontx-rxinitializecontext.md">RxInitializeContext</a>



<a href="..\rxcontx\nf-rxcontx-rxpreparecontextforreuse.md">RxPrepareContextForReuse</a>



<a href="..\rxcontx\nf-rxcontx-rxcreaterxcontext.md">RxCreateRxContext</a>



<a href="..\rxprocs\nf-rxprocs-rxdereference.md">RxDereference</a>



<a href="..\rxcontx\nf-rxcontx-rxresumeblockedoperations_serially.md">RxResumeBlockedOperations_Serially</a>



<a href="..\rxcontx\nf-rxcontx-rxdereferenceanddeleterxcontext_real.md">RxDereferenceAndDeleteRxContext_Real</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557382">__RxSynchronizeBlockingOperationsMaybeDroppingFcbLock</a>



<a href="..\rxprocs\nf-rxprocs-rxcompleterequest_real.md">RxCompleteRequest_Real</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20__RxSynchronizeBlockingOperations function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

