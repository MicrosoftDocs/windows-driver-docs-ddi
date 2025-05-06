---
UID: NF:fltkernel.FltCheckOplock
title: FltCheckOplock function (fltkernel.h)
description: A minifilter driver calls FltCheckOplock to synchronize the callback data structure for an IRP-based file I/O operation with the file's current opportunistic lock (oplock) state.
tech.root: ifsk
ms.date: 02/07/2025
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
req.irql: <= APC_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - FltCheckOplock
 - fltkernel/FltCheckOplock
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - fltkernel.h
api_name:
 - FltCheckOplock
---

# FltCheckOplock function

## -description

A minifilter driver calls **FltCheckOplock** to synchronize the callback data structure for an IRP-based file I/O operation with the file's current opportunistic lock (oplock) state.

## -parameters

### -param Oplock [in]

An opaque oplock pointer for the file. This pointer must have been initialized by a previous call to [**FltInitializeOplock**](nf-fltkernel-fltinitializeoplock.md).

### -param CallbackData [in]

A pointer to the callback data ([**FLT_CALLBACK_DATA**](/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_callback_data)) structure for the I/O operation.

### -param Context [in, optional]

A pointer to caller-defined context information to be passed to the callback routines that  **WaitCompletionRoutine** and **PrePostCallbackDataRoutine** point to. The Filter Manager treats this information as opaque.

### -param WaitCompletionRoutine [in, optional]

A pointer to a caller-supplied callback routine. If an oplock break is in progress, the Filter Manager calls this routine when the oplock break is completed. This parameter is optional and can be NULL. If it is NULL, the caller is put into a wait state until the oplock break is completed.

This routine is declared as follows:

``` cpp
typedef VOID
(*PFLTOPLOCK_WAIT_COMPLETE_ROUTINE) (
      IN PFLT_CALLBACK_DATA CallbackData,
      IN PVOID Context
      );
```

where:

* **CallbackData** is a pointer to a [**FLT_CALLBACK_DATA**](ns-fltkernel-_flt_callback_data) structure for the I/O operation.

* **Context** is a context information pointer that was passed in the **Context** parameter to **FltCheckOplock**.

### -param PrePostCallbackDataRoutine [in, optional]

A pointer to a caller-supplied callback routine to be called if the I/O operation is posted to a work queue. This parameter is optional and can be NULL.

This routine is declared as follows:

``` cpp
typedef VOID
(*PFLTOPLOCK_PREPOST_CALLBACKDATA_ROUTINE) (
      IN PFLT_CALLBACK_DATA CallbackData,
      IN PVOID Context
      );
```
where:

* **CallbackData** is a pointer to a [**FLT_CALLBACK_DATA**](ns-fltkernel-_flt_callback_data) structure for the I/O operation.

* **Context** is a context information pointer that was passed in the **Context** parameter to **FltCheckOplock**.

## -returns

**FltCheckOplock** returns one of the following FLT_PREOP_CALLBACK_STATUS codes:

| Return code | Description |
|-------------|-------------|
| **FLT_PREOP_COMPLETE** | **FltCheckOplock** encountered a pool allocation failure, or a call to the [**FsRtlCheckOplock**](/windows/win32/api/rrascfg/nf-rrascfg-ieapproviderconfig-initialize) function returned an error. **FltCheckOplock** will set the error code in the **Status** member of the [**IO_STATUS_BLOCK**](/windows-hardware/drivers/ddi/wdm/ns-wdm-_io_status_block) structure of the **IoStatus** member of the [**FLT_CALLBACK_DATA**](ns-fltkernel-_flt_callback_data) callback data structure. The **CallbackData** parameter points to this **FLT_CALLBACK_DATA**. |
| **FLT_PREOP_PENDING** | An oplock break was initiated, which caused the Filter Manager to post the I/O operation to a work queue. The I/O operation is represented by the callback data that the **CallbackData** parameter points to. |
| **FLT_PREOP_SUCCESS_NO_CALLBACK** | The I/O operation was performed immediately. Be aware that if this operation was a create operation that specified FILE_COMPLETE_IF_OPLOCKED in the create-options parameter, there might actually be an oplock break in progress even though the operation was performed immediately. To determine whether this is the situation, the caller should check the status in the **Status** member of the [**IO_STATUS_BLOCK**](/windows-hardware/drivers/ddi/wdm/ns-wdm-_io_status_block) structure of the **IoStatus** member of the [**FLT_CALLBACK_DATA**](ns-fltkernel-_flt_callback_data) callback data structure. |

