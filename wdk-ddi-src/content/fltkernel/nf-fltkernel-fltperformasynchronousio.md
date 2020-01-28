---
UID: NF:fltkernel.FltPerformAsynchronousIo
title: FltPerformAsynchronousIo function (fltkernel.h)
description: A minifilter driver calls FltPerformAsynchronousIo to initiate an asynchronous I/O operation.
old-location: ifsk\fltperformasynchronousio.htm
tech.root: ifsk
ms.assetid: c76529fe-c808-4239-9bde-68dc68d987ec
ms.date: 11/06/2019
ms.keywords: FltApiRef_p_to_z_ed6cd087-6139-4280-aaf3-fe6f0d5b056a.xml, FltPerformAsynchronousIo, FltPerformAsynchronousIo function [Installable File System Drivers], fltkernel/FltPerformAsynchronousIo, ifsk.fltperformasynchronousio
f1_keywords:
 - "fltkernel/FltPerformAsynchronousIo"
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
req.irql: See Remarks section.
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- fltmgr.sys
api_name:
- FltPerformAsynchronousIo
product:
- Windows
targetos: Windows
req.typenames: 
---

# FltPerformAsynchronousIo function

## -description

A minifilter driver calls **FltPerformAsynchronousIo** to initiate an asynchronous I/O operation.

## -parameters

### -param CallbackData [in, out]

Pointer to a callback data ([FLT_CALLBACK_DATA](https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_callback_data)) structure allocated by a previous call to [FltAllocateCallbackData](https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltallocatecallbackdata). This parameter is required and cannot be **NULL**. The caller is responsible for freeing this structure when it is no longer needed by calling [FltFreeCallbackData](https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltfreecallbackdata).

### -param CallbackRoutine [in]

Pointer to a [PFLT_COMPLETED_ASYNC_IO_CALLBACK](https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nc-fltkernel-pflt_completed_async_io_callback)-typed callback routine to be called when the I/O operation is completed. Note: The Filter Manager calls this routine after it calls the postoperation callback ([PFLT_POST_OPERATION_CALLBACK](https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nc-fltkernel-pflt_post_operation_callback)) routines of any minifilter drivers whose instances are attached below the initiating instance (specified in the *Instance* parameter to [FltAllocateCallbackData](https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltallocatecallbackdata)). This parameter is required and cannot be **NULL**. The Filter Manager always calls this routine, even when **FltPerformAsynchronousIo** fails.

### -param CallbackContext [in]

Context pointer to be passed to the *CallbackRoutine* This parameter is optional and can be **NULL**.

## -returns

**FltPerformAsynchronousIo** returns STATUS_SUCCESS to indicate that the I/O operation was completed by the file system, and the callback routine that *CallbackRoutine* points to has been called. Otherwise, it returns an appropriate NTSTATUS value such as one of the following:

| Return code | Description |
| ----------- | ----------- |
| STATUS_FLT_INVALID_ASYNCHRONOUS_REQUEST | IRP_MJ_CREATE requests cannot be performed asynchronously. This is an error code. |
| STATUS_PENDING | The operation returned STATUS_PENDING. Filter Manager will call the callback routine that *CallbackRoutine* points to when the I/O operation is complete. This code indicates only that the operation was initiated. |
| STATUS_FLT_IO_COMPLETE | The operation was completed by the preoperation callback routine of the minifilter driver whose instances are attached below the initiating instance. |

## -remarks

A minifilter driver calls **FltPerformAsynchronousIo** to initiate an asynchronous I/O operation after calling [FltAllocateCallbackData](https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltallocatecallbackdata) to allocate a callback data structure for the operation.

**FltPerformAsynchronousIo** sends the I/O operation only to the minifilter driver instances attached below the initiating instance (specified in the *Instance* parameter to [FltAllocateCallbackData](https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltallocatecallbackdata)), and the file system. Minifilter drivers attached above the specified instance do not receive the I/O operation.

Minifilter drivers can only initiate IRP-based I/O operations. They cannot initiate fast I/O or file system filter (FSFilter) callback operations.

Minifilter drivers should use **FltPerformAsynchronousIo** only for asynchronous I/O operations for which routines such as the following cannot be used:

- [FltReadFile](https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltreadfile)

- [FltWriteFile](https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltwritefile)

IRP_MJ_CREATE requests cannot be performed asynchronously.

The callback data ([FLT_CALLBACK_DATA](https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_callback_data)) structure can be freed or reused at any time after the callback routine that *CallbackRoutine* points to has been called. The caller can free the callback data structure by calling [FltFreeCallbackData](https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltfreecallbackdata) or prepare it for reuse by calling [FltReuseCallbackData](https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltreusecallbackdata).

> [!NOTE]
> STATUS_SUCCESS and STATUS_FLT_IO_COMPLETE indicate that the I/O operation was completed, but do not indicate the final status of the I/O operation. To determine the actual operation status returned by the underlying minifilter drivers, filter drivers, and file system, the *CallbackRoutine* should examine the **IoStatus** member of the callback data structure received in the *CallbackRoutine*'s *CallbackContext* parameter.
>
> Because Filter Manager always calls the callback routine that *CallbackRoutine* points to, even when **FltPerformAsynchronousIo** fails, the minifilter driver can perform the freeing or reusing operations directly in the callback routine.

The caller of **FltPerformAsynchronousIo** can be running at IRQL <= APC_LEVEL if the IRP_PAGING_IO flag is set in the **IrpFlags** member of the [FLT_IO_PARAMETER_BLOCK](https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_io_parameter_block) structure for the operation. (This flag is only valid for IRP_MJ_READ, IRP_MJ_WRITE, IRP_MJ_QUERY_INFORMATION, and IRP_MJ_SET_INFORMATION operations.) Otherwise, the caller must be running at IRQL PASSIVE_LEVEL.

## -see-also

[FLT_CALLBACK_DATA](https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_callback_data)

[FLT_IO_PARAMETER_BLOCK](https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_io_parameter_block)

[FltAllocateCallbackData](https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltallocatecallbackdata)

[FltFreeCallbackData](https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltfreecallbackdata)

[FltPerformSynchronousIo](https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltperformsynchronousio)

[FltReuseCallbackData](https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltreusecallbackdata)

[IRP_MJ_CREATE](https://docs.microsoft.com/windows-hardware/drivers/ifs/irp-mj-create)

[PFLT_COMPLETED_ASYNC_IO_CALLBACK](https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nc-fltkernel-pflt_completed_async_io_callback)

[PFLT_POST_OPERATION_CALLBACK](https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nc-fltkernel-pflt_post_operation_callback)
