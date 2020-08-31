---
UID: NC:fltkernel.PFLT_COMPLETED_ASYNC_IO_CALLBACK
title: PFLT_COMPLETED_ASYNC_IO_CALLBACK (fltkernel.h)
description: A minifilter driver that initiates an asynchronous I/O operation can specify a routine of type PFLT_COMPLETED_ASYNC_IO_CALLBACK routine to be called when the operation is completed.
old-location: ifsk\pflt_completed_async_io_callback.htm
tech.root: ifsk
ms.assetid: 920e4236-9078-41c6-befb-9e82accbfa59
ms.date: 03/29/2018
keywords: ["PFLT_COMPLETED_ASYNC_IO_CALLBACK callback"]
ms.keywords: FltCallbacks_b85c12a6-7d3b-4d0c-9d21-9d9613aa057c.xml, PFLT_COMPLETED_ASYNC_IO_CALLBACK, PFLT_COMPLETED_ASYNC_IO_CALLBACK function pointer [Installable File System Drivers], fltkernel/PFLT_COMPLETED_ASYNC_IO_CALLBACK, ifsk.pflt_completed_async_io_callback
req.header: fltkernel.h
req.include-header: Fltkernel.h
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
req.irql: See Remarks section.
targetos: Windows
req.typenames: EXpsFontRestriction
f1_keywords:
 - PFLT_COMPLETED_ASYNC_IO_CALLBACK
 - fltkernel/PFLT_COMPLETED_ASYNC_IO_CALLBACK
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - fltkernel.h
api_name:
 - PFLT_COMPLETED_ASYNC_IO_CALLBACK
---

# PFLT_COMPLETED_ASYNC_IO_CALLBACK callback


## -description

A minifilter driver that initiates an asynchronous I/O operation can specify a routine of type PFLT_COMPLETED_ASYNC_IO_CALLBACK routine to be called when the operation is completed.

## -parameters

### -param CallbackData 

[in]
Pointer to the callback data structure for the I/O operation.

### -param Context 

[in]
Context pointer that the minifilter driver passed as a parameter to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltperformasynchronousio">FltPerformAsynchronousIo</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltreadfile">FltReadFile</a>, or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltwritefile">FltWriteFile</a>.

## -remarks

When a minifilter driver calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltperformasynchronousio">FltPerformAsynchronousIo</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltreadfile">FltReadFile</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltwritefile">FltWriteFile</a> to initiate an asynchronous I/O operation, the minifilter driver can optionally specify a callback routine to be called when the I/O operation is completed. This is done by specifying a routine of type PFLT_COMPLETED_ASYNC_IO_CALLBACK for the <i>CallbackRoutine</i> parameter.

When the I/O operation is completed, this callback routine is called in an arbitrary thread context, at IRQL <= DISPATCH_LEVEL.

Because the PFLT_COMPLETED_ASYNC_IO_CALLBACK routine can be called at IRQL DISPATCH_LEVEL, it is subject to the following constraints:

<ul>
<li>
It cannot safely call any kernel-mode routines that require a lower IRQL.

</li>
<li>
Any data structures used in this routine must be allocated from nonpaged pool.

</li>
<li>
It cannot be made pageable.

</li>
<li>
It cannot acquire resources, mutexes, or fast mutexes. However, it can acquire spin locks.

</li>
</ul>

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_callback_data">FLT_CALLBACK_DATA</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltperformasynchronousio">FltPerformAsynchronousIo</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltreadfile">FltReadFile</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltwritefile">FltWriteFile</a>

