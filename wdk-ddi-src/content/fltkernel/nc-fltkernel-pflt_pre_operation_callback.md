---
UID: NC:fltkernel.PFLT_PRE_OPERATION_CALLBACK
title: PFLT_PRE_OPERATION_CALLBACK (fltkernel.h)
description: A minifilter driver's PFLT_PRE_OPERATION_CALLBACK routine performs pre-operation processing for I/O operations.
old-location: ifsk\pflt_pre_operation_callback.htm
tech.root: ifsk
ms.date: 11/23/2021
keywords: ["PFLT_PRE_OPERATION_CALLBACK callback"]
ms.keywords: FltCallbacks_cfde61cc-2054-4263-8697-aa50a1c9d267.xml, PFLT_PRE_OPERATION_CALLBACK, PFLT_PRE_OPERATION_CALLBACK function pointer [Installable File System Drivers], fltkernel/PFLT_PRE_OPERATION_CALLBACK, ifsk.pflt_pre_operation_callback
req.header: fltkernel.h
req.include-header: FltKernel.h
req.target-type: Desktop
req.target-min-winverclnt: Microsoft Windows 2000 Update Rollup 1 for SP4, Windows XP SP2, Windows Server 2003 SP1, and later Windows operating systems.
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
req.irql: See Remarks section
targetos: Windows
req.typenames: EXpsFontRestriction
f1_keywords:
 - PFLT_PRE_OPERATION_CALLBACK
 - fltkernel/PFLT_PRE_OPERATION_CALLBACK
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - fltkernel.h
api_name:
 - PFLT_PRE_OPERATION_CALLBACK
---

# PFLT_PRE_OPERATION_CALLBACK callback

## -description

A minifilter driver's **PFLT_PRE_OPERATION_CALLBACK** routine performs pre-operation processing for I/O operations.

## -parameters

### -param Data [in, out]

A pointer to the callback data ([**FLT_CALLBACK_DATA**](ns-fltkernel-_flt_callback_data.md)) structure for the I/O operation.

### -param FltObjects [in]

A pointer to an [**FLT_RELATED_OBJECTS**](ns-fltkernel-_flt_related_objects.md) structure that contains opaque pointers for the objects related to the current I/O request.

### -param CompletionContext [out]

If this callback routine returns FLT_PREOP_SUCCESS_WITH_CALLBACK or FLT_PREOP_SYNCHRONIZE, this parameter is an optional context pointer to be passed to the corresponding post-operation callback routine. Otherwise, it must be NULL.

## -returns

This callback routine returns one of the following FLT_PREOP_CALLBACK_STATUS values:

| Return code | Description |
| ----------- | ----------- |
| FLT_PREOP_COMPLETE | The minifilter driver is completing the I/O operation. The filter manager does not send the I/O operation to any minifilter drivers below the caller in the driver stack or to the file system. In this case, the filter manager only calls the post-operation callback routines of the minifilter drivers above the caller in the driver stack. |
| FLT_PREOP_DISALLOW_FASTIO | The operation is a fast I/O operation, and the minifilter driver is not allowing the fast I/O path to be used for this operation. The filter manager does not send the fast I/O operation to any minifilter drivers below the caller in the driver stack or to the file system. In this case, the filter manager only calls the post-operation callback routines of the minifilter drivers above the caller in the driver stack. |
| FLT_PREOP_PENDING | The minifilter driver has pended the I/O operation, and the operation is still pending. The filter manager does not process the I/O operation further until the minifilter driver calls [**FltCompletePendedPreOperation**](nf-fltkernel-fltcompletependedpreoperation.md). |
| FLT_PREOP_SUCCESS_NO_CALLBACK | The minifilter driver is returning the I/O operation to the filter manager for further processing. In this case, the filter manager does not call the minifilter driver's post-operation callback, if one exists, during I/O completion. |
| FLT_PREOP_SUCCESS_WITH_CALLBACK | The minifilter driver is returning the I/O operation to the filter manager for further processing. In this case, the filter manager calls the minifilter driver's post-operation callback during I/O completion. |
| FLT_PREOP_SYNCHRONIZE | The minifilter driver is returning the I/O operation to the filter manager for further processing, but it is not completing the operation. In this case, the filter manager calls the minifilter's post-operation callback in the context of the current thread at IRQL <= APC_LEVEL. |
| FLT_PREOP_DISALLOW_FSFILTER_IO | The minifilter driver is disallowing a fast QueryOpen operation and forcing the operation down the slow path. Doing so causes the I/O manager to service the request by performing an open/query/close of the file. Minifilter drivers should only return this status for QueryOpen. |

## -remarks

A minifilter driver's pre-operation callback routine processes one or more types of I/O operations. This callback routine is similar to a dispatch routine in the legacy filter model.

A minifilter driver registers a pre-operation callback routine for a particular type of I/O operation by storing the callback routine's entry point in the **OperationRegistration** array of the [**FLT_REGISTRATION**](ns-fltkernel-_flt_registration.md) structure. The minifilter driver passes this structure as a parameter to [**FltRegisterFilter**](nf-fltkernel-fltregisterfilter.md) in its [**DriverEntry**](/windows-hardware/drivers/ifs/writing-a-driverentry-routine-for-a-minifilter-driver) routine. A minifilter driver can register a pre-operation callback routine for a given type of I/O operation without registering a post-operation callback ([**PFLT_POST_OPERATION_CALLBACK**](nc-fltkernel-pflt_post_operation_callback.md)) routine and vice versa.

