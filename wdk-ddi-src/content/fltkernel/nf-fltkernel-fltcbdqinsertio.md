---
UID: NF:fltkernel.FltCbdqInsertIo
title: FltCbdqInsertIo function (fltkernel.h)
description: FltCbdqInsertIo inserts the callback data structure for an I/O operation into a minifilter driver's callback data queue.
old-location: ifsk\fltcbdqinsertio.htm
tech.root: ifsk
ms.assetid: d20d2626-89fb-4bc5-9309-88977b921078
ms.date: 04/16/2018
keywords: ["FltCbdqInsertIo function"]
ms.keywords: FltApiRef_a_to_d_d2635baa-958a-437b-88ca-9ee84df26d64.xml, FltCbdqInsertIo, FltCbdqInsertIo function [Installable File System Drivers], fltkernel/FltCbdqInsertIo, ifsk.fltcbdqinsertio
f1_keywords:
 - "fltkernel/FltCbdqInsertIo"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- fltkernel.h
api_name:
- FltCbdqInsertIo
product:
- Windows
targetos: Windows
req.typenames: 
---

# FltCbdqInsertIo function


## -description


<i>FltCbdqInsertIo</i> inserts the callback data structure for an I/O operation into a minifilter driver's callback data queue. 


## -parameters




### -param Cbdq [in, out]

Pointer to the caller's cancel-safe callback data queue. This queue must have been initialized by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltcbdqinitialize">FltCbdqInitialize</a>. 


### -param Cbd [in]

Pointer to the callback data (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_callback_data">FLT_CALLBACK_DATA</a>) structure for the I/O operation to be queued. The operation must be an IRP-based I/O operation. 


### -param Context [in, optional]

Caller-supplied variable that receives an opaque context pointer for the I/O request. Minifilter drivers can use this pointer to identify a specific item in the queue so that it can be removed by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltcbdqremoveio">FltCbdqRemoveIo</a>. If the minifilter driver is not required to remove particular I/O requests from the queue, this parameter can be <b>NULL</b>. 


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
The callback data structure was not inserted into the callback data queue because the queue is currently disabled. To reenable the queue, call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltcbdqenable">FltCbdqEnable</a>. This is an error code. 

</td>
</tr>
</table>
 




## -remarks



<i>FltCbdqInsertIo</i> inserts the specified callback data (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_callback_data">FLT_CALLBACK_DATA</a>) structure into a minifilter driver's callback data queue. 
* Note that there is a potential race condition between a filter driver inserting the callback data, and the associated IRP being cancelled. This can be avoided by immediately invoking the queue's cancellation routine if the IRP has already been cancelled. 

Minifilter drivers can use the <b>FltCbdq</b><i>Xxx</i> routines to implement a callback data queue for IRP-based I/O operations. By using these routines, minifilter drivers can make their queues cancel-safe; the system transparently handles I/O cancellation for the minifilter drivers. 

The <b>FltCbdq</b><i>Xxx</i> routines can only be used for IRP-based I/O operations. To determine whether a given callback data structure represents an IRP-based I/O operation, use the <a href="https://docs.microsoft.com/previous-versions/ff544654(v=vs.85)">FLT_IS_IRP_OPERATION</a> macro. 

A callback data queue is initialized by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltcbdqinitialize">FltCbdqInitialize</a>. <i>FltCbdqInsertIo</i> uses the functions provided in the queue's dispatch table to lock the queue and insert the callback data structure into the queue. The insert operation itself is performed by the queue's <i>CbdqInsertIo</i> routine.

See <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltcbdqinitialize">FltCbdqInitialize</a> for details on how to create a callback data queue. Use <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltcbdqremoveio">FltCbdqRemoveIo</a> to remove a particular I/O request from the queue, or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltcbdqremovenextio">FltCbdqRemoveNextIo</a> to remove the next available I/O request.

If the queue is protected by a <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/spin-locks">spin lock</a> rather than a <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/mutex-objects">mutex object</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exinitializeresourcelite">resource variable</a>, the caller of <i>FltCbdqInsertIo</i> can be running at IRQL <= DISPATCH_LEVEL. If a mutex or resource is used, the caller must be running at IRQL <= APC_LEVEL. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_callback_data">FLT_CALLBACK_DATA</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_callback_data_queue">FLT_CALLBACK_DATA_QUEUE</a>



<a href="https://docs.microsoft.com/previous-versions/ff544654(v=vs.85)">FLT_IS_IRP_OPERATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltcbdqdisable">FltCbdqDisable</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltcbdqenable">FltCbdqEnable</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltcbdqinitialize">FltCbdqInitialize</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltcbdqremoveio">FltCbdqRemoveIo</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltcbdqremovenextio">FltCbdqRemoveNextIo</a>
 

 

