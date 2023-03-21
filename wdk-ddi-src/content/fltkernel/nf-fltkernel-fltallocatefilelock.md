---
UID: NF:fltkernel.FltAllocateFileLock
title: FltAllocateFileLock function (fltkernel.h)
description: The FltAllocateFileLock routine allocates and initializes a new FILE_LOCK structure.
tech.root: ifsk
ms.date: 03/20/2023
keywords: ["FltAllocateFileLock function"]
ms.keywords: FltAllocateFileLock, FltAllocateFileLock routine [Installable File System Drivers], FltApiRef_a_to_d_f59cead3-059a-4457-9339-c90cc007ca63.xml, fltkernel/FltAllocateFileLock, ifsk.fltallocatefilelock
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: Windows XP SP2
req.target-min-winversvr: Windows Server 2003 SP1
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
req.dll: 
req.irql: <= APC_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - FltAllocateFileLock
 - fltkernel/FltAllocateFileLock
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - FltMgr.lib
 - FltMgr.dll
api_name:
 - FltAllocateFileLock
---

# FltAllocateFileLock function

## -description

The **FltAllocateFileLock** routine allocates and initializes a new [**FILE_LOCK**](../ntifs/ns-ntifs-file_lock.md) structure.

## -parameters

### -param CompleteLockCallbackDataRoutine [in, optional]

Pointer to a [**PFLT_COMPLETE_LOCK_CALLBACK_DATA_ROUTINE**](nc-fltkernel-pflt_complete_lock_callback_data_routine.md)-typed callback routine to be called when an [**IRP_MJ_LOCK_CONTROL**](/windows-hardware/drivers/ifs/irp-mj-lock-control) request is completed. This parameter is optional and can be NULL.

### -param UnlockRoutine [in, optional]

Pointer to a [**PUNLOCK_ROUTINE**](../ntifs/nc-ntifs-punlock_routine.md)-typed callback routine to be called when the byte range is unlocked. This parameter is optional and can be NULL.

## -returns

**FltAllocateFileLock** returns a pointer to the newly allocated [**FILE_LOCK**](../ntifs/ns-ntifs-file_lock.md) structure.

## -remarks

**FltAllocateFileLock** allocates a new [**FILE_LOCK**](../ntifs/ns-ntifs-file_lock.md) structure from paged pool and initializes it.

The returned [**FILE_LOCK**](../ntifs/ns-ntifs-file_lock.md) structure can be used to lock a byte range in a file by calling [**FltProcessFileLock**](nf-fltkernel-fltprocessfilelock.md).

When the [**FILE_LOCK**](../ntifs/ns-ntifs-file_lock.md) structure is no longer needed, it can be uninitialized by calling [**FltUninitializeFileLock**](nf-fltkernel-fltuninitializefilelock.md). The uninitialized **FILE_LOCK** structure can then be initialized for reuse by calling **FltInitializeFileLock**.

To free an initialized [**FILE_LOCK**](../ntifs/ns-ntifs-file_lock.md) structure, call [**FltFreeFileLock**](nf-fltkernel-fltfreefilelock.md).

When the **CallbackData** parameter passed to [**FltProcessFileLock**](nf-fltkernel-fltprocessfilelock.md) represents a fast I/O operation, the callback specified in **CompleteLockCallbackDataRoutine** is not invoked. Only when the I/O operation in **CallbackData** is an IRP, and **CompleteLockCallbackDataRoutine** is not NULL, will the callback routine be called.

## -see-also

[**FILE_LOCK**](../ntifs/ns-ntifs-file_lock.md)

[**FltCheckLockForReadAccess**](nf-fltkernel-fltchecklockforreadaccess.md)

[**FltCheckLockForWriteAccess**](nf-fltkernel-fltchecklockforwriteaccess.md)

[**FltFreeFileLock**](nf-fltkernel-fltfreefilelock.md)

[**FltInitializeFileLock**](nf-fltkernel-fltinitializefilelock.md)

[**FltProcessFileLock**](nf-fltkernel-fltprocessfilelock.md)

[**FltUninitializeFileLock**](nf-fltkernel-fltuninitializefilelock.md)

[**FsRtlAllocateFileLock**](../ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlallocatefilelock.md)

[**IRP_MJ_LOCK_CONTROL**](/windows-hardware/drivers/ifs/irp-mj-lock-control)

[**PFLT_COMPLETE_LOCK_CALLBACK_DATA_ROUTINE**](nc-fltkernel-pflt_complete_lock_callback_data_routine.md)

[**PUNLOCK_ROUTINE**](../ntifs/nc-ntifs-punlock_routine.md)