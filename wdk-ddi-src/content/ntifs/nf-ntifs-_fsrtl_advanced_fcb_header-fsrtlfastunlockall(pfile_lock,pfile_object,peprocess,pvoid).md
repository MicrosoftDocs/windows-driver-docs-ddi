---
UID: NF:ntifs.FsRtlFastUnlockAll(PFILE_LOCK,PFILE_OBJECT,PEPROCESS,PVOID)
title: FsRtlFastUnlockAll function (ntifs.h)
description: The FsRtlFastUnlockAll routine releases all byte-range locks that were acquired by the specified process for a file.
old-location: ifsk\fsrtlfastunlockall.htm
tech.root: ifsk
ms.date: 03/29/2018
keywords: ["FsRtlFastUnlockAll function"]
ms.keywords: FsRtlFastUnlockAll, FsRtlFastUnlockAll routine [Installable File System Drivers], fsrtlref_713fc415-f52e-4e0f-8806-02f44fb9b3f4.xml, ifsk.fsrtlfastunlockall, ntifs/FsRtlFastUnlockAll
f1_keywords:
 - "ntifs/FsRtlFastUnlockAll"
 - "FsRtlFastUnlockAll"
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
- FsRtlFastUnlockAll
targetos: Windows
req.typenames: VOLUME_READ_PLEX_INPUT, *PVOLUME_READ_PLEX_INPUT
dev_langs:
 - c++
ms.custom: RS5
---

# FsRtlFastUnlockAll function


## -description


The <b>FsRtlFastUnlockAll</b> routine releases all byte-range locks that were acquired by the specified process for a file.


## -parameters




### -param FileLock 
[in]
Pointer to the FILE_LOCK structure for the file. This structure must have been initialized by a previous call to <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlallocatefilelock">FsRtlAllocateFileLock</a> or <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlinitializefilelock">FsRtlInitializeFileLock</a>.


### -param FileObject 
[in]
Pointer to the file object for the file.


### -param ProcessId 
[in]
Pointer to the process ID for the process.


### -param Context 
[in, optional]
Optional context pointer to be used when completing IRPs.


## -returns



<b>FsRtlFastUnlockAll</b> returns STATUS_SUCCESS or an error status code such as STATUS_RANGE_NOT_LOCKED.




## -remarks



After releasing the byte-range locks, <b>FsRtlFastUnlockAll</b> completes any currently queued lock IRPs that can now be completed.




## -see-also




<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlallocatefilelock">FsRtlAllocateFileLock</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlinitializefilelock">FsRtlInitializeFileLock</a>
 

 
