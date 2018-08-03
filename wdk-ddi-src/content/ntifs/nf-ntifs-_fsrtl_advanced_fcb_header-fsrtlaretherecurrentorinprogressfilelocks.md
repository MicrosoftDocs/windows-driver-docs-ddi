---
UID: NF:ntifs._FSRTL_ADVANCED_FCB_HEADER.FsRtlAreThereCurrentOrInProgressFileLocks
title: FsRtlAreThereCurrentOrInProgressFileLocks function
author: windows-driver-content
description: TheFsRtlAreThereCurrentOrInProgressFileLocks routine determines if there are byte range locks assigned to a file or any lock operations in progress for that file.
old-location: ifsk\fsrtlaretherecurrentorinprogressfilelocks.htm
tech.root: ifsk
ms.assetid: 9e5e0e37-5f01-4bc3-b660-c65c540af04e
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: FsRtlAreThereCurrentOrInProgressFileLocks, FsRtlAreThereCurrentOrInProgressFileLocks routine [Installable File System Drivers], fsrtlref_66517730-628e-4aa4-b3c0-b5c0e0fd4d7d.xml, ifsk.fsrtlaretherecurrentorinprogressfilelocks, ntifs/FsRtlAreThereCurrentOrInProgressFileLocks
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: FltKernel.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 7 and later versions of the Windows operating system.
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
req.irql: "<=APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	FsRtlAreThereCurrentOrInProgressFileLocks
product:
- Windows
targetos: Windows
req.typenames: 
---

# FsRtlAreThereCurrentOrInProgressFileLocks function


## -description


The<b>FsRtlAreThereCurrentOrInProgressFileLocks </b>routine determines if there are byte range locks assigned to a file or any lock operations in progress for that file.


## -parameters




### -param FileLock [in]

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff540328">FILE_LOCK</a> structure for the file to be checked.


## -returns



The routine returns <b>TRUE</b> when there are any byte range locks assigned to the file or when there are byte range lock requests in progress for the file. Otherwise, the routine returns <b>FALSE</b>.




## -remarks



File systems can use the <b>FsRtlAreThereCurrentOrInProgressFileLocks</b> routine in <a href="https://msdn.microsoft.com/5cbbfecc-2182-40f6-9f54-a8146c1f663f">Oplock Semantics</a> to determine whether to grant a shared oplock.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff540328">FILE_LOCK</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545640">FsRtlAllocateFileLock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546038">FsRtlGetNextFileLock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546122">FsRtlInitializeFileLock</a>



<a href="https://msdn.microsoft.com/5cbbfecc-2182-40f6-9f54-a8146c1f663f">Oplock Semantics</a>
 

 

