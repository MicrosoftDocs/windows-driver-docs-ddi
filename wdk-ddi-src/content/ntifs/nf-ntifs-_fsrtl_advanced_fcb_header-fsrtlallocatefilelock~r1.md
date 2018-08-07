---
UID: NF:ntifs._FSRTL_ADVANCED_FCB_HEADER.FsRtlAllocateFileLock~r1
title: FsRtlAllocateFileLock function
author: windows-driver-content
description: The FsRtlAllocateFileLock routine allocates and initializes a new FILE_LOCK structure.
old-location: ifsk\fsrtlallocatefilelock.htm
tech.root: ifsk
ms.assetid: 148c177d-162a-4578-a40c-2e5fe6176d51
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: FsRtlAllocateFileLock, FsRtlAllocateFileLock routine [Installable File System Drivers], fsrtlref_cb42425d-add9-4c5b-bddc-54dc55448902.xml, ifsk.fsrtlallocatefilelock, ntifs/FsRtlAllocateFileLock
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	FsRtlAllocateFileLock
product:
- Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# FsRtlAllocateFileLock function


## -description


The <b>FsRtlAllocateFileLock</b> routine allocates and initializes a new FILE_LOCK structure.


## -parameters




### -param CompleteLockIrpRoutine [in, optional]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff551032">PCOMPLETE_LOCK_IRP_ROUTINE</a>-typed callback routine to be called when an <a href="https://msdn.microsoft.com/library/windows/hardware/ff549251">IRP_MJ_LOCK_CONTROL</a> request is completed. This parameter is optional and can be <b>NULL</b>.


### -param UnlockRoutine [in, optional]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff551951">PUNLOCK_ROUTINE</a>-typed callback routine to be called when the byte range is unlocked. This parameter is optional and can be <b>NULL</b>.


## -returns



<b>FsRtlAllocateFileLock</b> returns a pointer to the newly allocated FILE_LOCK structure.




## -remarks



<b>FsRtlAllocateFileLock</b> allocates a new FILE_LOCK structure from paged pool and initializes it.

Minifilters should call <a href="https://msdn.microsoft.com/library/windows/hardware/ff541743">FltAllocateFileLock</a> instead of <b>FsRtlAllocateFileLock</b>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff541743">FltAllocateFileLock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545697">FsRtlAreThereCurrentFileLocks</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545758">FsRtlCheckLockForReadAccess</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545760">FsRtlCheckLockForWriteAccess</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545918">FsRtlFastCheckLockForRead</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545928">FsRtlFastCheckLockForWrite</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545940">FsRtlFastLock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545947">FsRtlFastUnlockAll</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545954">FsRtlFastUnlockAllByKey</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545958">FsRtlFastUnlockSingle</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546038">FsRtlGetNextFileLock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546122">FsRtlInitializeFileLock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547166">FsRtlProcessFileLock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547313">FsRtlUninitializeFileLock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549251">IRP_MJ_LOCK_CONTROL</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551032">PCOMPLETE_LOCK_IRP_ROUTINE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551951">PUNLOCK_ROUTINE</a>
 

 

