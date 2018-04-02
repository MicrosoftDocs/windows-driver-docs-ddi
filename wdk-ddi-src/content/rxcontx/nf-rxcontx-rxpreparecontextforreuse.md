---
UID: NF:rxcontx.RxPrepareContextForReuse
title: RxPrepareContextForReuse function
author: windows-driver-content
description: RxPrepareContextForReuse prepares an RX_CONTEXT data structure for reuse by resetting all of the operation-specific allocations and acquisitions that have been made (the ReferenceCount member to the RX_CONTEXT structure is set to zero).
old-location: ifsk\rxpreparecontextforreuse.htm
old-project: ifsk
ms.assetid: 16b4bd82-0ffc-40c7-8cd2-f73a2a588ac8
ms.author: windowsdriverdev
ms.date: 3/29/2018
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
req.lib: 
req.dll: 
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	rxcontx.h
api_name:
-	RxPrepareContextForReuse
product: Windows
targetos: Windows
req.typenames: RILWRITEPHONEBOOKENTRYPARAMS, *LPRILWRITEPHONEBOOKENTRYPARAMS
req.product: Windows 10 or later.
---

# RxPrepareContextForReuse function


## -description


<b>RxPrepareContextForReuse</b> prepares an RX_CONTEXT data structure for reuse by resetting all of the operation-specific allocations and acquisitions that have been made (the <b>ReferenceCount</b> member to the RX_CONTEXT structure is set to zero). Parameters that have been obtained from the IRP are not modified. 


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




<a href="https://msdn.microsoft.com/library/windows/hardware/ff554340">RxCompleteRequest</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554348">RxCompleteRequest_Real</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554367">RxCreateRxContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554388">RxDereference</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554393">RxDereferenceAndDeleteRxContext_Real</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554502">RxInitializeContext</a>



<a href="https://msdn.microsoft.com/8418ed17-39f0-4a3b-9eb5-453c7cc2ae98">RxResumeBlockedOperations_Serially</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557377">__RxSynchronizeBlockingOperations</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557382">__RxSynchronizeBlockingOperationsMaybeDroppingFcbLock</a>
 

 

