---
UID: NF:ntifs.FsRtlOplockFsctrlEx
title: FsRtlOplockFsctrlEx function (ntifs.h)
description: The FsRtlOplockFsctrlEx routine performs various opportunistic lock (oplock) operations on behalf of a file system or filter driver.
old-location: ifsk\fsrtloplockfsctrlex.htm
tech.root: ifsk
ms.date: 01/08/2021
keywords: ["FsRtlOplockFsctrlEx function"]
ms.keywords: FsRtlOplockFsctrlEx, FsRtlOplockFsctrlEx routine [Installable File System Drivers], fsrtlref_fa242815-36f3-4c0a-ae1d-826d0208e191.xml, ifsk.fsrtloplockfsctrlex, ntifs/FsRtlOplockFsctrlEx
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: The FsRtlOplockFsctrlEx routine is available starting with Windows 7.
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
 - FsRtlOplockFsctrlEx
 - ntifs/FsRtlOplockFsctrlEx
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - FsRtlOplockFsctrlEx
dev_langs:
 - c++
---

# FsRtlOplockFsctrlEx function

## -description

The **FsRtlOplockFsctrlEx** routine performs various opportunistic lock (oplock) operations on behalf of a file system or filter driver.

## -parameters

### -param Oplock

[in] Opaque oplock pointer for the file. This pointer must have been initialized by a previous call to [**FsRtlInitializeOplock**](nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlinitializeoplock.md).

### -param Irp

[in] Pointer to the IRP for the I/O operation. This parameter is required and cannot be **NULL**.

### -param OpenCount

[in]
Number of user handles for the file, if an exclusive oplock is being requested. Setting a nonzero value for a level 2, R, or RH oplock request indicates that there are byte-range locks on the file. For information about oplock types, see [Oplock Overview](/windows-hardware/drivers/ifs/oplock-overview).

### -param Flags

[in] A bitmask for the associated oplock operations. A file system or filter driver sets bits to specify the behavior of **FsRtlOplockFsctrlEx**. This parameter has the following options:

| Flag | Meaning |
| ---- | ------- |
| OPLOCK_FSCTRL_FLAG_ALL_KEYS_MATCH (0x00000001) | The file system verified that all oplock keys on any currently open handles match. By specifying this flag, you allow the oplock package to grant an oplock of level RW or RWH when more than one open handle to the file exists. For more information about oplock types, see [Oplock Overview](/windows-hardware/drivers/ifs/oplock-overview).

## -returns

**FsRtlOplockFsctrlEx** returns one of the following NTSTATUS values:

| Return code | Description |
| ----------- | ----------- |
| STATUS_SUCCESS | For an IRP_MJ_CREATE request, STATUS_SUCCESS indicates that the requested filter oplock was granted. For a FSCTL operation, the meaning of STATUS_SUCCESS depends on the FSCTL code. For more information, see the reference pages for the FSCTL codes listed in the following Remarks section. |
| STATUS_CANCELLED | The I/O operation was canceled. STATUS_CANCELLED is an error code. |
| STATUS_INVALID_PARAMETER | The FSCTL code for the I/O operation was not one of the valid values listed in the following Remarks section. STATUS_INVALID_PARAMETER is an error code. |
| STATUS_OPLOCK_NOT_GRANTED | The oplock could not be granted. STATUS_OPLOCK_NOT_GRANTED is an error code. |
| STATUS_PENDING | Used only for FSCTL operations. The meaning of STATUS_PENDING depends on the FSCTL code. For more information, see the reference pages for the FSCTL codes listed in the following Remarks section. STATUS_PENDING is a success code. |
| STATUS_CANNOT_BREAK_OPLOCK | A new oplock could not be granted. The IRP is an IRP_MJ_CREATE request and FILE_OPEN_REQUIRING_OPLOCK was specified in the create options parameter for the operation. STATUS_CANNOT_BREAK_OPLOCK is a success code. |

## -remarks

File systems and legacy filter drivers call **FsRtlOplockFsctrlEx** to perform various oplock operations for a create or file system control I/O operation. Minifilters should call [**FltOplockFsctrlEx**](../fltkernel/nf-fltkernel-fltoplockfsctrlex.md) instead of **FsRtlOplockFsctrlEx**.

The IRP pointed to by the *Irp* parameter must be a valid IRP for an [IRP_MJ_FILE_SYSTEM_CONTROL](/windows-hardware/drivers/kernel/irp-mj-file-system-control) or [IRP_MJ_CREATE](/windows-hardware/drivers/ifs/irp-mj-create) operation.

