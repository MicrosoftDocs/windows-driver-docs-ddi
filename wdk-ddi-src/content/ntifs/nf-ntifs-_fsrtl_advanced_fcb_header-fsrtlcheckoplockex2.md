---
UID: NF:ntifs.FsRtlCheckOplockEx2
title: FSRTL_ADVANCED_FCB_HEADER::FsRtlCheckOplockEx2
description: FsRtlCheckOplockEx2 synchronizes the IRP for a file I/O operation with the current opportunistic lock (oplock) state of the file.
tech.root: ifsk
ms.date: 03/24/2020
ms.topic: method
ms.keywords: FSRTL_ADVANCED_FCB_HEADER::FsRtlCheckOplockEx2, FsRtlCheckOplockEx2, FSRTL_ADVANCED_FCB_HEADER.FsRtlCheckOplockEx2, FSRTL_ADVANCED_FCB_HEADER::FsRtlCheckOplockEx2, FSRTL_ADVANCED_FCB_HEADER.FsRtlCheckOplockEx2
req.header: ntifs.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 2004
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.irql: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
targetos: Windows
f1_keywords:
 - FsRtlCheckOplockEx2
 - ntifs/FsRtlCheckOplockEx2
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - ntifs.h
api_name:
 - FsRtlCheckOplockEx2
product:
 - Windows
---

# FSRTL_ADVANCED_FCB_HEADER::FsRtlCheckOplockEx2


## -description

**FsRtlCheckOplockEx2** synchronizes the IRP for a file I/O operation with the current opportunistic lock (oplock) state of the file.

## -parameters

### -param Oplock 

[in]
Pointer to the opaque oplock structure for the file. This pointer must have been initialized by a previous call to [**FsRtlInitializeOplock**](./nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlinitializeoplock.md).

### -param Irp 

[in]
Pointer to the IRP that declares the requested I/O operation.

### -param Flags 

[in]
A bitmask for the associated file I/O operation. A file system or filter driver sets bits to specify the behavior of **FsRtlCheckOplockEx2**. *Flags* has the following options:

| Flag Value | Meaning |
| ---------- | ------- |
| OPLOCK_FLAG_COMPLETE_IF_OPLOCKED (0x00000001) | Specifies to allow an oplock break to proceed without blocking or pending the operation that caused the oplock break. |
| OPLOCK_FLAG_OPLOCK_KEY_CHECK_ONLY (0x00000002) | Specifies that **FsRtlCheckOplockEx2** should only check for an oplock key on the FILE_OBJECT that is associated with the IRP that the *Irp* parameter points to. **FsRtlCheckOplockEx2** must then add the key if one is provided in the IRP. No other oplock processing occurs; that is, no oplock break will occur. Supported starting with Windows 7. |
| OPLOCK_FLAG_BACK_OUT_ATOMIC_OPLOCK (0x00000004) | Specifies that **FsRtlCheckOplockEx2** should revert any state that was previously set up through a call to the [**FsRtlOplockFsctrl**](./nf-ntifs-_fsrtl_advanced_fcb_header-fsrtloplockfsctrl.md) routine. **FsRtlOplockFsctrl** is called during processing of an IRP_MJ_CREATE request that specifies the FILE_OPEN_REQUIRING_OPLOCK flag in the create options parameter. The OPLOCK_FLAG_BACK_OUT_ATOMIC_OPLOCK flag is typically used in final processing of such a create request when it previously failed. Supported starting with Windows 7. |
| OPLOCK_FLAG_IGNORE_OPLOCK_KEYS (0x00000008) | Specifies to allow all oplock breaks to proceed regardless of the oplock key. Supported starting with Windows 7. |
| OPLOCK_FLAG_PARENT_OBJECT (0x00000010) | Specifies that *Oplock* is associated with the parent (directory) of the file or directory to which the IRP in the *Irp* parameter is directed. Supported starting with Windows 8. |
| OPLOCK_FLAG_CLOSING_DELETE_ON_CLOSE (0x00000020) | Specifies that the I/O operation specified in *Irp* is an IRP_MJ_CLEANUP for a handle that was originally opened with the FILE_DELETE_ON_CLOSE flag set in its create options.  This flag as no effect if *Irp* is not an IRP_MJ_CLEANUP operation.  Specifying this flag may result in an oplock break. Supported starting with Windows 8. |
| OPLOCK_FLAG_REMOVING_FILE_OR_LINK   (0x00000040) | Specifies handling an oplock break on a parent directory when deleting a file or link in that directory. If specified, this flag must be combined with OPLOCK_FLAG_PARENT_OBJECT.  This flag must be specified when the file system is processing an operation that results in the removal of a link or file. Supported starting with Windows 8. |

