---
UID: NF:fltkernel.FltIsOperationSynchronous
title: FltIsOperationSynchronous function (fltkernel.h)
description: The FltIsOperationSynchronous routine determines whether a given callback data structure (FLT_CALLBACK_DATA) represents a synchronous or asynchronous I/O operation.
old-location: ifsk\fltisoperationsynchronous.htm
tech.root: ifsk
ms.date: 11/29/2021
keywords: ["FltIsOperationSynchronous function"]
ms.keywords: FltApiRef_e_to_o_f80a8dfd-53b1-42cf-9d7c-18fc4af6ff4e.xml, FltIsOperationSynchronous, FltIsOperationSynchronous routine [Installable File System Drivers], fltkernel/FltIsOperationSynchronous, ifsk.fltisoperationsynchronous
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
req.lib: FltMgr.lib
req.dll: Fltmgr.sys
req.irql: Any level
targetos: Windows
req.typenames: 
f1_keywords:
 - FltIsOperationSynchronous
 - fltkernel/FltIsOperationSynchronous
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - fltmgr.sys
api_name:
 - FltIsOperationSynchronous
---

# FltIsOperationSynchronous function

## -description

The **FltIsOperationSynchronous** routine determines whether a given callback data structure ([**FLT_CALLBACK_DATA**](ns-fltkernel-_flt_callback_data.md)) represents a synchronous or asynchronous I/O operation.

## -parameters

### -param CallbackData [in]

Pointer to the callback data structure for the operation ([**FLT_CALLBACK_DATA**](ns-fltkernel-_flt_callback_data.md)).

## -returns

**FltIsOperationSynchronous** returns TRUE if the operation is synchronous, and FALSE if the operation is asynchronous.

## -remarks

**FltIsOperationSynchronous** determines whether a given callback data structure ([**FLT_CALLBACK_DATA**](ns-fltkernel-_flt_callback_data.md)) represents a synchronous or asynchronous I/O operation, according to the following conditions:

* If the operation is not an IRP-based I/O operation, the operation is synchronous. To determine whether an operation is IRP-based, use the [**FLT_IS_IRP_OPERATION**](/previous-versions/ff544654(v=vs.85)) macro.

* If the operation is an asynchronous paging I/O operation, the operation is asynchronous, even if one of the other conditions in this list is true.

* If the operation is a synchronous paging I/O operation, the operation is synchronous.

* If the file object for the operation was opened for synchronous I/O, the operation is synchronous.

* If the IRP_SYNCHRONOUS_API flag is set in the IRP for the operation, the operation is synchronous. This flag is set for operations, such as IRP_MJ_QUERY_INFORMATION and IRP_MJ_SET_INFORMATION, that are always synchronous, even when performed on a file object that was opened for asynchronous I/O.

* If none of the above conditions is true, the operation is asynchronous.

> [!NOTE]
>
> **FltIsOperationSynchronous**  also returns TRUE if the callback data structure represents an IRP_MJ_DEVICE_CONTROL, IRP_MJ_INTERNAL_DEVICE_CONTROL, or IRP_MJ_FILE_SYSTEM_CONTROL operation with an I/O control code (IOCTL) or file system control code (FSCTL) that was defined with METHOD_BUFFERED, even if the file object was opened for asynchronous I/O. Such a request is likely to be made synchronous by the file system, but this is not necessarily true in all cases.
>
> When **FltIsOperationSynchronous** returns TRUE, this does not indicate that the I/O operation is synchronized. That is, the TRUE value does not indicate that a minifilter driver returned FLT_PREOP_SYNCHRONIZE in the preoperation callback ([**PFLT_POST_OPERATION_CALLBACK**](nc-fltkernel-pflt_post_operation_callback.md)) routine for this operation. Instead, **FltIsOperationSynchronous** returns TRUE to indicate that the I/O operation is synchronous from the I/O manager's perspective.

**FltIsOperationSynchronous** can be called for all classes of operations: fast I/O, file system filter (FSFilter) callbacks, and IRP-based operations.

## -see-also

[**FLT_CALLBACK_DATA**](ns-fltkernel-_flt_callback_data.md)

[**FLT_IS_FASTIO_OPERATION**](nf-fltkernel-flt_is_fastio_operation.md)

[**FLT_IS_FS_FILTER_OPERATION**](/previous-versions/ff544648(v=vs.85))

[**FLT_IS_IRP_OPERATION**](/previous-versions/ff544654(v=vs.85))

[**IoIsOperationSynchronous**](../ntifs/nf-ntifs-ioisoperationsynchronous.md)
