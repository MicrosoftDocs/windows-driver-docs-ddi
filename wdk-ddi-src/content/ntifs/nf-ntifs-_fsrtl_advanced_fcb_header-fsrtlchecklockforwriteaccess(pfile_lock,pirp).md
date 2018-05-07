---
UID: NF:ntifs._FSRTL_ADVANCED_FCB_HEADER.FsRtlCheckLockForWriteAccess(PFILE_LOCK,PIRP)
title: FsRtlCheckLockForWriteAccess function
author: windows-driver-content
description: The FsRtlCheckLockForWriteAccess routine determines whether the process associated with a given IRP has write access to a locked region of a file.
old-location: ifsk\fsrtlchecklockforwriteaccess.htm
old-project: ifsk
ms.assetid: 549da751-6a28-4d54-995f-dabb9e29ab09
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: FsRtlCheckLockForWriteAccess, FsRtlCheckLockForWriteAccess routine [Installable File System Drivers], fsrtlref_460451fb-37b9-4c7e-bf53-8d72c7e73a55.xml, ifsk.fsrtlchecklockforwriteaccess, ntifs/FsRtlCheckLockForWriteAccess
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	FsRtlCheckLockForWriteAccess
product: Windows
targetos: Windows
req.typenames: VOLUME_READ_PLEX_INPUT, *PVOLUME_READ_PLEX_INPUT
---

# FsRtlCheckLockForWriteAccess function


## -description


The <b>FsRtlCheckLockForWriteAccess</b> routine determines whether the process associated with a given IRP has write access to a locked region of a file.


## -parameters




### -param FileLock [in]

Pointer to the FILE_LOCK structure for the file. This structure must have been initialized by a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff545640">FsRtlAllocateFileLock</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff546122">FsRtlInitializeFileLock</a>.


### -param Irp [in]

Pointer to the IRP. Must be an IRP for a write operation.


## -returns



<b>FsRtlCheckLockForWriteAccess</b> returns <b>TRUE</b> if the process has write access, <b>FALSE</b> otherwise.




## -remarks



On Microsoft Windows XP and later, <b>FsRtlCheckLockForWriteAccess</b> checks the process to which the thread that requested the write operation is currently attached. 

On Microsoft Windows 2000 and earlier, <b>FsRtlCheckLockForWriteAccess</b> checks the process that created the thread. 

<b>FsRtlCheckLockForWriteAccess</b> checks to see if there are any conflicting locks in the byte range that is to be written.

<b>FsRtlCheckLockForWriteAccess</b> does not complete the IRP specified by <i>Irp</i>. 

Minifilters must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff541837">FltCheckLockForWriteAccess</a> instead of <b>FsRtlCheckLockForWriteAccess</b>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff541837">FltCheckLockForWriteAccess</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545640">FsRtlAllocateFileLock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545758">FsRtlCheckLockForReadAccess</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545928">FsRtlFastCheckLockForWrite</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546122">FsRtlInitializeFileLock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547166">FsRtlProcessFileLock</a>
 

 

