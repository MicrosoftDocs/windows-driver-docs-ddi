---
UID: NF:rxcontx.RxCreateRxContext
title: RxCreateRxContext function
author: windows-driver-content
description: RxCreateRxContext allocates a new RX_CONTEXT structure and initializes the data structure.
old-location: ifsk\rxcreaterxcontext.htm
old-project: ifsk
ms.assetid: ff39aebb-03c0-4ba4-844a-417579ed2bbf
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: RxCreateRxContext, RxCreateRxContext function [Installable File System Drivers], ifsk.rxcreaterxcontext, rxcontx/RxCreateRxContext, rxref_ceb498ca-e985-4100-a104-8333abb41fdf.xml
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
-	RxCreateRxContext
product: Windows
targetos: Windows
req.typenames: 
---

# RxCreateRxContext function


## -description


<b>RxCreateRxContext</b> allocates a new RX_CONTEXT structure and initializes the data structure. 


## -parameters




### -param Irp [in, optional]

A pointer to the IRP to be encapsulated by this RX_CONTEXT structure.


### -param RxDeviceObject [in]

A pointer to the device object to which this RX_CONTEXT and IRP apply.


### -param InitialContextFlags [in]

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



<b>RxCreateRxContext</b> calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff554502">RxInitializeContext</a> to initialize the newly created RX_CONTEXT structure before returning. 

<b>RxCreateRxContext</b> allocates non-paged pool memory when creating a new RX_CONTEXT data structure and sets the following value in the Flags member of the RX_CONTEXT:



When this value is set, the RX_CONTEXT structure was allocated from non-paged pool memory.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff554751">RX_CONTEXT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554340">RxCompleteRequest</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554348">RxCompleteRequest_Real</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554388">RxDereference</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554393">RxDereferenceAndDeleteRxContext_Real</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554502">RxInitializeContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554643">RxPrepareContextForReuse</a>



<a href="https://msdn.microsoft.com/8418ed17-39f0-4a3b-9eb5-453c7cc2ae98">RxResumeBlockedOperations_Serially</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557377">__RxSynchronizeBlockingOperations</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557382">__RxSynchronizeBlockingOperationsMaybeDroppingFcbLock</a>
 

 

