---
UID: NF:fltkernel.FltDoCompletionProcessingWhenSafe
title: FltDoCompletionProcessingWhenSafe function (fltkernel.h)
description: If it is safe to do so, the FltDoCompletionProcessingWhenSafe function executes a minifilter driver postoperation callback routine.
old-location: ifsk\fltdocompletionprocessingwhensafe.htm
tech.root: ifsk
ms.date: 01/06/2020
keywords: ["FltDoCompletionProcessingWhenSafe function"]
ms.keywords: FltApiRef_a_to_d_4e8cd7a1-1469-4ae1-97a9-51a184d0ad5a.xml, FltDoCompletionProcessingWhenSafe, FltDoCompletionProcessingWhenSafe routine [Installable File System Drivers], fltkernel/FltDoCompletionProcessingWhenSafe, ifsk.fltdocompletionprocessingwhensafe
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: Available in Microsoft Windows 2000 Update Rollup 1 for SP4, Windows XP SP2, Windows Server 2003 SP1, and later operating systems. Not available in Windows 2000 SP4 and earlier operating systems.
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
req.dll: 
req.irql: Any.
targetos: Windows
req.typenames: 
f1_keywords:
 - FltDoCompletionProcessingWhenSafe
 - fltkernel/FltDoCompletionProcessingWhenSafe
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Fltmgr.lib
 - Fltmgr.dll
api_name:
 - FltDoCompletionProcessingWhenSafe
---

# FltDoCompletionProcessingWhenSafe function


## -description

If it is safe to do so, the **FltDoCompletionProcessingWhenSafe** function executes a minifilter driver postoperation callback routine.

## -parameters

### -param Data 

[in]
Pointer to the callback data structure ([FLT_CALLBACK_DATA](./ns-fltkernel-_flt_callback_data.md)) for the I/O operation. Usually this is the same as the *Data* pointer that was passed to the postoperation callback routine ([PFLT_POST_OPERATION_CALLBACK](./nc-fltkernel-pflt_post_operation_callback.md)) that called **FltDoCompletionProcessingWhenSafe**.

### -param FltObjects 

[in]
Pointer to the related objects structure ([FLT_RELATED_OBJECTS](./ns-fltkernel-_flt_related_objects.md)) for the I/O operation. Usually this is the same as the *FltObjects* pointer that was passed to the postoperation callback routine that called **FltDoCompletionProcessingWhenSafe**.

### -param CompletionContext 

[in, optional]
Pointer to a caller-supplied context information that will be passed in to the callback function that is specified in the *SafePostCallback* parameter.

### -param Flags 

[in]
Bitmask of flags which specify how completion processing will be performed. Usually this is the same as the *Flags* value that was passed to the postoperation callback routine that called **FltDoCompletionProcessingWhenSafe**. For more information, see the following Remarks section.

### -param SafePostCallback 

[in]
Pointer to a caller-supplied [PFLT_POST_OPERATION_CALLBACK](./nc-fltkernel-pflt_post_operation_callback.md)-typed callback routine that the operating system calls when it is safe to do so.

### -param RetPostOperationStatus 

[out]
Caller-allocated variable that receives the final status value for the I/O operation. For more information on how this parameter is set, see the following Remarks section.

## -returns

**FltDoCompletionProcessingWhenSafe** returns **TRUE** if completion processing for the I/O operation can be performed immediately or the I/O operation was successfully posted to a worker thread; otherwise, it returns **FALSE**.

## -remarks

**FltDoCompletionProcessingWhenSafe** executes the *SafePostCallback* immediately if the caller is running at IRQL <= APC_LEVEL. Otherwise, if it is safe to post the operation to a worker thread, the *SafePostCallback* processing is deferred until it can be called in a thread context where IRQL <= APC_LEVEL.

If IRQL < DISPATCH_LEVEL:

- **FltDoCompletionProcessingWhenSafe** immediately calls the *SafePostCallback* callback routine.
- The *RetPostOperationStatus* parameter receives a FLT_POSTOP_CALLBACK_STATUS value returned by *SafePostCallback*.
- **FltDoCompletionProcessingWhenSafe** returns **TRUE**.

If IRQL >= DISPATCH_LEVEL:

- **FltDoCompletionProcessingWhenSafe** attempts to post the I/O operation to a worker thread, and then call the *SafePostCallback* routine from the worker thread.
- If the I/O operation could be safely posted:
  - Filter manager sets *RetPostOperationStatus* to FLT_POSTOP_MORE_PROCESSING_REQUIRED.
  - **FltDoCompletionProcessingWhenSafe** returns **TRUE**.
- If the I/O operation could not be safely posted:
  - Filter manager sets *RetPostOperationStatus* to FLT_POSTOP_FINISHED_PROCESSING.
  - **FltDoCompletionProcessingWhenSafe** returns **FALSE**.

**FltDoCompletionProcessingWhenSafe** can only be called for IRP-based operations. To determine whether the operation is an IRP-based operation, use the [FLT_IS_IRP_OPERATION](/previous-versions/ff544654(v=vs.85)) macro.

**FltDoCompletionProcessingWhenSafe** cannot be used to post completion of a paging I/O operation to a worker thread.

**FltDoCompletionProcessingWhenSafe** can only be called from a minifilter driver's postoperation callback routine ([PFLT_POST_OPERATION_CALLBACK](./nc-fltkernel-pflt_post_operation_callback.md)). Note that **FltDoCompletionProcessingWhenSafe** should never be called if the *Flags* parameter of the postoperation callback has the FLTFL_POST_OPERATION_DRAINING bit set.

If a minifilter calls **FltDoCompletionProcessingWhenSafe** and the *SafePostCallback* is invoked in a worker thread because it is not safe to invoke it in the current thread context, the filter manager will resume completion processing as long as the minifilter does not return FLT_POSTOP_MORE_PROCESSING_REQUIRED from the *SafePostCallback*.

If the minifilter does return FLT_POSTOP_MORE_PROCESSING_REQUIRED from the *SafePostCallback*, the minifilter must call [**FltCompletePendedPostOperation**](./nf-fltkernel-fltcompletependedpostoperation.md) to resume completion processing.

> [!CAUTION]
> To avoid deadlocks, **FltDoCompletionProcessingWhenSafe** cannot be called for I/O operations that can be directly completed by a driver in the storage stack, such as the following:
>
> - IRP_MJ_READ
> - IRP_MJ_WRITE
> - IRP_MJ_FLUSH_BUFFERS

## -see-also

[FLT_CALLBACK_DATA](./ns-fltkernel-_flt_callback_data.md)

[FLT_IS_IRP_OPERATION](/previous-versions/ff544654(v=vs.85))

[FLT_RELATED_OBJECTS](./ns-fltkernel-_flt_related_objects.md)

[**FltCancelIo**](./nf-fltkernel-fltcancelio.md)

[**FltCompletePendedPostOperation**](./nf-fltkernel-fltcompletependedpostoperation.md)

[PFLT_POST_OPERATION_CALLBACK](./nc-fltkernel-pflt_post_operation_callback.md)
