---
UID: NF:fltkernel.FltProcessFileLock
title: FltProcessFileLock function (fltkernel.h)
description: The FltProcessFileLock routine processes and completes a file lock operation.
old-location: ifsk\fltprocessfilelock.htm
tech.root: ifsk
ms.date: 11/29/2021
keywords: ["FltProcessFileLock function"]
ms.keywords: FltApiRef_p_to_z_e4ff8145-c586-4c3c-acfa-d4c22f48a5d2.xml, FltProcessFileLock, FltProcessFileLock routine [Installable File System Drivers], fltkernel/FltProcessFileLock, ifsk.fltprocessfilelock
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: Windows XP with SP2
req.target-min-winversvr: Windows Server 2003 with SP1
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
req.irql: <= APC_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - FltProcessFileLock
 - fltkernel/FltProcessFileLock
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - fltmgr.sys
api_name:
 - FltProcessFileLock
---

# FltProcessFileLock function

## -description

The **FltProcessFileLock** routine processes and completes a file lock operation.

## -parameters

### -param FileLock [in]

Pointer to the FILE_LOCK structure for the file. This structure must have been initialized by a previous call to [**FltAllocateFileLock**](nf-fltkernel-fltallocatefilelock.md) or [**FltInitializeFileLock**](nf-fltkernel-fltinitializefilelock.md).

### -param CallbackData [in]

Pointer to the callback data ([**FLT_CALLBACK_DATA**](ns-fltkernel-_flt_callback_data.md)) structure for the [**IRP_MJ_LOCK_CONTROL**](/windows-hardware/drivers/ifs/irp-mj-lock-control) operation.

### -param Context [in, optional]

Context pointer to be used when completing the operation. This context pointer is passed to the **CompleteLockCallbackDataRoutine** and **UnlockRoutine** callback routines that the minifilter driver registered in a previous call to [**FltAllocateFileLock**](nf-fltkernel-fltallocatefilelock.md). This parameter is optional and can be NULL.

## -returns

**FltProcessFileLock** returns one of the following.

| Return code | Description |
| ----------- | ----------- |
| FLT_PREOP_COMPLETE  | The Filter Manager is done with the **CallbackData**, which can now be completed. |
| FLT_PREOP_DISALLOW_FASTIO | The **CallbackData** represents a fast I/O operation, and a minifilter driver in the stack has disallowed the fast I/O to be used for this operation. The Filter Manager does not send the operation to any minifilter drivers below the one that disallowed the operation. In this case, the Filter Manager only calls the postoperation callback routines (and **CompleteLockCallbackDataRoutine** callbacks) of the minifilter drivers above the minifilter driver that disallowed the fast I/O operation. |
| FLT_PREOP_PENDING | The lock operation has been pended. |

## -remarks

**FltProcessFileLock** processes a file lock ([**IRP_MJ_LOCK_CONTROL**](/windows-hardware/drivers/ifs/irp-mj-lock-control)) operation. The lock operation can be a fast I/O or IRP-based operation.

For unlock operations, the Filter Manager calls the **UnlockRoutine** ([**PUNLOCK_ROUTINE**](/windows-hardware/drivers/ifs/punlock-routine)) callback routine that the caller registered for the [**FILE_LOCK**](/windows-hardware/drivers/ifs/file-lock) structure in a previous call to [**FltAllocateFileLock**](nf-fltkernel-fltallocatefilelock.md).

When the lock operation is completed, the Filter Manager calls the **CompleteLockCallbackDataRoutine** ([**PFLT_COMPLETE_LOCK_CALLBACK_DATA_ROUTINE**](nc-fltkernel-pflt_complete_lock_callback_data_routine.md)) completion callback routine that the caller registered for the [**FILE_LOCK**](/windows-hardware/drivers/ifs/file-lock) structure in a previous call to [**FltAllocateFileLock**](nf-fltkernel-fltallocatefilelock.md).

When the **CallbackData** parameter passed to **FltProcessFileLock** represents a fast I/O operation, the callback specified in **CompleteLockCallbackDataRoutine** parameter of the [**FltAllocateFileLock**](nf-fltkernel-fltallocatefilelock.md) routine is not invoked. Only when the I/O operation in **CallbackData** is an IRP, and **CompleteLockCallbackDataRoutine** is not NULL, will the callback routine be called.

To determine whether the **CallbackData** represents a fast I/O operation, use the [**FLT_IS_FASTIO_OPERATION**](nf-fltkernel-flt_is_fastio_operation.md) macro.

To allocate and initialize a new file lock structure, call [**FltAllocateFileLock**](nf-fltkernel-fltallocatefilelock.md).

To free an initialized [**FILE_LOCK**](/windows-hardware/drivers/ifs/file-lock) structure, call [**FltFreeFileLock**](nf-fltkernel-fltfreefilelock.md).

## -see-also

[**FILE_LOCK**](/windows-hardware/drivers/ifs/file-lock)

[**FLT_CALLBACK_DATA**](ns-fltkernel-_flt_callback_data.md)

[**FLT_IS_FASTIO_OPERATION**](nf-fltkernel-flt_is_fastio_operation.md)

[**FltAllocateFileLock**](nf-fltkernel-fltallocatefilelock.md)

[**FltCheckLockForReadAccess**](nf-fltkernel-fltchecklockforreadaccess.md)

[**FltCheckLockForWriteAccess**](nf-fltkernel-fltchecklockforwriteaccess.md)

[**FltFreeFileLock**](nf-fltkernel-fltfreefilelock.md)

[**FltInitializeFileLock**](nf-fltkernel-fltinitializefilelock.md)

[**FltUninitializeFileLock**](nf-fltkernel-fltuninitializefilelock.md)

[**FsRtlProcessFileLock**](../ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlprocessfilelock.md)

[**IRP_MJ_LOCK_CONTROL**](/windows-hardware/drivers/ifs/irp-mj-lock-control)

[**PFLT_COMPLETE_LOCK_CALLBACK_DATA_ROUTINE**](nc-fltkernel-pflt_complete_lock_callback_data_routine.md)

[**PUNLOCK_ROUTINE**](/windows-hardware/drivers/ifs/punlock-routine)
