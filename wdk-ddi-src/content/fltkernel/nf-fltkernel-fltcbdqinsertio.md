---
UID: NF:fltkernel.FltCbdqInsertIo
title: FltCbdqInsertIo function
author: windows-driver-content
description: FltCbdqInsertIo inserts the callback data structure for an I/O operation into a minifilter driver's callback data queue.
old-location: ifsk\fltcbdqinsertio.htm
old-project: ifsk
ms.assetid: d20d2626-89fb-4bc5-9309-88977b921078
ms.author: windowsdriverdev
ms.date: 2/7/2018
ms.keywords: FltCbdqInsertIo function [Installable File System Drivers], ifsk.fltcbdqinsertio, fltkernel/FltCbdqInsertIo, FltApiRef_a_to_d_d2635baa-958a-437b-88ca-9ee84df26d64.xml, FltCbdqInsertIo
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
-	FltCbdqInsertIo
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# FltCbdqInsertIo function


## -description


<i>FltCbdqInsertIo</i> inserts the callback data structure for an I/O operation into a minifilter driver's callback data queue. 


## -syntax


````
NTSTATUS FltCbdqInsertIo(
  _Inout_  PFLT_CALLBACK_DATA_QUEUE            Cbdq,
  _In_     PFLT_CALLBACK_DATA                  Cbd,
  _In_opt_ PFLT_CALLBACK_DATA_QUEUE_IO_CONTEXT Context,
  _In_opt_ PVOID                               InsertContext
);
````


## -parameters




### -param Cbdq [in, out]

Pointer to the caller's cancel-safe callback data queue. This queue must have been initialized by calling <a href="..\fltkernel\nf-fltkernel-fltcbdqinitialize.md">FltCbdqInitialize</a>. 


### -param Cbd [in]

Pointer to the callback data (<a href="..\fltkernel\ns-fltkernel-_flt_callback_data.md">FLT_CALLBACK_DATA</a>) structure for the I/O operation to be queued. The operation must be an IRP-based I/O operation. 


### -param Context [in, optional]

Caller-supplied variable that receives an opaque context pointer for the I/O request. Minifilter drivers can use this pointer to identify a specific item in the queue so that it can be removed by calling <a href="..\fltkernel\nf-fltkernel-fltcbdqremoveio.md">FltCbdqRemoveIo</a>. If the minifilter driver is not required to remove particular I/O requests from the queue, this parameter can be <b>NULL</b>. 


### -param InsertContext [in, optional]

Context pointer to be passed to the minifilter driver's <i>CbdqInsertIo</i> callback routine. 


## -returns



<i>FltCbdqInsertIo</i> returns STATUS_SUCCESS or an appropriate NTSTATUS value such as one of the following: 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_PENDING</b></dt>
</dl>
</td>
<td width="60%">
The callback data structure was inserted into the callback data queue. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_FLT_CBDQ_DISABLED</b></dt>
</dl>
</td>
<td width="60%">
The callback data structure was not inserted into the callback data queue because the queue is currently disabled. To reenable the queue, call <a href="..\fltkernel\nf-fltkernel-fltcbdqenable.md">FltCbdqEnable</a>. This is an error code. 

</td>
</tr>
</table>
 




## -remarks



<i>FltCbdqInsertIo</i> inserts the specified callback data (<a href="..\fltkernel\ns-fltkernel-_flt_callback_data.md">FLT_CALLBACK_DATA</a>) structure into a minifilter driver's callback data queue. 

Minifilter drivers can use the <b>FltCbdq</b><i>Xxx</i> routines to implement a callback data queue for IRP-based I/O operations. By using these routines, minifilter drivers can make their queues cancel-safe; the system transparently handles I/O cancellation for the minifilter drivers. 

The <b>FltCbdq</b><i>Xxx</i> routines can only be used for IRP-based I/O operations. To determine whether a given callback data structure represents an IRP-based I/O operation, use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544654">FLT_IS_IRP_OPERATION</a> macro. 

A callback data queue is initialized by calling <a href="..\fltkernel\nf-fltkernel-fltcbdqinitialize.md">FltCbdqInitialize</a>. <i>FltCbdqInsertIo</i> uses the functions provided in the queue's dispatch table to lock the queue and insert the callback data structure into the queue. The insert operation itself is performed by the queue's <i>CbdqInsertIo</i> routine.

See <a href="..\fltkernel\nf-fltkernel-fltcbdqinitialize.md">FltCbdqInitialize</a> for details on how to create a callback data queue. Use <a href="..\fltkernel\nf-fltkernel-fltcbdqremoveio.md">FltCbdqRemoveIo</a> to remove a particular I/O request from the queue, or <a href="..\fltkernel\nf-fltkernel-fltcbdqremovenextio.md">FltCbdqRemoveNextIo</a> to remove the next available I/O request.

If the queue is protected by a <a href="https://msdn.microsoft.com/0585fc2a-0d0b-434d-92b3-da07a9385444">spin lock</a> rather than a <a href="https://msdn.microsoft.com/e2142b6d-f460-4f80-be0f-e00b5d43731c">mutex object</a> or <a href="..\wdm\nf-wdm-exinitializeresourcelite.md">resource variable</a>, the caller of <i>FltCbdqInsertIo</i> can be running at IRQL &lt;= DISPATCH_LEVEL. If a mutex or resource is used, the caller must be running at IRQL &lt;= APC_LEVEL. 




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff544654">FLT_IS_IRP_OPERATION</a>



<a href="..\fltkernel\nf-fltkernel-fltcbdqenable.md">FltCbdqEnable</a>



<a href="..\fltkernel\nf-fltkernel-fltcbdqremovenextio.md">FltCbdqRemoveNextIo</a>



<a href="..\fltkernel\nf-fltkernel-fltcbdqinitialize.md">FltCbdqInitialize</a>



<a href="..\fltkernel\ns-fltkernel-_flt_callback_data_queue.md">FLT_CALLBACK_DATA_QUEUE</a>



<a href="..\fltkernel\ns-fltkernel-_flt_callback_data.md">FLT_CALLBACK_DATA</a>



<a href="..\fltkernel\nf-fltkernel-fltcbdqremoveio.md">FltCbdqRemoveIo</a>



<a href="..\fltkernel\nf-fltkernel-fltcbdqdisable.md">FltCbdqDisable</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltCbdqInsertIo function%20 RELEASE:%20(2/7/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