If the IRP is an [IRP_MJ_FILE_SYSTEM_CONTROL](/windows-hardware/drivers/kernel/irp-mj-file-system-control) request, **FsRtlOplockFsctrlEx** can be used with one of the following FSCTL codes, which is set in *IrpSp->Parameters.FileSystemControl.FsControlCode*:

* [FSCTL_OPBATCH_ACK_CLOSE_PENDING](/windows-hardware/drivers/ifs/fsctl-opbatch-ack-close-pending)
* [FSCTL_OPLOCK_BREAK_ACK_NO_2](/windows-hardware/drivers/ifs/fsctl-oplock-break-ack-no-2)
* [FSCTL_OPLOCK_BREAK_ACKNOWLEDGE](/windows-hardware/drivers/ifs/fsctl-oplock-break-acknowledge)
* [FSCTL_OPLOCK_BREAK_NOTIFY](/windows-hardware/drivers/ifs/fsctl-oplock-break-notify)
* [FSCTL_REQUEST_BATCH_OPLOCK](/windows-hardware/drivers/ifs/fsctl-request-batch-oplock)
* [FSCTL_REQUEST_FILTER_OPLOCK](/windows-hardware/drivers/ifs/fsctl-request-filter-oplock)
* [FSCTL_REQUEST_OPLOCK_LEVEL_1](/windows-hardware/drivers/ifs/fsctl-request-oplock-level-1)
* [FSCTL_REQUEST_OPLOCK_LEVEL_2](/windows-hardware/drivers/ifs/fsctl-request-oplock-level-2)
* [FSCTL_REQUEST_OPLOCK](/windows-hardware/drivers/ifs/fsctl-request-oplock)

For more information about these FSCTLs and about opportunistic locks in general, see the Microsoft Windows SDK documentation.

If the IRP is an IRP_MJ_CREATE request, **FsRtlOplockFsctrlEx** can be used to request a pending filter oplock if all of the following conditions are true:

* The value of the *OpenCount* parameter must be 1.
* The value of the *DesiredAccess* parameter for the IRP_MJ_CREATE request must be FILE_READ_ATTRIBUTES.
* The value of the *ShareAccess* parameter for the IRP_MJ_CREATE request must be FILE_SHARE_READ | FILE_SHARE_WRITE | FILE_SHARE_DELETE.

If the request for a pending filter oplock is granted, **FsRtlOplockFsctrlEx** returns STATUS_SUCCESS. For more information about create parameters, see the reference entry for [IRP_MJ_CREATE](/windows-hardware/drivers/ifs/irp-mj-create).

Filters and file systems that call this function must synchronize calls into the system-supplied oplock package. See [Oplock synchronization](/windows-hardware/drivers/ifs/oplock-synchronization) for more information.

## -see-also

[FSCTL_OPBATCH_ACK_CLOSE_PENDING](/windows-hardware/drivers/ifs/fsctl-opbatch-ack-close-pending)

[FSCTL_OPLOCK_BREAK_ACKNOWLEDGE](/windows-hardware/drivers/ifs/fsctl-oplock-break-acknowledge)

[FSCTL_OPLOCK_BREAK_ACK_NO_2](/windows-hardware/drivers/ifs/fsctl-oplock-break-ack-no-2)

[FSCTL_OPLOCK_BREAK_NOTIFY](/windows-hardware/drivers/ifs/fsctl-oplock-break-notify)

[FSCTL_REQUEST_BATCH_OPLOCK](/windows-hardware/drivers/ifs/fsctl-request-batch-oplock)

[FSCTL_REQUEST_FILTER_OPLOCK](/windows-hardware/drivers/ifs/fsctl-request-filter-oplock)

[FSCTL_REQUEST_OPLOCK](/windows-hardware/drivers/ifs/fsctl-request-oplock)

[FSCTL_REQUEST_OPLOCK_LEVEL_1](/windows-hardware/drivers/ifs/fsctl-request-oplock-level-1)

[FSCTL_REQUEST_OPLOCK_LEVEL_2](/windows-hardware/drivers/ifs/fsctl-request-oplock-level-2)

[**FltOplockFsctrl**](../fltkernel/nf-fltkernel-fltoplockfsctrl.md)

[**FsRtlInitializeOplock**](nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlinitializeoplock.md)

[IRP_MJ_CREATE](/windows-hardware/drivers/ifs/irp-mj-create)

[IRP_MJ_FILE_SYSTEM_CONTROL](/windows-hardware/drivers/kernel/irp-mj-file-system-control)
