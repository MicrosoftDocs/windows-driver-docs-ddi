---
UID: NF:ntifs.FsRtlAllocateFileLock(PCOMPLETE_LOCK_IRP_ROUTINE,PUNLOCK_ROUTINE)
title: FsRtlAllocateFileLock function (ntifs.h)
description: The FsRtlAllocateFileLock routine allocates and initializes a new FILE_LOCK structure.
old-location: ifsk\fsrtlallocatefilelock.htm
tech.root: ifsk
ms.assetid: 148c177d-162a-4578-a40c-2e5fe6176d51
ms.date: 03/29/2018
ms.keywords: FsRtlAllocateFileLock, FsRtlAllocateFileLock routine [Installable File System Drivers], fsrtlref_cb42425d-add9-4c5b-bddc-54dc55448902.xml, ifsk.fsrtlallocatefilelock, ntifs/FsRtlAllocateFileLock
f1_keywords:
 - "ntifs/FsRtlAllocateFileLock"
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
req.irql: <= APC_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- FsRtlAllocateFileLock
product:
- Windows
targetos: Windows
req.typenames: VOLUME_READ_PLEX_INPUT, *PVOLUME_READ_PLEX_INPUT
dev_langs:
 - c++
ms.custom: RS5
---

# FsRtlAllocateFileLock function


## -description


The <b>FsRtlAllocateFileLock</b> routine allocates and initializes a new FILE_LOCK structure.


## -parameters




### -param CompleteLockIrpRoutine [in, optional]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/pcomplete-lock-irp-routine">PCOMPLETE_LOCK_IRP_ROUTINE</a>-typed callback routine to be called when an <a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/irp-mj-lock-control">IRP_MJ_LOCK_CONTROL</a> request is completed. This parameter is optional and can be <b>NULL</b>.


### -param UnlockRoutine [in, optional]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/punlock-routine">PUNLOCK_ROUTINE</a>-typed callback routine to be called when the byte range is unlocked. This parameter is optional and can be <b>NULL</b>.


## -returns



<b>FsRtlAllocateFileLock</b> returns a pointer to the newly allocated FILE_LOCK structure.




## -remarks



<b>FsRtlAllocateFileLock</b> allocates a new FILE_LOCK structure from paged pool and initializes it.

Minifilters should call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltallocatefilelock">FltAllocateFileLock</a> instead of <b>FsRtlAllocateFileLock</b>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltallocatefilelock">FltAllocateFileLock</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-fsrtlaretherecurrentfilelocks">FsRtlAreThereCurrentFileLocks</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlchecklockforreadaccess">FsRtlCheckLockForReadAccess</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlchecklockforwriteaccess">FsRtlCheckLockForWriteAccess</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlfastchecklockforread">FsRtlFastCheckLockForRead</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlfastchecklockforwrite">FsRtlFastCheckLockForWrite</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-fsrtlfastlock">FsRtlFastLock</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlfastunlockall">FsRtlFastUnlockAll</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlfastunlockallbykey">FsRtlFastUnlockAllByKey</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlfastunlocksingle">FsRtlFastUnlockSingle</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlgetnextfilelock">FsRtlGetNextFileLock</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlinitializefilelock">FsRtlInitializeFileLock</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlprocessfilelock">FsRtlProcessFileLock</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtluninitializefilelock">FsRtlUninitializeFileLock</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/irp-mj-lock-control">IRP_MJ_LOCK_CONTROL</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/pcomplete-lock-irp-routine">PCOMPLETE_LOCK_IRP_ROUTINE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/punlock-routine">PUNLOCK_ROUTINE</a>
 

 

