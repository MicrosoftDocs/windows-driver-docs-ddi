---
UID: NF:fltkernel.FltCbdqRemoveIo
title: FltCbdqRemoveIo function
author: windows-driver-content
description: FltCbdqRemoveIo removes a particular item from a minifilter driver's callback data queue.
old-location: ifsk\fltcbdqremoveio.htm
old-project: ifsk
ms.assetid: 88ff23b0-502c-4b15-9037-e4ea75441722
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: fltkernel/FltCbdqRemoveIo, FltCbdqRemoveIo function [Installable File System Drivers], FltApiRef_a_to_d_3d737d8a-141a-4a15-9b78-45a215f9fd25.xml, ifsk.fltcbdqremoveio, FltCbdqRemoveIo
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: See Remarks section.
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	fltkernel.h
apiname:
-	FltCbdqRemoveIo
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# FltCbdqRemoveIo function


## -description


<i>FltCbdqRemoveIo</i> removes a particular item from a minifilter driver's callback data queue. 


## -syntax


````
PFLT_CALLBACK_DATA FltCbdqRemoveIo(
  _Inout_ PFLT_CALLBACK_DATA_QUEUE            Cbdq,
  _In_    PFLT_CALLBACK_DATA_QUEUE_IO_CONTEXT Context
);
````


## -parameters




### -param Cbdq [in, out]

Pointer to a cancel-safe callback data queue. This queue must have been initialized by calling <a href="..\fltkernel\nf-fltkernel-fltcbdqinitialize.md">FltCbdqInitialize</a>. 


### -param Context [in]

Context pointer for the item to be removed. This context is initialized by <a href="..\fltkernel\nf-fltkernel-fltcbdqinsertio.md">FltCbdqInsertIo</a> when the I/O request is first inserted in the queue. This parameter is required and must be non-<b>NULL</b>. 


## -returns



<i>FltCbdqRemoveIo</i> returns a pointer to the callback data structure for the I/O request that was removed from the queue. If no matching I/O request is found or if the queue is empty, <i>FltCbdqRemoveIo</i> returns <b>NULL</b>. 




## -remarks



<i>FltCbdqRemoveIo</i> removes the callback data (<a href="..\fltkernel\ns-fltkernel-_flt_callback_data.md">FLT_CALLBACK_DATA</a>) structure for a particular I/O operation from a minifilter driver's callback data queue. <i>FltCbdqRemoveIo</i> can only be used to delete a callback data structure that has a <i>Context</i> structure associated with it. This association is created when the callback data structure is inserted into the callback data queue by <a href="..\fltkernel\nf-fltkernel-fltcbdqinsertio.md">FltCbdqInsertIo</a>. 

Minifilter drivers can use the <b>FltCbdq</b><i>Xxx</i> routines to implement a callback data queue for IRP-based I/O operations. By using these routines, minifilter drivers can make their queues cancel-safe; the system transparently handles I/O cancellation for the minifilter drivers. 

The <b>FltCbdq</b><i>Xxx</i> routines can only be used for IRP-based I/O operations. To determine whether a given callback data structure represents an IRP-based I/O operation, use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544654">FLT_IS_IRP_OPERATION</a> macro. 

A callback data queue is initialized by <a href="..\fltkernel\nf-fltkernel-fltcbdqinitialize.md">FltCbdqInitialize</a>. <i>FltCbdqRemoveIo</i> uses the routines provided in the queue's dispatch table to lock the queue and remove the callback data structure from the queue. The remove operation itself is performed by the minifilter driver's <i>CbdqRemoveIo</i> callback routine. 

If the queue is protected by a <a href="https://msdn.microsoft.com/0585fc2a-0d0b-434d-92b3-da07a9385444">spin lock</a> rather than a <a href="https://msdn.microsoft.com/e2142b6d-f460-4f80-be0f-e00b5d43731c">mutex object</a> or <a href="..\wdm\nf-wdm-exinitializeresourcelite.md">resource variable</a>, the caller of <i>FltCbdqRemoveIo</i> can be running at IRQL &lt;= DISPATCH_LEVEL. If a mutex or resource is used, the caller must be running at IRQL &lt;= APC_LEVEL. 




## -see-also

<a href="..\fltkernel\ns-fltkernel-_flt_callback_data.md">FLT_CALLBACK_DATA</a>



<a href="..\fltkernel\ns-fltkernel-_flt_callback_data_queue.md">FLT_CALLBACK_DATA_QUEUE</a>



<a href="..\fltkernel\nf-fltkernel-fltcbdqremovenextio.md">FltCbdqRemoveNextIo</a>



<a href="..\fltkernel\nf-fltkernel-fltcbdqenable.md">FltCbdqEnable</a>



<a href="..\fltkernel\ns-fltkernel-_flt_callback_data_queue.md">FLT_CALLBACK_DATA_QUEUE</a>



<a href="..\fltkernel\nf-fltkernel-fltcbdqdisable.md">FltCbdqDisable</a>



<a href="..\fltkernel\nf-fltkernel-fltcbdqinitialize.md">FltCbdqInitialize</a>



<a href="..\fltkernel\ns-fltkernel-_flt_callback_data.md">FLT_CALLBACK_DATA</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltCbdqRemoveIo function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

