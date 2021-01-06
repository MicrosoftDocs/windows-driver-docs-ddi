---
UID: NF:fltkernel.FltCbdqInsertIo
title: FltCbdqInsertIo function (fltkernel.h)
description: FltCbdqInsertIo inserts the callback data structure for an I/O operation into a filter driver's callback data queue.
old-location: ifsk\fltcbdqinsertio.htm
tech.root: ifsk
ms.date: 01/04/2021
keywords: ["FltCbdqInsertIo function"]
ms.keywords: FltApiRef_a_to_d_d2635baa-958a-437b-88ca-9ee84df26d64.xml, FltCbdqInsertIo, FltCbdqInsertIo function [Installable File System Drivers], fltkernel/FltCbdqInsertIo, ifsk.fltcbdqinsertio
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
targetos: Windows
req.typenames: 
f1_keywords:
 - FltCbdqInsertIo
 - fltkernel/FltCbdqInsertIo
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - fltkernel.h
api_name:
 - FltCbdqInsertIo
---

# FltCbdqInsertIo function

## -description

**FltCbdqInsertIo** inserts the callback data structure for an I/O operation into a filter driver's callback data queue.

## -parameters

### -param Cbdq

[in, out]
Pointer to the caller's cancel-safe callback data queue. This queue must have been initialized by calling [**FltCbdqInitialize**](nf-fltkernel-fltcbdqinitialize.md).

### -param Cbd

[in]
Pointer to the callback data ([**FLT_CALLBACK_DATA**](ns-fltkernel-_flt_callback_data.md)) structure for the I/O operation to be queued. The operation must be an IRP-based I/O operation.

### -param Context

[in, optional]
Caller-supplied variable that receives an opaque context pointer for the I/O request. Filter drivers can use this pointer to identify a specific item in the queue so that it can be removed by calling [**FltCbdqRemoveIo**](nf-fltkernel-fltcbdqremoveio.md). If the filter driver is not required to remove particular I/O requests from the queue, this parameter can be **NULL**.

### -param InsertContext

[in, optional]
Context pointer to be passed to the filter driver's *CbdqInsertIo* callback routine.

## -returns

**FltCbdqInsertIo** returns STATUS_SUCCESS when the callback data structure was inserted into the callback data queue, or an appropriate NTSTATUS value such as the following:

| Return code | Description |
| ----------- | ----------- |
| STATUS_FLT_CBDQ_DISABLED | The callback data structure was not inserted into the callback data queue because the queue is currently disabled. To reenable the queue, call [**FltCbdqEnable**](nf-fltkernel-fltcbdqenable.md). This is an error code. |

> [!NOTE]
> In the case of success, **FltCbdqInsertIo** returns whatever the filter's *InsertIo* callback returns; for example, a filter might return either STATUS_SUCCESS or STATUS_PENDING to indicate success. It is important that the filter be self-consistent on whichever value it uses to indicate success.

## -remarks

**FltCbdqInsertIo** inserts the specified callback data ([**FLT_CALLBACK_DATA**](ns-fltkernel-_flt_callback_data.md)) structure into a filter driver's callback data queue.

* Note that there is a potential race condition between a filter driver inserting the callback data, and the associated IRP being cancelled. This can be avoided by immediately invoking the queue's cancellation routine if the IRP has already been cancelled.

Filter drivers can use the **FltCbdq***Xxx* routines to implement a callback data queue for IRP-based I/O operations. By using these routines, filter drivers can make their queues cancel-safe; the system transparently handles I/O cancellation for the filter drivers.

The **FltCbdq***Xxx* routines can only be used for IRP-based I/O operations. To determine whether a given callback data structure represents an IRP-based I/O operation, use the [**FLT_IS_IRP_OPERATION**](/previous-versions/ff544654(v=vs.85)) macro.

A callback data queue is initialized by calling [**FltCbdqInitialize**](nf-fltkernel-fltcbdqinitialize.md). **FltCbdqInsertIo** uses the functions provided in the queue's dispatch table to lock the queue and insert the callback data structure into the queue. The insert operation itself is performed by the queue's *CbdqInsertIo* routine.

See [**FltCbdqInitialize**](nf-fltkernel-fltcbdqinitialize.md) for details on how to create a callback data queue. Use [**FltCbdqRemoveIo**](nf-fltkernel-fltcbdqremoveio.md) to remove a particular I/O request from the queue, or [**FltCbdqRemoveNextIo**](nf-fltkernel-fltcbdqremovenextio.md) to remove the next available I/O request.

If the queue is protected by a [spin lock](/windows-hardware/drivers/kernel/spin-locks) rather than a [mutex object](/windows-hardware/drivers/kernel/mutex-objects) or [resource variable](/windows-hardware/drivers/ddi/wdm/nf-wdm-exinitializeresourcelite), the caller of **FltCbdqInsertIo** can be running at IRQL <= DISPATCH_LEVEL. If a mutex or resource is used, the caller must be running at IRQL <= APC_LEVEL.

## -see-also

[**FLT_CALLBACK_DATA**](ns-fltkernel-_flt_callback_data.md)

[**FLT_CALLBACK_DATA_QUEUE**](ns-fltkernel-_flt_callback_data_queue.md)

[**FLT_IS_IRP_OPERATION**](/previous-versions/ff544654(v=vs.85))

[**FltCbdqDisable**](nf-fltkernel-fltcbdqdisable.md)

[**FltCbdqEnable**](nf-fltkernel-fltcbdqenable.md)

[**FltCbdqInitialize**](nf-fltkernel-fltcbdqinitialize.md)

[**FltCbdqRemoveIo**](nf-fltkernel-fltcbdqremoveio.md)

[**FltCbdqRemoveNextIo**](nf-fltkernel-fltcbdqremovenextio.md)
