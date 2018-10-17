---
UID: NF:ntifs._FSRTL_ADVANCED_FCB_HEADER.FsRtlInitializeFileLock(PFILE_LOCK,PCOMPLETE_LOCK_IRP_ROUTINE,PUNLOCK_ROUTINE)
title: FsRtlInitializeFileLock function
author: windows-driver-content
description: The FsRtlInitializeFileLock routine initializes a FILE_LOCK structure.
old-location: ifsk\fsrtlinitializefilelock.htm
tech.root: ifsk
ms.assetid: 0a476cd8-b0e6-4faa-bb97-3647a88ecded
ms.date: 3/29/2018
ms.keywords: FsRtlInitializeFileLock, FsRtlInitializeFileLock routine [Installable File System Drivers], fsrtlref_227dc998-43e4-427b-afe5-6d26ff5d1c36.xml, ifsk.fsrtlinitializefilelock, ntifs/FsRtlInitializeFileLock
ms.topic: function
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
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	FsRtlInitializeFileLock
product:
-	Windows
targetos: Windows
req.typenames: VOLUME_READ_PLEX_INPUT, *PVOLUME_READ_PLEX_INPUT
---

# FsRtlInitializeFileLock function


## -description


The <b>FsRtlInitializeFileLock</b> routine initializes a FILE_LOCK structure.


## -parameters




### -param FileLock [in]

Pointer to an uninitialized FILE_LOCK structure.


### -param CompleteLockIrpRoutine [in, optional]

Pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff551032">PCOMPLETE_LOCK_IRP_ROUTINE</a>-typed callback routine to be called when an <a href="https://msdn.microsoft.com/library/windows/hardware/ff549251">IRP_MJ_LOCK_CONTROL</a> request is completed. This parameter is optional and can be <b>NULL</b>.


### -param UnlockRoutine [in, optional]

Pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff551951">PUNLOCK_ROUTINE</a>-typed callback routine to be called when the byte range is unlocked. This parameter is optional and can be <b>NULL</b>.


## -returns



None




## -remarks



<b>FsRtlInitializeFileLock</b> initializes an uninitialized FILE_LOCK structure.

It is a programming error to call <b>FsRtlInitializeFileLock</b> for a FILE_LOCK structure that has already been initialized by <b>FsRtlInitializeFileLock</b> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff545640">FsRtlAllocateFileLock</a>, unless the structure has been uninitialized by a subsequent call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff547313">FsRtlUninitializeFileLock</a>.

Once initialized, the FILE_LOCK structure can be used to lock a byte range in a file by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff547166">FsRtlProcessFileLock</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff545940">FsRtlFastLock</a>. <b>FsRtlProcessFileLock</b> processes lock IRPs. <b>FsRtlFastLock</b> performs non-IRP locking.

When the FILE_LOCK structure is no longer needed, it can be uninitialized by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff547313">FsRtlUninitializeFileLock</a>. The uninitialized FILE_LOCK structure can then be initialized for reuse by calling <b>FsRtlInitializeFileLock</b>.

Minifilters must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff543273">FltInitializeFileLock</a> instead of <b>FsRtlInitializeFileLock</b>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff543273">FltInitializeFileLock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545640">FsRtlAllocateFileLock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545697">FsRtlAreThereCurrentFileLocks</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545940">FsRtlFastLock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547166">FsRtlProcessFileLock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547313">FsRtlUninitializeFileLock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549251">IRP_MJ_LOCK_CONTROL</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548343">IoCompleteRequest</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551032">PCOMPLETE_LOCK_IRP_ROUTINE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551951">PUNLOCK_ROUTINE</a>
 

 