### -param FlagsEx2 

[in]
Reserved; must be set to zero.

### -param CompletionRoutineContext 

[in, optional]
Pointer to caller-defined context information to be passed to the callback routine that the *CompletionRoutine* parameter points to. This parameter is optional and can be **NULL**.

### -param CompletionRoutine 

[in, optional]
Pointer to a caller-supplied callback routine. If an oplock break is in progress, this routine is called when the break is completed. This parameter is optional and can be **NULL**. If it is **NULL**, **FsRtlCheckOpLockEx2** operates synchronously, putting the caller into a wait state until the oplock break is completed.

*CompletionRoutine* is declared as follows:

```c++
typedef VOID
(*POPLOCK_WAIT_COMPLETE_ROUTINE) (
      IN PVOID Context,
      IN PIRP Irp
      );
```

*CompletionRoutine* has the following parameters:

- *Context*: A context information pointer that was passed in the *Context* parameter to **FsRtlCheckOplockEx2**.
- *Irp*: A pointer to the IRP for the I/O operation.

### -param PostIrpRoutine 

[in, optional]
Pointer to a caller-supplied callback routine to be called if the I/O operation is posted to a work queue. This parameter is optional and can be **NULL**.

*PostIrpRoutine* is declared as follows:

```c++
typedef VOID
(*POPLOCK_FS_PREPOST_IRP) (
      IN PVOID Context,
      IN PIRP Irp
      );
```

*PostIrpRoutine* has the following parameters:

- *Context*, which is a context information pointer that was passed in the *Context* parameter to **FsRtlCheckOplockEx2**.
- *Irp*: A pointer to the IRP for the I/O operation.

### -param Timeout 

[in]
If non-zero, specifies a timeout (in milliseconds) to wait on an event used to block the caller's thread in order to wait for the oplock break to complete. This value is ignored unless both of the following conditions are true: *CompletionRoutine* is NULL and *NotifyRoutine* is not NULL.

### -param NotifyContext 

[in, optional]
Pointer to an [OPLOCK_NOTIFY_PARAMS](ns-ntifs-_oplock_notify_params.md) structure to be passed to the callback routine that the *NotifyRoutine* parameter points to. This parameter is optional and can be **NULL**.

### -param NotifyRoutine 

[in, optional]
Pointer to a caller-supplied callback routine to be called for oplock state notification. This parameter is optional and can be **NULL**.

*NotifyRoutine* is declared as follows:

```c++
typedef NTSTATUS
(*POPLOCK_NOTIFY_ROUTINE) (
      IN POPLOCK_NOTIFY_PARAMS NotifyParams
      );
```

*NotifyRoutine* has the following parameters:

- *NotifyParams*, which is set to be the *NotifyContext* parameter passed to **FsRtlCheckOplockEx2**.

## -returns

**FsRtlCheckOplockEx2** returns STATUS_SUCCESS or an appropriate NTSTATUS code such as one of the following:

| Return code | Description |
| ----------- | ----------- |
| STATUS_CANCELLED | The IRP was canceled. STATUS_CANCELLED is an error code. |
| STATUS_CANNOT_BREAK_OPLOCK | The oplock break cannot be accomplished. The IRP is an IRP_MJ_CREATE request.  FILE_OPEN_REQUIRING_OPLOCK was specified in the create options parameter for the operation, and there is a granted oplock. |
| STATUS_OPLOCK_BREAK_IN_PROGRESS | An oplock break is underway. The IRP is an IRP_MJ_CREATE request, and FILE_COMPLETE_IF_OPLOCKED was specified in the create options parameter for the operation. STATUS_OPLOCK_BREAK_IN_PROGRESS is a success code that is returned if OPLOCK_FLAG_COMPLETE_IF_OPLOCKED was set, and an oplock has been broken. |
| STATUS_PENDING | An oplock break is underway, and control of the IRP was passed to the oplock package. If *CompletionRoutine* is **NULL**, **FsRtlCheckOplockEx2** blocks while the oplock break is processed rather than return STATUS_PENDING. STATUS_PENDING is a success code. |

## -remarks

Minifilters should call [**FltCheckOplockEx**](../fltkernel/nf-fltkernel-fltcheckoplockex.md) instead of **FsRtlCheckOplockEx2**.

**FsRtlCheckOplockEx2** synchronizes the IRP for an I/O operation with the current oplock state of a file according to the following conditions:

- If the I/O operation will cause the oplock to break, the oplock break is initiated.

