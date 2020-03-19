---
UID: NF:ntifs.FsRtlCheckLockForReadAccess(PFILE_LOCK,PIRP)
title: FsRtlCheckLockForReadAccess function (ntifs.h)
description: The FsRtlCheckLockForReadAccess routine determines whether the process associated with a given IRP has read access to a locked region of a file.
old-location: ifsk\fsrtlchecklockforreadaccess.htm
tech.root: ifsk
ms.assetid: 3734b286-b5cb-4906-9947-3ad23ef54267
ms.date: 03/29/2018
keywords: ["FsRtlCheckLockForReadAccess function"]
ms.keywords: FsRtlCheckLockForReadAccess, FsRtlCheckLockForReadAccess routine [Installable File System Drivers], fsrtlref_6ec3721a-c748-40c2-8469-336a56fd9eb6.xml, ifsk.fsrtlchecklockforreadaccess, ntifs/FsRtlCheckLockForReadAccess
f1_keywords:
 - "ntifs/FsRtlCheckLockForReadAccess"
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
- FsRtlCheckLockForReadAccess
product:
- Windows
targetos: Windows
req.typenames: VOLUME_READ_PLEX_INPUT, *PVOLUME_READ_PLEX_INPUT
dev_langs:
 - c++
ms.custom: RS5
---

# FsRtlCheckLockForReadAccess function


## -description


The <b>FsRtlCheckLockForReadAccess</b> routine determines whether the process associated with a given IRP has read access to a locked region of a file.


## -parameters




### -param FileLock [in]

Pointer to the FILE_LOCK structure for the file. This structure must have been initialized by a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlallocatefilelock">FsRtlAllocateFileLock</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlinitializefilelock">FsRtlInitializeFileLock</a>.


### -param Irp [in]

Pointer to the IRP. Must be an IRP for a read operation.


## -returns



<b>FsRtlCheckLockForReadAccess</b> returns <b>TRUE</b> if the process has read access, <b>FALSE</b> otherwise.




## -remarks



On Microsoft Windows XP and later, <b>FsRtlCheckLockForReadAccess</b> checks the process to which the thread that requested the read operation is currently attached.

On Microsoft Windows 2000 and earlier, <b>FsRtlCheckLockForReadAccess</b> checks the process that created the thread.

<b>FsRtlCheckLockForReadAccess</b> checks to see if there are any conflicting locks in the byte range that is to be read.

<b>FsRtlCheckLockForReadAccess</b> does not complete the IRP specified by <i>Irp</i>.

Minifilters must call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltchecklockforreadaccess">FltCheckLockForReadAccess</a> instead of <b>FsRtlCheckLockForReadAccess</b>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltchecklockforreadaccess">FltCheckLockForReadAccess</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlallocatefilelock">FsRtlAllocateFileLock</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlchecklockforwriteaccess">FsRtlCheckLockForWriteAccess</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlfastchecklockforread">FsRtlFastCheckLockForRead</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlinitializefilelock">FsRtlInitializeFileLock</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlprocessfilelock">FsRtlProcessFileLock</a>
 

 

