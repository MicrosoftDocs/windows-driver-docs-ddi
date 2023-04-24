---
UID: NC:fltkernel.PFLT_COMPLETE_LOCK_CALLBACK_DATA_ROUTINE
title: PFLT_COMPLETE_LOCK_CALLBACK_DATA_ROUTINE (fltkernel.h)
description: A minifilter driver can register a routine of type PFLT_COMPLETE_LOCK_CALLBACK_DATA_ROUTINE as the minifilter driver's CompleteLockCallbackDataRoutine callback routine for a FILE_LOCK structure.
tech.root: ifsk
ms.date: 03/20/2023
keywords: ["PFLT_COMPLETE_LOCK_CALLBACK_DATA_ROUTINE callback function"]
ms.keywords: CompleteLockCallbackDataRoutine, CompleteLockCallbackDataRoutine routine [Installable File System Drivers], FltCallbacks_a02e356c-ad01-4ae4-bfff-b753ffa0a1c3.xml, PFLT_COMPLETE_LOCK_CALLBACK_DATA_ROUTINE, fltkernel/CompleteLockCallbackDataRoutine, ifsk.pflt_complete_lock_callback_data_routine
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Desktop
req.target-min-winverclnt: Windows XP SP2
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
req.lib: 
req.dll: 
req.irql: <=APC_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - PFLT_COMPLETE_LOCK_CALLBACK_DATA_ROUTINE
 - fltkernel/PFLT_COMPLETE_LOCK_CALLBACK_DATA_ROUTINE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - fltkernel.h
api_name:
 - PFLT_COMPLETE_LOCK_CALLBACK_DATA_ROUTINE
---

# PFLT_COMPLETE_LOCK_CALLBACK_DATA_ROUTINE callback function

## -description

A minifilter driver can register a routine of type **PFLT_COMPLETE_LOCK_CALLBACK_DATA_ROUTINE** as the minifilter driver's **CompleteLockCallbackDataRoutine** callback routine for a [**FILE_LOCK**](../ntifs/ns-ntifs-file_lock.md) structure.

## -parameters

### -param Context [in, optional]

Context pointer that was passed to [**FltProcessFileLock**](nf-fltkernel-fltprocessfilelock.md).

### -param CallbackData [in]

Pointer to the callback data ([**FLT_CALLBACK_DATA**](ns-fltkernel-_flt_callback_data.md)) structure for the [**IRP_MJ_LOCK_CONTROL**](/windows-hardware/drivers/ifs/irp-mj-lock-control) operation that is being completed. The lock request type will be one of the following:

* IRP_MN_LOCK
* IRP_MN_UNLOCK_ALL
* IRP_MN_UNLOCK_ALL_BY_KEY
* IRP_MN_UNLOCK_SINGLE

## -returns

This routine returns STATUS_SUCCESS or an appropriate NTSTATUS value. If it returns an NTSTATUS value that is not a success code, the file lock is removed from the file.

## -remarks

A minifilter driver can optionally specify a routine of type **PFLT_COMPLETE_LOCK_CALLBACK_DATA_ROUTINE** as the minifilter driver's **CompleteLockCallbackDataRoutine** routine for a byte-range file lock. To specify this routine, the minifilter driver passes a pointer to the routine as the **CompleteLockCallbackDataRoutine** parameter for [**FltAllocateFileLock**](nf-fltkernel-fltallocatefilelock.md).

When completing the an [**IRP_MJ_LOCK_CONTROL**](/windows-hardware/drivers/ifs/irp-mj-lock-control) operation for the file lock, filter manager calls this routine, if specified, as a notification to the minifilter.

## -see-also

[**FILE_LOCK**](../ntifs/ns-ntifs-file_lock.md)

[**FltAllocateFileLock**](nf-fltkernel-fltallocatefilelock.md)

[**FltCheckLockForReadAccess**](nf-fltkernel-fltchecklockforreadaccess.md)

[**FltCheckLockForWriteAccess**](nf-fltkernel-fltchecklockforwriteaccess.md)

[**FltFreeFileLock**](nf-fltkernel-fltfreefilelock.md)

[**FltInitializeFileLock**](nf-fltkernel-fltinitializefilelock.md)

[**FltProcessFileLock**](nf-fltkernel-fltprocessfilelock.md)

[**FltUninitializeFileLock**](nf-fltkernel-fltuninitializefilelock.md)

[**IRP_MJ_LOCK_CONTROL**](/windows-hardware/drivers/ifs/irp-mj-lock-control)

[**PUNLOCK_ROUTINE**](../ntifs/nc-ntifs-punlock_routine.md)