- If the I/O operation cannot continue until the oplock break is complete and a completion routine in *CompletionRoutine* was specified, **FsRtlCheckOplockEx2** returns STATUS_PENDING and calls the callback routine specified in *PostIrpRoutine*. When the oplock break has been acknowledged, the callback routine in *CompletionRoutine* is called.

- If the I/O operation cannot continue until the oplock break is complete and *CompletionRoutine* was not specified, the caller's thread is blocked and **FsRtlCheckOplockEx2** will return only when the oplock break is complete.

If the caller's thread is blocked and *NotifyRoutine* is not **NULL**, *NotifyRoutine* will be called for any or all of the following reasons set in *NotifyParams*:

- OPLOCK_NOTIFY_BREAK_WAIT_INTERIM_TIMEOUT
- OPLOCK_NOTIFY_BREAK_WAIT_TERMINATED

The call to *NotifyRoutine* for any of the above reasons occurs only if *CompletionRoutine* is NULL and it is necessary to block the caller's thread to wait for the break to complete.

If *NotifyRoutine* is invoked for reason OPLOCK_NOTIFY_BREAK_WAIT_INTERIM_TIMEOUT, it will always be invoked for reason OPLOCK_NOTIFY_BREAK_WAIT_TERMINATED if the wait terminates/completes for any reason (which may be never).

**FsRtlCheckOplockEx2** ignores the OPLOCK_NOTIFY_BREAK_WAIT_INTERIM_TIMEOUT and OPLOCK_NOTIFY_BREAK_WAIT_TERMINATED status codes returned by *NotifyRoutine*.

A *PostIrpRoutine* should be specified only if a *CompletionRoutine* has been specified. When *PostIrpRoutine* is not **NULL**, it is called before anything is queued to the waiting Irp queue.

If the OPLOCK_FLAG_PARENT_OBJECT flag is specified in *Flags*, **FsRtlCheckOplockEx2** will unconditionally break any existing parent oplock; that is, the major code in the *Irp* is not considered.

If a file system uses oplocks, it must call **FsRtlCheckOplockEx2** from any dispatch routines for I/O operations that can cause oplock breaks. This rule applies to the following types of I/O operations, because these operations can cause oplock breaks:

- IRP_MJ_CLEANUP

- IRP_MJ_CREATE

- IRP_MJ_FILE_SYSTEM_CONTROL

- IRP_MJ_FLUSH_BUFFERS

- IRP_MJ_LOCK_CONTROL

- IRP_MJ_READ

- IRP_MJ_SET_INFORMATION

- IRP_MJ_WRITE

For more information about oplocks, see [Opportunistic Locks](/windows/win32/fileio/opportunistic-locks).

## -see-also

[FSCTL_OPBATCH_ACK_CLOSE_PENDING](/windows-hardware/drivers/ifs/fsctl-opbatch-ack-close-pending)

[FSCTL_OPLOCK_BREAK_ACKNOWLEDGE](/windows-hardware/drivers/ifs/fsctl-oplock-break-acknowledge)

[FSCTL_OPLOCK_BREAK_ACK_NO_2](/windows-hardware/drivers/ifs/fsctl-oplock-break-ack-no-2)

[FSCTL_OPLOCK_BREAK_NOTIFY](/windows-hardware/drivers/ifs/fsctl-oplock-break-notify)

[FSCTL_REQUEST_BATCH_OPLOCK](/windows-hardware/drivers/ifs/fsctl-request-batch-oplock)

[FSCTL_REQUEST_FILTER_OPLOCK](/windows-hardware/drivers/ifs/fsctl-request-filter-oplock)

[FSCTL_REQUEST_OPLOCK_LEVEL_1](/windows-hardware/drivers/ifs/fsctl-request-oplock-level-1)

[FSCTL_REQUEST_OPLOCK_LEVEL_2](/windows-hardware/drivers/ifs/fsctl-request-oplock-level-2)

[FltCheckOplockEx](../fltkernel/nf-fltkernel-fltcheckoplockex.md)

[FsRtlCurrentBatchOplock](./nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlcurrentbatchoplock.md)

[FsRtlInitializeOplock](./nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlinitializeoplock.md)

[FsRtlOplockFsctrl](./nf-ntifs-_fsrtl_advanced_fcb_header-fsrtloplockfsctrl.md)

[FsRtlOplockIsFastIoPossible](./nf-ntifs-_fsrtl_advanced_fcb_header-fsrtloplockisfastiopossible.md)

[FsRtlUninitializeOplock](./nf-ntifs-_fsrtl_advanced_fcb_header-fsrtluninitializeoplock.md)

[OPLOCK_NOTIFY_PARAMS](ns-ntifs-_oplock_notify_params.md)

