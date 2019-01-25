---
UID: NF:fltkernel.FltCbdqRemoveIo
title: FltCbdqRemoveIo function (fltkernel.h)
description: FltCbdqRemoveIo removes a particular item from a minifilter driver's callback data queue.
old-location: ifsk\fltcbdqremoveio.htm
tech.root: ifsk
ms.assetid: 88ff23b0-502c-4b15-9037-e4ea75441722
ms.date: 04/16/2018
ms.keywords: FltApiRef_a_to_d_3d737d8a-141a-4a15-9b78-45a215f9fd25.xml, FltCbdqRemoveIo, FltCbdqRemoveIo function [Installable File System Drivers], fltkernel/FltCbdqRemoveIo, ifsk.fltcbdqremoveio
ms.topic: function
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
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
req.irql: See Remarks section.
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	fltkernel.h
api_name:
-	FltCbdqRemoveIo
product:
- Windows
targetos: Windows
req.typenames: 
---

# FltCbdqRemoveIo function


## -description


<i>FltCbdqRemoveIo</i> removes a particular item from a minifilter driver's callback data queue. 


## -parameters




### -param Cbdq [in, out]

Pointer to a cancel-safe callback data queue. This queue must have been initialized by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff541802">FltCbdqInitialize</a>. 


### -param Context [in]

Context pointer for the item to be removed. This context is initialized by <a href="https://msdn.microsoft.com/library/windows/hardware/ff541815">FltCbdqInsertIo</a> when the I/O request is first inserted in the queue. This parameter is required and must be non-<b>NULL</b>. 


## -returns



<i>FltCbdqRemoveIo</i> returns a pointer to the callback data structure for the I/O request that was removed from the queue. If no matching I/O request is found or if the queue is empty, <i>FltCbdqRemoveIo</i> returns <b>NULL</b>. 




## -remarks



<i>FltCbdqRemoveIo</i> removes the callback data (<a href="https://msdn.microsoft.com/library/windows/hardware/ff544620">FLT_CALLBACK_DATA</a>) structure for a particular I/O operation from a minifilter driver's callback data queue. <i>FltCbdqRemoveIo</i> can only be used to delete a callback data structure that has a <i>Context</i> structure associated with it. This association is created when the callback data structure is inserted into the callback data queue by <a href="https://msdn.microsoft.com/library/windows/hardware/ff541815">FltCbdqInsertIo</a>. 

Minifilter drivers can use the <b>FltCbdq</b><i>Xxx</i> routines to implement a callback data queue for IRP-based I/O operations. By using these routines, minifilter drivers can make their queues cancel-safe; the system transparently handles I/O cancellation for the minifilter drivers. 

The <b>FltCbdq</b><i>Xxx</i> routines can only be used for IRP-based I/O operations. To determine whether a given callback data structure represents an IRP-based I/O operation, use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544654">FLT_IS_IRP_OPERATION</a> macro. 

A callback data queue is initialized by <a href="https://msdn.microsoft.com/library/windows/hardware/ff541802">FltCbdqInitialize</a>. <i>FltCbdqRemoveIo</i> uses the routines provided in the queue's dispatch table to lock the queue and remove the callback data structure from the queue. The remove operation itself is performed by the minifilter driver's <i>CbdqRemoveIo</i> callback routine. 

If the queue is protected by a <a href="https://msdn.microsoft.com/0585fc2a-0d0b-434d-92b3-da07a9385444">spin lock</a> rather than a <a href="https://msdn.microsoft.com/e2142b6d-f460-4f80-be0f-e00b5d43731c">mutex object</a> or <a href="https://msdn.microsoft.com/be18a6e6-863d-4a0c-9bcd-a36ace0b54fe">resource variable</a>, the caller of <i>FltCbdqRemoveIo</i> can be running at IRQL &lt;= DISPATCH_LEVEL. If a mutex or resource is used, the caller must be running at IRQL &lt;= APC_LEVEL. 

There is a potential race between the filter manager removing a cancelled I/O request, and the filter driver removing it because it was completed. It is important to note that the request context remains valid after it is first removed, which will cause a second removal attempt to fail.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff544620">FLT_CALLBACK_DATA</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544624">FLT_CALLBACK_DATA_QUEUE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544654">FLT_IS_IRP_OPERATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541796">FltCbdqDisable</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541799">FltCbdqEnable</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541802">FltCbdqInitialize</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541815">FltCbdqInsertIo</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541825">FltCbdqRemoveNextIo</a>
 

 

