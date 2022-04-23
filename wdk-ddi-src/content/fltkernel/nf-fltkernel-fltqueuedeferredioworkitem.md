---
UID: NF:fltkernel.FltQueueDeferredIoWorkItem
title: FltQueueDeferredIoWorkItem function (fltkernel.h)
description: The FltQueueDeferredIoWorkItem routine posts an IRP-based I/O operation to a work queue.
old-location: ifsk\fltqueuedeferredioworkitem.htm
tech.root: ifsk
ms.date: 04/18/2022
keywords: ["FltQueueDeferredIoWorkItem function"]
ms.keywords: FltApiRef_p_to_z_df42429d-485c-4c28-a9e7-b334d7ad52d7.xml, FltQueueDeferredIoWorkItem, FltQueueDeferredIoWorkItem routine [Installable File System Drivers], fltkernel/FltQueueDeferredIoWorkItem, ifsk.fltqueuedeferredioworkitem
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: Windows 2000
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
req.lib: Fltmgr.lib
req.dll: Fltmgr.sys
req.irql: <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - FltQueueDeferredIoWorkItem
 - fltkernel/FltQueueDeferredIoWorkItem
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - fltmgr.sys
api_name:
 - FltQueueDeferredIoWorkItem
---

# FltQueueDeferredIoWorkItem function

## -description

The **FltQueueDeferredIoWorkItem** routine posts an IRP-based I/O operation to a work queue.

## -parameters

### -param FltWorkItem [in]

A pointer to the work item to add to the work queue. The work item must have been allocated by calling [**FltAllocateDeferredIoWorkItem**](nf-fltkernel-fltallocatedeferredioworkitem.md).

### -param Data [in]

A pointer to the [**FLT_CALLBACK_DATA**](ns-fltkernel-_flt_callback_data.md) structure for the I/O operation. The operation must be an IRP-based I/O operation. To determine whether a given callback data structure represents an IRP-based I/O operation, use the [**FLT_IS_IRP_OPERATION**](/previous-versions/ff544654(v=vs.85)) macro.

### -param WorkerRoutine [in]

A pointer to a caller-supplied worker callback routine. This routine is declared as follows:

``` C
typedef VOID
(*PFLT_DEFERRED_IO_WORKITEM_ROUTINE) (
    _In_ PFLT_DEFERRED_IO_WORKITEM FltWorkItem,
    _In_ PFLT_CALLBACK_DATA CallbackData,
    _In_opt_ PVOID Context
    );
```

where:

* **FltWorkItem** is an opaque pointer to a deferred work item structure.
* **CallbackData** is a pointer to the callback data structure for the I/O operation.
* **Context** is an optional context information pointer that was passed as the **Context** parameter of **FltQueueDeferredIoWorkItem**.

### -param QueueType [in]

Specifies the queue into which the work item that **FltWorkItem** points to is to be inserted. **QueueType** can be one of the following values.

| Value | Meaning |
| ----- | ------- |
| **CriticalWorkQueue** | Insert the work item into the queue from which a system thread with a real-time priority attribute processes the work item. |
| **DelayedWorkQueue**  | Insert the work item into the queue from which a system thread with a variable priority attribute processes the work item. |

The **QueueType** value **HyperCriticalWorkQueue** is reserved for system use.

### -param Context [in]

A pointer to caller-defined context information to be passed as the **Context** parameter of the callback routine specified in the **WorkerRoutine** parameter.

## -returns

The **FltQueueDeferredIoWorkItem** routine returns STATUS_SUCCESS or an appropriate NTSTATUS value such as one of the following:

| Return code | Description |
| ----------- | ----------- |
| STATUS_FLT_DELETING_OBJECT | The target instance for the I/O operation (**Data->Iopb->TargetInstance**) is being torn down. This is an error code. |
| STATUS_FLT_NOT_SAFE_TO_POST_OPERATION | The I/O operation cannot be posted safely to a worker thread. See Remarks for possible reasons why this error code is returned. |

