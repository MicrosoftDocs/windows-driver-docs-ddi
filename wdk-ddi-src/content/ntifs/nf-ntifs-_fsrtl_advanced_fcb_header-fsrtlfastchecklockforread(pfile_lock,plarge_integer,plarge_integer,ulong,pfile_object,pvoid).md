---
UID: NF:ntifs._FSRTL_ADVANCED_FCB_HEADER.FsRtlFastCheckLockForRead(PFILE_LOCK,PLARGE_INTEGER,PLARGE_INTEGER,ULONG,PFILE_OBJECT,PVOID)
title: FsRtlFastCheckLockForRead function (ntifs.h)
description: The FsRtlFastCheckLockForRead routine determines whether the specified process has read access to a locked byte range of a file.
old-location: ifsk\fsrtlfastchecklockforread.htm
tech.root: ifsk
ms.assetid: c3003169-8437-4f43-b777-fcb4d43d4d72
ms.date: 03/29/2018
ms.keywords: FsRtlFastCheckLockForRead, FsRtlFastCheckLockForRead routine [Installable File System Drivers], fsrtlref_b0a3dc82-d734-44b8-8762-7e10478f60c6.xml, ifsk.fsrtlfastchecklockforread, ntifs/FsRtlFastCheckLockForRead
ms.topic: function
req.header: ntifs.h
req.include-header: FltKernel.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: This routine is available on Microsoft Windows 2000 and later versions of Windows operating systems.
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
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	FsRtlFastCheckLockForRead
product:
-	Windows
targetos: Windows
req.typenames: VOLUME_READ_PLEX_INPUT, *PVOLUME_READ_PLEX_INPUT
ms.custom: RS5
---

# FsRtlFastCheckLockForRead function


## -description


The <b>FsRtlFastCheckLockForRead</b> routine determines whether the specified process has read access to a locked byte range of a file.


## -parameters




### -param FileLock [in]

A pointer to the FILE_LOCK structure for the file. This structure must have been initialized by a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff545640">FsRtlAllocateFileLock</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff546122">FsRtlInitializeFileLock</a>.


### -param StartingByte [in]

A pointer to a variable that specifies the starting byte offset within the file of the byte range to check.


### -param Length [in]

A pointer to a variable that specifies the length, in bytes, of the range to check.


### -param Key [in]

The key for the byte range lock.


### -param FileObject [in]

A pointer to the file object for the file.


### -param ProcessId [in]

A pointer to the process ID for the process.


## -returns



The <b>FsRtlFastCheckLockForRead</b> routine returns <b>TRUE</b> if the specified process has read access, <b>FALSE</b> otherwise.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff545640">FsRtlAllocateFileLock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545928">FsRtlFastCheckLockForWrite</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546122">FsRtlInitializeFileLock</a>
 

 

