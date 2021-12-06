---
UID: NF:fltkernel.FltReissueSynchronousIo
title: FltReissueSynchronousIo function (fltkernel.h)
description: FltReissueSynchronousIo initiates a new synchronous I/O operation that uses the parameters from a previously synchronized I/O operation.
old-location: ifsk\fltreissuesynchronousio.htm
tech.root: ifsk
ms.date: 11/29/2021
keywords: ["FltReissueSynchronousIo function"]
ms.keywords: FltApiRef_p_to_z_c86041cf-780e-4754-b580-6665573bdb88.xml, FltReissueSynchronousIo, FltReissueSynchronousIo function [Installable File System Drivers], fltkernel/FltReissueSynchronousIo, ifsk.fltreissuesynchronousio
req.header: fltkernel.h
req.include-header: FltKernel.h
req.target-type: Universal
req.target-min-winverclnt: Windows 2000 Update Rollup 1 for SP4; Windows XP SP2 
req.target-min-winversvr: Windows Server 2003 SP1
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
req.irql: <= APC_LEVEL (non-paging IO can only be reissued at PASSIVE_LEVEL)
targetos: Windows
req.typenames: 
f1_keywords:
 - FltReissueSynchronousIo
 - fltkernel/FltReissueSynchronousIo
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - fltmgr.sys
api_name:
 - FltReissueSynchronousIo
---

# FltReissueSynchronousIo function

## -description

**FltReissueSynchronousIo** initiates a new synchronous I/O operation that uses the parameters from a previously synchronized I/O operation.

## -parameters

### -param InitiatingInstance [in]

An opaque instance pointer to the minifilter driver instance that is reissuing the I/O operation. Must be the same instance that initiated the previous I/O operation. This parameter is required and cannot be set to NULL.

### -param CallbackData [in]

A pointer to the callback data ([**FLT_CALLBACK_DATA**](ns-fltkernel-_flt_callback_data.md)) structure from a previously synchronized I/O operation. This parameter is required and cannot be set to NULL.

## -returns

None

## -remarks

A minifilter driver calls **FltReissueSynchronousIo** from a postoperation callback ([**PFLT_POST_OPERATION_CALLBACK**](nc-fltkernel-pflt_post_operation_callback.md)) routine to reissue a synchronized I/O request. It typically calls **FltReissueSynchronousIo** from a postoperation callback routine to reissue a failed operation with different parameters, or to handle a reparse bounce. However, it can also call **FltReissueSynchronousIo** to reissue I/O that the minifilter driver generated through calls to the [**FltAllocateCallbackData**](nf-fltkernel-fltallocatecallbackdata.md) and [**FltPerformSynchronousIo**](nf-fltkernel-fltperformsynchronousio.md) routines. In this situation, it does not matter whether it calls **FltReissueSynchronousIo** in a postoperation callback routine or outside the context of an operation callback routine. For calls outside the context of a postoperation callback routine, consider using the [**FltReuseCallbackData**](nf-fltkernel-fltreusecallbackdata.md) and **FltPerformSynchronousIo** routines instead.

The caller can modify the contents of the callback data ([**FLT_CALLBACK_DATA**](ns-fltkernel-_flt_callback_data.md)) structure's I/O parameter block before reissuing the I/O request. If it does, it must call [**FltSetCallbackDataDirty**](nf-fltkernel-fltsetcallbackdatadirty.md) before calling **FltReissueSynchronousIo**.

For example, if a minifilter driver uses reparse points, and its post-create callback routine is called for a create operation that returned STATUS_REPARSE, the minifilter driver can reissue the create operation for its own reparse points. In this case, the minifilter driver will complete the following steps:

1. Set the FILE_OPEN_REPARSE_POINT flag in the callback data structure's I/O parameter block.

2. Call [**FltSetCallbackDataDirty**](nf-fltkernel-fltsetcallbackdatadirty.md).

3. Call **FltReissueSynchronousIo** to reissue the create request.

The Filter Manager sends the reissued I/O request only to the minifilter driver instances that are attached below the initiating instance (specified in the **InitiatingInstance** parameter) and to the file system. Minifilter driver instances attached above the initiating instance do not receive the reissued I/O request.

Only synchronized I/O operations can be reissued. To provide the driver with the ability to reissue, by calling **FltReissueSynchronousIo** in the postoperation callback routine, a minifilter driver must specifically return FLT_PREOP_SYNCHRONIZE in the preoperation callback routine.

> [!NOTE]
> The minifilter driver does not call the [**FltIsOperationSynchronous**](nf-fltkernel-fltisoperationsynchronous.md) routine to determine whether the preoperation callback routine for this operation returned FLT_PREOP_SYNCHRONIZE. The minifilter driver calls **FltIsOperationSynchronous** to determine whether the operation itself is synchronous from the I/O manager's perspective.

Only IRP-based I/O operations can be reissued. Fast I/O operations and file system filter (FSFilter) callback operations cannot be reissued. To determine whether an I/O operation is IRP-based, use the [**FLT_IS_IRP_OPERATION**](/previous-versions/ff544654(v=vs.85)) macro.

A create (IRP_MJ_CREATE) operation that has been canceled cannot be reissued. Before calling **FltReissueSynchronousIo** for a create operation, callers should check the **Flags** member of the file object for the create operation. If the FO_FILE_OPEN_CANCELLED flag is set, this means that the create operation has been canceled, and a close ([**IRP_MJ_CLOSE**](/windows-hardware/drivers/kernel/irp-mj-close)) operation will be issued for this file object. If **FltReissueSynchronousIo** is called for a create operation that has been canceled, the Filter Manager fails the reissued I/O request with STATUS_CANCELLED.

> [!NOTE]
> When minifilter drivers re-issue the create in the post-create callback, they do not have to release and set the buffer that is associated with their reparse point (**TagData** field in **CallbackData**) to NULL. Instead, the Filter Manager releases and sets the buffer to NULL for them.

## -see-also

[**FLT_CALLBACK_DATA**](ns-fltkernel-_flt_callback_data.md)

[**FLT_IS_FASTIO_OPERATION**](nf-fltkernel-flt_is_fastio_operation.md)

[**FLT_IS_FS_FILTER_OPERATION**](/previous-versions/ff544648(v=vs.85))

[**FLT_IS_IRP_OPERATION**](/previous-versions/ff544654(v=vs.85))

[**FLT_IS_REISSUED_IO**](/previous-versions/ff544660(v=vs.85))

[**FLT_PARAMETERS for IRP_MJ_CREATE**](/windows-hardware/drivers/ifs/flt-parameters-for-irp-mj-create)

[**FltCancelFileOpen**](nf-fltkernel-fltcancelfileopen.md)

[**FltIsOperationSynchronous**](nf-fltkernel-fltisoperationsynchronous.md)

[**FltPerformSynchronousIo**](nf-fltkernel-fltperformsynchronousio.md)

[**FltReuseCallbackData**](nf-fltkernel-fltreusecallbackdata.md)

[**FltSetCallbackDataDirty**](nf-fltkernel-fltsetcallbackdatadirty.md)

[**IRP_MJ_CLOSE**](/windows-hardware/drivers/kernel/irp-mj-close)

[**IRP_MJ_CREATE**](/windows-hardware/drivers/ifs/irp-mj-create)

[**PFLT_POST_OPERATION_CALLBACK**](nc-fltkernel-pflt_post_operation_callback.md)

[**PFLT_PRE_OPERATION_CALLBACK**](nc-fltkernel-pflt_pre_operation_callback.md)
