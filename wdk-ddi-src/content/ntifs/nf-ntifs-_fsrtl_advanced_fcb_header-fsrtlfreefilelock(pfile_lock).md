---
UID: NF:ntifs._FSRTL_ADVANCED_FCB_HEADER.FsRtlFreeFileLock(PFILE_LOCK)
title: FsRtlFreeFileLock function (ntifs.h)
description: The FsRtlFreeFileLock routine uninitializes and frees a file lock structure.
old-location: ifsk\fsrtlfreefilelock.htm
tech.root: ifsk
ms.assetid: 191a7964-4359-4b7f-8760-74f537b0737f
ms.date: 03/29/2018
ms.keywords: FsRtlFreeFileLock, FsRtlFreeFileLock routine [Installable File System Drivers], fsrtlref_112afa00-3370-4671-ad22-0743f8dd1c52.xml, ifsk.fsrtlfreefilelock, ntifs/FsRtlFreeFileLock
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: This routine is available on Microsoft Windows 2000 and later.
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
req.irql: "<= APC_LEVEL"
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- FsRtlFreeFileLock
product:
- Windows
targetos: Windows
req.typenames: VOLUME_READ_PLEX_INPUT, *PVOLUME_READ_PLEX_INPUT
ms.custom: RS5
---

# FsRtlFreeFileLock function


## -description


The <b>FsRtlFreeFileLock</b> routine uninitializes and frees a file lock structure.


## -parameters




### -param FileLock [in]

Pointer to the FILE_LOCK structure. This structure must have been allocated by a previous call to <b>FsRtlAllocateFileLock</b>.


## -returns



None




## -remarks



<b>FsRtlFreeFileLock</b> should be used only for file locks that were allocated and initialized by <b>FsRtlAllocateFileLock</b>.

It is a programming error to call <b>FsRtlFreeFileLock</b> for a FILE_LOCK structure that has already been uninitialized by a call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtluninitializefilelock">FsRtlUninitializeFileLock</a>.

Minifilters must call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltfreefilelock">FltFreeFileLock</a> instead of <b>FsRtlFreeFileLock</b>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltfreefilelock">FltFreeFileLock</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-fsrtlaretherecurrentfilelocks">FsRtlAreThereCurrentFileLocks</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlchecklockforreadaccess">FsRtlCheckLockForReadAccess</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlchecklockforwriteaccess">FsRtlCheckLockForWriteAccess</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlfastchecklockforread">FsRtlFastCheckLockForRead</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlfastchecklockforwrite">FsRtlFastCheckLockForWrite</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-fsrtlfastlock">FsRtlFastLock</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlfastunlockall">FsRtlFastUnlockAll</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlfastunlockallbykey">FsRtlFastUnlockAllByKey</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlfastunlocksingle">FsRtlFastUnlockSingle</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlgetnextfilelock">FsRtlGetNextFileLock</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlinitializefilelock">FsRtlInitializeFileLock</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlprocessfilelock">FsRtlProcessFileLock</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtluninitializefilelock">FsRtlUninitializeFileLock</a>
 

 