If this routine returns FLT_PREOP_COMPLETE, it must set the callback data structure's **IoStatus.Status** field to the final NTSTATUS value for the I/O operation. This NTSTATUS value cannot be STATUS_PENDING. For a cleanup or close operation, it must be a success NTSTATUS value other than STATUS_PENDING because cleanup and close operations cannot fail.

If this routine returns FLT_PREOP_DISALLOW_FASTIO, it should not set the callback data structure's **IoStatus.Status** field because the filter manager automatically sets this field to STATUS_FLT_DISALLOW_FAST_IO.

FLT_PREOP_DISALLOW_FASTIO can only be returned for a fast I/O operation. To determine whether a given callback data structure represents a fast I/O operation, use the [**FLT_IS_FASTIO_OPERATION**](nf-fltkernel-flt_is_fastio_operation.md) macro.

FLT_PREOP_PENDING can only be returned for IRP-based I/O operations because only IRP-based I/O operations can be pended. To determine whether a given callback data structure represents an IRP-based I/O operation, use the [**FLT_IS_IRP_OPERATION**](/previous-versions/ff544654(v=vs.85)) macro.

If a minifilter driver's pre-operation callback routine returns FLT_PREOP_SYNCHRONIZE, the minifilter driver must have registered a corresponding post-operation callback for the operation.

FLT_PREOP_SYNCHRONIZE should only be returned for IRP-based I/O operations. If it is returned for an I/O operation that is not an IRP-based operation, the filter manager treats this return value as if it were FLT_PREOP_SUCCESS_WITH_CALLBACK.

Minifilter drivers should not return FLT_PREOP_SYNCHRONIZE for create operations, because these operations are already synchronized by the filter manager.

Minifilter drivers must never return FLT_PREOP_SYNCHRONIZE for asynchronous read and write operations. Doing so can severely degrade both minifilter driver and system performance.

A minifilter driver's pre-operation or post-operation callback routine can modify the contents of the callback data structure for the operation. If it does, it must then call [**FltSetCallbackDataDirty**](nf-fltkernel-fltsetcallbackdatadirty.md), unless it has changed the contents of the callback data structure's **IoStatus** field.

The IRQL for this generic callback routine depends on its specific IO paths.

File systems round write and read operations at end of file up to a multiple of the sector size of the underlying file storage device. When processing pre-read or pre-write operations, filters that allocate and swap buffers need to round the size of an allocated buffer up to a multiple of the sector size of the associated device. If they do not, the length of data transferred from the underlying file system will exceed the allocated length of the buffer. For more information about swapping buffers, see the [SwapBuffers Minifilter Sample](/samples/microsoft/windows-driver-samples/swapbuffer-file-system-minifilter-driver/).

Starting with Windows 8, **CompletionContext** uses the [**_Flt_CompletionContext_Outptr_**](/windows-hardware/drivers/devtest/-flt-completioncontext-outptr--annotation) annotation which defines valid context values based on the operation result. The following is a usage example for the callback with the annotation for **CompletionContext**.

```cpp
FLT_PREOP_CALLBACK_STATUS
SwapPreReadBuffers(
    _Inout_ PFLT_CALLBACK_DATA Data,
    _In_ PCFLT_RELATED_OBJECTS FltObjects,
    _Flt_CompletionContext_Outptr_ PVOID *CompletionContext
    );


```

## -see-also

[**FLT_CALLBACK_DATA**](ns-fltkernel-_flt_callback_data.md)

[**FLT_IO_PARAMETER_BLOCK**](ns-fltkernel-_flt_io_parameter_block.md)

[**FLT_IS_FASTIO_OPERATION**](nf-fltkernel-flt_is_fastio_operation.md)

[**FLT_IS_IRP_OPERATION**](/previous-versions/ff544654(v=vs.85))

[**FLT_IS_REISSUED_IO**](/previous-versions/ff544660(v=vs.85))

[**FLT_IS_SYSTEM_BUFFER**](/previous-versions/ff544663(v=vs.85))

[**FLT_REGISTRATION**](ns-fltkernel-_flt_registration.md)

[**FLT_RELATED_OBJECTS**](ns-fltkernel-_flt_related_objects.md)

[**FltCompletePendedPostOperation**](nf-fltkernel-fltcompletependedpostoperation.md)

[**FltCompletePendedPreOperation**](nf-fltkernel-fltcompletependedpreoperation.md)

[**FltQueueDeferredIoWorkItem**](nf-fltkernel-fltqueuedeferredioworkitem.md)

[**FltRegisterFilter**](nf-fltkernel-fltregisterfilter.md)

[**FltSetCallbackDataDirty**](nf-fltkernel-fltsetcallbackdatadirty.md)

[**PFLT_POST_OPERATION_CALLBACK**](nc-fltkernel-pflt_post_operation_callback.md)

[**_Flt_CompletionContext_Outptr_**](/windows-hardware/drivers/devtest/-flt-completioncontext-outptr--annotation)
