---
UID: NF:ntifs.FsRtlCheckOplock
title: FsRtlCheckOplock function (ntifs.h)
description: Learn more about the FsRtlCheckOplock function.
tech.root: ifsk
ms.date: 09/27/2023
keywords: ["FsRtlCheckOplock function"]
ms.keywords: FsRtlCheckOplock, FsRtlCheckOplock routine [Installable File System Drivers], fsrtlref_c11dbb80-c7a8-437d-bb6b-661edcf2f24a.xml, ifsk.fsrtlcheckoplock, rxprocs/FsRtlCheckOplock
req.header: ntifs.h
req.include-header: FltKernel.h, Ntifs.h
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <= APC_LEVEL
targetos: Windows
req.typenames: 
ms.custom: RS5
f1_keywords:
 - FsRtlCheckOplock
 - ntifs/FsRtlCheckOplock
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - FsRtlCheckOplock
dev_langs:
 - c++
---

# FsRtlCheckOplock function

## -description

The **FsRtlCheckOplock** routine synchronizes the IRP for a file I/O operation with the file's current opportunistic lock (oplock) state.

## -parameters

### -param Oplock [in]

An opaque opportunistic lock pointer for the file. This pointer must have been initialized by a previous call to [**FsRtlInitializeOplock**](nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlinitializeoplock.md).

### -param Irp [in]

A pointer to the IRP for the I/O operation.

### -param Context [in, optional]

A pointer to caller-defined context information to be passed to the callback routines that the **CompletionRoutine** and **PostIrpRoutine** parameters point to.

### -param CompletionRoutine [in, optional]

A pointer to a caller-supplied callback routine. If an opportunistic lock break is in progress, this routine is called when the break is completed. This parameter is optional and can be NULL. If it is NULL, the caller is put into a wait state until the opportunistic lock break is completed.

This routine is declared as follows:

``` cpp
typedef VOID
(*POPLOCK_WAIT_COMPLETE_ROUTINE) (
      IN PVOID Context,
      IN PIRP Irp
      );
```

This routine has the following parameters:

| Parameter | Description |
| --------- | ----------- |
| Context   | A context information pointer that was passed in the **Context** parameter to **FsRtlCheckOplock**. |
| Irp       | A pointer to the IRP for the I/O operation. |

### -param PostIrpRoutine [in, optional]

A pointer to a caller-supplied callback routine to be called if the I/O operation is posted to a work queue. This parameter is optional and can be NULL.

This routine is declared as follows:

``` cpp
typedef VOID
(*POPLOCK_FS_PREPOST_IRP) (
      IN PVOID Context,
      IN PIRP Irp
      );
```

This routine has the following parameters:

| Parameter | Description |
| --------- | ----------- |
| Context   | A context information pointer that was passed in the **Context** parameter to **FsRtlCheckOplock**. |
| Irp       | A pointer to the IRP for the I/O operation. |

## -returns

The **FsRtlCheckOplock** routine returns STATUS_SUCCESS or an appropriate NTSTATUS code such as one of the following:

| Return code | Description |
| ----------- | ----------- |
| STATUS_CANCELLED | The IRP was canceled. STATUS_CANCELLED is an error code.  |
| STATUS_CANNOT_BREAK_OPLOCK  | If the IRP is an IRP_MJ_CREATE and FILE_OPEN_REQUIRING_OPLOCK is in the IRP's CreateOptions, the routine will not initiate a break of an existing opportunistic lock, but fails with STATUS_CANNOT_BREAK_OPLOCK.  |
| STATUS_OPLOCK_BREAK_IN_PROGRESS | An opportunistic lock break is underway. The IRP is an IRP_MJ_CREATE request, and FILE_COMPLETE_IF_OPLOCKED was specified in the create options parameter for the operation. STATUS_OPLOCK_BREAK_IN_PROGRESS is a success code.  |
| STATUS_PENDING | An opportunistic lock break has been initiated, and control of the IRP has been passed to the oplock package. If CompletionRoutine is NULL, this routine will block while the oplock break is processed, rather than return STATUS_PENDING. STATUS_PENDING is a success code. |

## -remarks

**FsRtlCheckOplock** synchronizes the IRP for an I/O operation with the current opportunistic lock state of a file according to the following conditions:

* If the I/O operation will cause the opportunistic lock to break, the opportunistic lock break is initiated.

* If the I/O operation cannot continue until the opportunistic lock break is complete, **FsRtlCheckOplock** returns STATUS_PENDING and calls the callback routine that the **PostIrpRoutine** parameter points to.

If a file system or filter driver uses opportunistic locks, it must call **FsRtlCheckOplock** from any dispatch routines for I/O operations that can cause opportunistic lock breaks. This rule applies to the following types of I/O operations, because these operations can cause opportunistic lock breaks:

* IRP_MJ_CLEANUP
* IRP_MJ_CREATE
* IRP_MJ_FILE_SYSTEM_CONTROL
* IRP_MJ_FLUSH_BUFFERS
* IRP_MJ_LOCK_CONTROL
* IRP_MJ_READ
* IRP_MJ_SET_INFORMATION
* IRP_MJ_WRITE

For detailed information about opportunistic locks, see the Windows SDK documentation.

Minifilters should call [**FltCheckOplock**](../fltkernel/nf-fltkernel-fltcheckoplock.md) instead of **FsRtlCheckOplock**.

## -see-also

[**FSCTL_OPBATCH_ACK_CLOSE_PENDING**](/windows-hardware/drivers/ifs/fsctl-opbatch-ack-close-pending)

[**FSCTL_OPLOCK_BREAK_ACKNOWLEDGE**](/windows-hardware/drivers/ifs/fsctl-oplock-break-acknowledge)

[**FSCTL_OPLOCK_BREAK_ACK_NO_2**](/windows-hardware/drivers/ifs/fsctl-oplock-break-ack-no-2)

[**FSCTL_OPLOCK_BREAK_NOTIFY**](/windows-hardware/drivers/ifs/fsctl-oplock-break-notify)

[**FSCTL_REQUEST_BATCH_OPLOCK**](/windows-hardware/drivers/ifs/fsctl-request-batch-oplock)

[**FSCTL_REQUEST_FILTER_OPLOCK**](/windows-hardware/drivers/ifs/fsctl-request-filter-oplock)

[**FSCTL_REQUEST_OPLOCK_LEVEL_1**](/windows-hardware/drivers/ifs/fsctl-request-oplock-level-1)

[**FSCTL_REQUEST_OPLOCK_LEVEL_2**](/windows-hardware/drivers/ifs/fsctl-request-oplock-level-2)

[**FltCheckOplock**](../fltkernel/nf-fltkernel-fltcheckoplock.md)

[**FsRtlCurrentBatchOplock**](nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlcurrentbatchoplock.md)

[**FsRtlInitializeOplock**](nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlinitializeoplock.md)

[**FsRtlOplockFsctrl**](nf-ntifs-_fsrtl_advanced_fcb_header-fsrtloplockfsctrl.md)

[**FsRtlOplockIsFastIoPossible**](nf-ntifs-_fsrtl_advanced_fcb_header-fsrtloplockisfastiopossible.md)

[**FsRtlUninitializeOplock**](nf-ntifs-_fsrtl_advanced_fcb_header-fsrtluninitializeoplock.md)
