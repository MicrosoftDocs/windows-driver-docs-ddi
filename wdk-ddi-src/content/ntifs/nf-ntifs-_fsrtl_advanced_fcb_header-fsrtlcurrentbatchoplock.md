---
UID: NF:ntifs.FsRtlCurrentBatchOplock
title: FsRtlCurrentBatchOplock function (ntifs.h)
description: A file system or filter driver calls FsRtlCurrentBatchOplock to determine whether there are any batch or filter opportunistic locks (oplocks) on a file.
old-location: ifsk\fsrtlcurrentbatchoplock.htm
tech.root: ifsk
ms.assetid: cfa02246-12ac-4229-bcdb-4792eb5cb0e7
ms.date: 04/16/2018
ms.keywords: FsRtlCurrentBatchOplock, FsRtlCurrentBatchOplock function [Installable File System Drivers], fsrtlref_d5d16133-2531-4e50-85b7-381740d45d9a.xml, ifsk.fsrtlcurrentbatchoplock, ntifs/FsRtlCurrentBatchOplock
ms.topic: function
f1_keywords:
 - "ntifs/FsRtlCurrentBatchOplock"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- FsRtlCurrentBatchOplock
product:
- Windows
targetos: Windows
req.typenames: 
---

# FsRtlCurrentBatchOplock function


## -description


A file system or filter driver calls <b>FsRtlCurrentBatchOplock</b> to determine whether there are any batch or filter opportunistic locks (oplocks) on a file. 


## -parameters




### -param Oplock [in]

Opaque opportunistic lock pointer for the file. This pointer must have been initialized by a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlinitializeoplock">FsRtlInitializeOplock</a>. 


## -returns



<b>FsRtlCurrentBatchOplock</b> returns <b>TRUE</b> if there are current outstanding batch or filter opportunistic locks; <b>FALSE</b> otherwise. 




## -remarks



<b>FsRtlCurrentBatchOplock</b> returns <b>FALSE</b> if no batch or filter opportunistic locks are currently held. 

For detailed information about opportunistic locks, see the Microsoft Windows SDK documentation. 

Minifilters should call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltcurrentbatchoplock">FltCurrentBatchOplock</a> instead of <b>FsRtlCurrentBatchOplock</b>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/fsctl-opbatch-ack-close-pending">FSCTL_OPBATCH_ACK_CLOSE_PENDING</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/fsctl-oplock-break-acknowledge">FSCTL_OPLOCK_BREAK_ACKNOWLEDGE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/fsctl-oplock-break-ack-no-2">FSCTL_OPLOCK_BREAK_ACK_NO_2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/fsctl-oplock-break-notify">FSCTL_OPLOCK_BREAK_NOTIFY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/fsctl-request-batch-oplock">FSCTL_REQUEST_BATCH_OPLOCK</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/fsctl-request-filter-oplock">FSCTL_REQUEST_FILTER_OPLOCK</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/fsctl-request-oplock-level-1">FSCTL_REQUEST_OPLOCK_LEVEL_1</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/fsctl-request-oplock-level-2">FSCTL_REQUEST_OPLOCK_LEVEL_2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltcurrentbatchoplock">FltCurrentBatchOplock</a>



<a href="https://docs.microsoft.com/windows/desktop/api/rrascfg/nf-rrascfg-ieapproviderconfig-initialize">FsRtlCheckOplock</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlinitializeoplock">FsRtlInitializeOplock</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtloplockfsctrl">FsRtlOplockFsctrl</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtloplockisfastiopossible">FsRtlOplockIsFastIoPossible</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtluninitializeoplock">FsRtlUninitializeOplock</a>
 

 

