---
UID: NF:ntifs.FsRtlAreThereCurrentFileLocks
title: FsRtlAreThereCurrentFileLocks macro
author: windows-driver-content
description: The FsRtlAreThereCurrentFileLocks macro checks whether any byte range locks exist for the specified file.
old-location: ifsk\fsrtlaretherecurrentfilelocks.htm
old-project: ifsk
ms.assetid: 2d8789e1-721d-4abe-9864-0f7fdeb24482
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: FsRtlAreThereCurrentFileLocks, FsRtlAreThereCurrentFileLocks function [Installable File System Drivers], fsrtlref_c3102eee-b523-418a-8977-a875e0eb76b7.xml, ifsk.fsrtlaretherecurrentfilelocks, ntifs/FsRtlAreThereCurrentFileLocks
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Desktop
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
req.lib: 
req.dll: 
req.irql: Any level
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntifs.h
api_name:
-	FsRtlAreThereCurrentFileLocks
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# FsRtlAreThereCurrentFileLocks macro


## -description


The<b> FsRtlAreThereCurrentFileLocks</b> macro checks whether any byte range locks exist for the specified file. 


## -parameters




### -param FL

TBD






#### - FileLock [in]

Pointer to the FILE_LOCK structure for the file. This structure must have been initialized by a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff545640">FsRtlAllocateFileLock</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff546122">FsRtlInitializeFileLock</a>.


## -remarks



File systems and filter drivers often call <b>FsRtlAreThereCurrentFileLocks</b> from their FastIoCheckIfPossible routines. 

<div class="alert"><b>Note</b>  If a byte-range lock has existed since the specified file was opened, the <b>FsRtlAreThereCurrentFileLocks </b>routine returns <b>TRUE</b>,  unless the relevant FILE_LOCK is reinitialized. If a lock was established, and then released, the use of <b>FsRtlAreThereCurrentFileLocks</b>  can prevent the assignment of oplocks unnecessarily. Use <a href="https://msdn.microsoft.com/library/windows/hardware/ff545706">FsRtlAreThereCurrentOrInProgressFileLocks</a> to avoid this problem.</div>
<div> </div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff545640">FsRtlAllocateFileLock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546122">FsRtlInitializeFileLock</a>
 

 

