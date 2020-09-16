---
UID: NF:ntifs.FsRtlInitializeOplock
title: FsRtlInitializeOplock function (ntifs.h)
description: FsRtlInitializeOplock initializes an opportunistic lock (oplock) pointer.
old-location: ifsk\fsrtlinitializeoplock.htm
tech.root: ifsk
ms.assetid: bfa6f6fd-ce50-40e0-9e98-81519260cc86
ms.date: 04/16/2018
keywords: ["FsRtlInitializeOplock function"]
ms.keywords: FsRtlInitializeOplock, FsRtlInitializeOplock function [Installable File System Drivers], fsrtlref_e9d22a89-79a8-4aae-9b5c-fca644d5f972.xml, ifsk.fsrtlinitializeoplock, ntifs/FsRtlInitializeOplock
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
 - FsRtlInitializeOplock
 - ntifs/FsRtlInitializeOplock
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - FsRtlInitializeOplock
---

# FsRtlInitializeOplock function


## -description

<b>FsRtlInitializeOplock</b> initializes an opportunistic lock (oplock) pointer.

## -parameters

### -param Oplock 

[in, out]
Caller-supplied pointer variable that receives the initialized opportunistic lock pointer. This variable must be initialized to <b>NULL</b> before the initial call to <b>FsRtlInitializeOplock</b>.

## -remarks

File systems and filter drivers call <b>FsRtlInitializeOplock</b> to initialize an opaque opportunistic lock pointer. 

When the opportunistic lock pointer is no longer needed, it can be uninitialized by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtluninitializeoplock">FsRtlUninitializeOplock</a>. The uninitialized opportunistic lock pointer can then be initialized for reuse by calling <b>FsRtlInitializeOplock</b>. 

For detailed information about opportunistic locks, see the Microsoft Windows SDK documentation. 

Minifilters should call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltinitializeoplock">FltInitializeOplock</a> instead of <b>FsRtlInitializeOplock</b>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/fsctl-opbatch-ack-close-pending">FSCTL_OPBATCH_ACK_CLOSE_PENDING</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/fsctl-oplock-break-acknowledge">FSCTL_OPLOCK_BREAK_ACKNOWLEDGE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/fsctl-oplock-break-ack-no-2">FSCTL_OPLOCK_BREAK_ACK_NO_2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/fsctl-oplock-break-notify">FSCTL_OPLOCK_BREAK_NOTIFY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/fsctl-request-batch-oplock">FSCTL_REQUEST_BATCH_OPLOCK</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/fsctl-request-filter-oplock">FSCTL_REQUEST_FILTER_OPLOCK</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/fsctl-request-oplock-level-1">FSCTL_REQUEST_OPLOCK_LEVEL_1</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/fsctl-request-oplock-level-2">FSCTL_REQUEST_OPLOCK_LEVEL_2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltinitializeoplock">FltInitializeOplock</a>



<a href="https://docs.microsoft.com/windows/win32/api/rrascfg/nf-rrascfg-ieapproviderconfig-initialize">FsRtlCheckOplock</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlcurrentbatchoplock">FsRtlCurrentBatchOplock</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtloplockfsctrl">FsRtlOplockFsctrl</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtloplockisfastiopossible">FsRtlOplockIsFastIoPossible</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtluninitializeoplock">FsRtlUninitializeOplock</a>

