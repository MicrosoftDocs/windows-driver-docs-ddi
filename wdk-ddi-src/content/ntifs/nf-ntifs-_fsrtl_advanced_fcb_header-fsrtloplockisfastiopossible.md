---
UID: NF:ntifs.FsRtlOplockIsFastIoPossible
title: FsRtlOplockIsFastIoPossible function (ntifs.h)
description: Learn more about the FsRtlOplockIsFastIoPossible function.
tech.root: ifsk
ms.date: 09/27/2023
keywords: ["FsRtlOplockIsFastIoPossible function"]
ms.keywords: FsRtlOplockIsFastIoPossible, FsRtlOplockIsFastIoPossible function [Installable File System Drivers], fsrtlref_94131dc4-e2ee-4ec0-92b9-39cd8a7d6e41.xml, ifsk.fsrtloplockisfastiopossible, rxprocs/FsRtlOplockIsFastIoPossible
req.header: ntifs.h
req.include-header: Ntifs.h
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <= APC_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - FsRtlOplockIsFastIoPossible
 - ntifs/FsRtlOplockIsFastIoPossible
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - FsRtlOplockIsFastIoPossible
---

# FsRtlOplockIsFastIoPossible function

## -description

**FsRtlOplockIsFastIoPossible** checks a file's opportunistic lock (oplock) state to determine whether fast I/O can be performed on the file.

## -parameters

### -param Oplock [in]

Opaque opportunistic lock pointer for the file. This pointer must have been initialized by a previous call to [**FsRtlInitializeOplock**](nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlinitializeoplock.md).

## -returns

**FsRtlOplockIsFastIoPossible** returns FALSE if there are outstanding opportunistic locks on the file that prevent fast I/O from being performed; TRUE otherwise.

## -remarks

**FsRtlOplockIsFastIoPossible** determines whether fast I/O can be performed on a file, according to the following conditions:

* If the **Oplock** parameter is NULL, or if the value of **Oplock* is NULL, there are no outstanding opportunistic locks on the file, and fast I/O can be performed on the file.

* If an exclusive opportunistic lock was granted for the file, but no oplock break is in progress, fast I/O can be performed on the file.

For detailed information about opportunistic locks, see the Windows SDK documentation.

Minifilters should call [**FltOplockIsFastIoPossible**](../fltkernel/nf-fltkernel-fltoplockisfastiopossible.md) instead of **FsRtlOplockIsFastIoPossible**.

## -see-also

[FSCTL_OPBATCH_ACK_CLOSE_PENDING](/windows-hardware/drivers/ifs/fsctl-opbatch-ack-close-pending)

[FSCTL_OPLOCK_BREAK_ACKNOWLEDGE](/windows-hardware/drivers/ifs/fsctl-oplock-break-acknowledge)

[FSCTL_OPLOCK_BREAK_ACK_NO_2](/windows-hardware/drivers/ifs/fsctl-oplock-break-ack-no-2)

[FSCTL_OPLOCK_BREAK_NOTIFY](/windows-hardware/drivers/ifs/fsctl-oplock-break-notify)

[FSCTL_REQUEST_BATCH_OPLOCK](/windows-hardware/drivers/ifs/fsctl-request-batch-oplock)

[FSCTL_REQUEST_FILTER_OPLOCK](/windows-hardware/drivers/ifs/fsctl-request-filter-oplock)

[FSCTL_REQUEST_OPLOCK_LEVEL_1](/windows-hardware/drivers/ifs/fsctl-request-oplock-level-1)

[FSCTL_REQUEST_OPLOCK_LEVEL_2](/windows-hardware/drivers/ifs/fsctl-request-oplock-level-2)

[**FltOplockIsFastIoPossible**](../fltkernel/nf-fltkernel-fltoplockisfastiopossible.md)

[**FsRtlCheckOplock**](/windows/win32/api/rrascfg/nf-rrascfg-ieapproviderconfig-initialize)

[**FsRtlCurrentBatchOplock**](nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlcurrentbatchoplock.md)

[**FsRtlInitializeOplock**](nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlinitializeoplock.md)

[**FsRtlOplockFsctrl**](nf-ntifs-_fsrtl_advanced_fcb_header-fsrtloplockfsctrl.md)

[**FsRtlUninitializeOplock**](nf-ntifs-_fsrtl_advanced_fcb_header-fsrtluninitializeoplock.md)