## -remarks

The **FltQueueDeferredIoWorkItem** routine posts an I/O operation to a system work queue. The specified **WorkerRoutine** callback routine is called in the context of a system thread, at IRQL PASSIVE_LEVEL.

The operation must be an IRP-based I/O operation. To determine whether a given callback data structure represents an IRP-based I/O operation, use the [**FLT_IS_IRP_OPERATION**](/previous-versions/ff544654(v=vs.85)) macro.

**FltQueueDeferredIoWorkItem** returns STATUS_FLT_NOT_SAFE_TO_POST_OPERATION when the I/O operation cannot be posted safely to a worker thread. Possible reasons include the following:

* **FltQueueDeferredIoWorkItem** cannot post a paging I/O operation to a worker thread.

* **FltQueueDeferredIoWorkItem** cannot post an I/O operation to a worker thread if the **TopLevelIrp** field of the current thread is not **NULL**, because the resulting file system recursion could cause deadlocks or stack overflows. For more information, see [**IoGetTopLevelIrp**](../ntifs/nf-ntifs-iogettoplevelirp.md).

A minifilter driver can use **FltQueueDeferredIoWorkItem** in a preoperation callback ([**PFLT_PRE_OPERATION_CALLBACK**](nc-fltkernel-pflt_pre_operation_callback.md)) routine as follows:

1. The preoperation callback calls [**FltAllocateDeferredIoWorkItem**](nf-fltkernel-fltallocatedeferredioworkitem.md) to allocate the work item.

2. The preoperation callback calls **FltQueueDeferredIoWorkItem** to post the operation to the work queue.

3. The preoperation callback returns FLT_PREOP_PENDING.

4. After processing the I/O operation, the work routine calls [**FltCompletePendedPreOperation**](nf-fltkernel-fltcompletependedpreoperation.md) to return the I/O operation to the Filter Manager.

5. The work routine calls [**FltFreeDeferredIoWorkItem**](nf-fltkernel-fltfreedeferredioworkitem.md) to free the work item.

A minifilter driver can use **FltQueueDeferredIoWorkItem** in a post-operation callback ([**PFLT_POST_OPERATION_CALLBACK**](nc-fltkernel-pflt_post_operation_callback.md)) routine as follows:

1. The post-operation callback calls [**FltAllocateDeferredIoWorkItem**](nf-fltkernel-fltallocatedeferredioworkitem.md) to allocate the work item.

2. The post-operation callback calls **FltQueueDeferredIoWorkItem** to post the operation to the work queue.

3. The post-operation callback returns FLT_POSTOP_MORE_PROCESSING_REQUIRED.

4. After processing the I/O operation, the work routine calls [**FltCompletePendedPostOperation**](nf-fltkernel-fltcompletependedpostoperation.md) to return the I/O operation to the Filter Manager.

The work routine calls [**FltFreeDeferredIoWorkItem**](nf-fltkernel-fltfreedeferredioworkitem.md) to free the work item.

## -see-also

[**FLT_CALLBACK_DATA**](ns-fltkernel-_flt_callback_data.md)

[**FLT_IS_IRP_OPERATION**](/previous-versions/ff544654(v=vs.85))

[**FltAllocateDeferredIoWorkItem**](nf-fltkernel-fltallocatedeferredioworkitem.md)

[**FltCompletePendedPostOperation**](nf-fltkernel-fltcompletependedpostoperation.md)

[**FltCompletePendedPreOperation**](nf-fltkernel-fltcompletependedpreoperation.md)

[**FltFreeDeferredIoWorkItem**](nf-fltkernel-fltfreedeferredioworkitem.md)

[**IoGetTopLevelIrp**](../ntifs/nf-ntifs-iogettoplevelirp.md)

[**PFLT_POST_OPERATION_CALLBACK**](nc-fltkernel-pflt_post_operation_callback.md)

[**PFLT_PRE_OPERATION_CALLBACK**](nc-fltkernel-pflt_pre_operation_callback.md)
