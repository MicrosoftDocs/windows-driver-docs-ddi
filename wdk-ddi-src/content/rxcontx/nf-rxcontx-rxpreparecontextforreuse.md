---
UID: NF:rxcontx.RxPrepareContextForReuse
title: RxPrepareContextForReuse function
author: windows-driver-content
description: RxPrepareContextForReuse prepares an RX_CONTEXT data structure for reuse by resetting all of the operation-specific allocations and acquisitions that have been made (the ReferenceCount member to the RX_CONTEXT structure is set to zero).
old-location: ifsk\rxpreparecontextforreuse.htm
old-project: ifsk
ms.assetid: 16b4bd82-0ffc-40c7-8cd2-f73a2a588ac8
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RxPrepareContextForReuse, RxPrepareContextForReuse function [Installable File System Drivers], ifsk.rxpreparecontextforreuse, rxcontx/RxPrepareContextForReuse, rxref_34eae0cd-faff-47e7-8313-aca1361edc68.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
-	RxPrepareContextForReuse
product: Windows
targetos: Windows
req.typenames: RILWRITEPHONEBOOKENTRYPARAMS, *LPRILWRITEPHONEBOOKENTRYPARAMS
req.product: Windows 10 or later.
---

# RxPrepareContextForReuse function


## -description


<b>RxPrepareContextForReuse</b> prepares an RX_CONTEXT data structure for reuse by resetting all of the operation-specific allocations and acquisitions that have been made (the <b>ReferenceCount</b> member to the RX_CONTEXT structure is set to zero). Parameters that have been obtained from the IRP are not modified. 


## -syntax


````
VOID RxPrepareContextForReuse(
  _Inout_ PRX_CONTEXT RxContext
);
````


## -parameters




### -param RxContext [in, out]

A pointer to the RX_CONTEXT structure.


## -returns



None 




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

<a href="..\rxcontx\nf-rxcontx-rxdereferenceanddeleterxcontext_real.md">RxDereferenceAndDeleteRxContext_Real</a>



<a href="..\rxprocs\nf-rxprocs-rxdereference.md">RxDereference</a>



<a href="..\rxcontx\nf-rxcontx-rxresumeblockedoperations_serially.md">RxResumeBlockedOperations_Serially</a>



<a href="..\rxprocs\nf-rxprocs-rxcompleterequest.md">RxCompleteRequest</a>



<a href="..\rxcontx\nf-rxcontx-rxinitializecontext.md">RxInitializeContext</a>



<a href="..\rxcontx\nf-rxcontx-rxcreaterxcontext.md">RxCreateRxContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557382">__RxSynchronizeBlockingOperationsMaybeDroppingFcbLock</a>



<a href="..\rxcontx\nf-rxcontx-__rxsynchronizeblockingoperations.md">__RxSynchronizeBlockingOperations</a>



<a href="..\rxprocs\nf-rxprocs-rxcompleterequest_real.md">RxCompleteRequest_Real</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RxPrepareContextForReuse function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