## -remarks

A minifilter driver calls **FltCheckOplock** to synchronize an IRP-based I/O operation with the current oplock state of a file according to the following conditions:

* If the I/O operation will cause the oplock to break, the oplock break is initiated.

* If the I/O operation can't continue until the oplock break is complete, **FltCheckOplock** returns FLT_PREOP_PENDING and calls the callback routine that the **PrePostCallbackDataRoutine** parameter points to.

If a minifilter driver uses oplocks, it must call **FltCheckOplock** from any preoperation callback ([**PFLT_PRE_OPERATION_CALLBACK**](nc-fltkernel-pflt_pre_operation_callback.md)) routines for I/O operations that can cause oplock breaks. This rule applies to the following types of I/O operations, because these operations can cause oplock breaks:

* IRP_MJ_CLEANUP
* IRP_MJ_CREATE
* IRP_MJ_FILE_SYSTEM_CONTROL
* IRP_MJ_FLUSH_BUFFERS
* IRP_MJ_LOCK_CONTROL
* IRP_MJ_READ
* IRP_MJ_SET_INFORMATION
* IRP_MJ_WRITE
* IRP_MJ_ACQUIRE_FOR_SECTION_SYNCHRONIZATION

The I/O operation must be an IRP-based I/O operation. To determine whether a given callback data structure represents an IRP-based I/O operation, use the [**FLT_IS_IRP_OPERATION**](/previous-versions/ff544654(v=vs.85)) macro.

Minifilters must not call **FltCheckOplock** again within the callback specified in **WaitCompletionRoutine**. Doing so can result in a deadlock condition if the oplock package calls the completion callback before **FltCheckOplock** returns.

For detailed information about opportunistic locks, see the Microsoft Windows SDK documentation.

## -see-also

[**FLT_CALLBACK_DATA**](ns-fltkernel-_flt_callback_data.md)

[**FLT_IS_IRP_OPERATION**](/previous-versions/ff544654(v=vs.85))

[**FSCTL_OPBATCH_ACK_CLOSE_PENDING**](/windows-hardware/drivers/ifs/fsctl-opbatch-ack-close-pending)

[**FSCTL_OPLOCK_BREAK_ACKNOWLEDGE**](/windows-hardware/drivers/ifs/fsctl-oplock-break-acknowledge)

[**FSCTL_OPLOCK_BREAK_ACK_NO_2**](/windows-hardware/drivers/ifs/fsctl-oplock-break-ack-no-2)

[**FSCTL_OPLOCK_BREAK_NOTIFY**](/windows-hardware/drivers/ifs/fsctl-oplock-break-notify)

[**FSCTL_REQUEST_BATCH_OPLOCK**](/windows-hardware/drivers/ifs/fsctl-request-batch-oplock)

[**FSCTL_REQUEST_FILTER_OPLOCK**](/windows-hardware/drivers/ifs/fsctl-request-filter-oplock)

[**FSCTL_REQUEST_OPLOCK_LEVEL_1**](/windows-hardware/drivers/ifs/fsctl-request-oplock-level-1)

[**FSCTL_REQUEST_OPLOCK_LEVEL_2**](/windows-hardware/drivers/ifs/fsctl-request-oplock-level-2)

[**FltCheckOplockEx**](nf-fltkernel-fltcheckoplockex.md)

[**FltCurrentBatchOplock**](nf-fltkernel-fltcurrentbatchoplock.md)

[**FltInitializeOplock**](nf-fltkernel-fltinitializeoplock.md)

[**FltOplockFsctrl**](nf-fltkernel-fltoplockfsctrl.md)

[**FltOplockIsFastIoPossible**](nf-fltkernel-fltoplockisfastiopossible.md)

[**FltUninitializeOplock**](nf-fltkernel-fltuninitializeoplock.md)

[**FsRtlCheckOplock**](/windows/win32/api/rrascfg/nf-rrascfg-ieapproviderconfig-initialize)

[**PFLT_PRE_OPERATION_CALLBACK**](nc-fltkernel-pflt_pre_operation_callback.md)
