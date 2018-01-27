---
UID: NF:ntifs.FsRtlAreThereCurrentFileLocks
title: FsRtlAreThereCurrentFileLocks macro
author: windows-driver-content
description: The FsRtlAreThereCurrentFileLocks macro checks whether any byte range locks exist for the specified file.
old-location: ifsk\fsrtlaretherecurrentfilelocks.htm
old-project: ifsk
ms.assetid: 2d8789e1-721d-4abe-9864-0f7fdeb24482
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: ntifs/FsRtlAreThereCurrentFileLocks, FsRtlAreThereCurrentFileLocks function [Installable File System Drivers], ifsk.fsrtlaretherecurrentfilelocks, fsrtlref_c3102eee-b523-418a-8977-a875e0eb76b7.xml, FsRtlAreThereCurrentFileLocks
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
req.lib: ntifs.h
req.dll: 
req.irql: Any level
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	HeaderDef
apilocation: 
-	ntifs.h
apiname: 
-	FsRtlAreThereCurrentFileLocks
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# FsRtlAreThereCurrentFileLocks macro


## -description


The<b> FsRtlAreThereCurrentFileLocks</b> macro checks whether any byte range locks exist for the specified file. 


## -syntax


````
BOOLEAN FsRtlAreThereCurrentFileLocks(
  _In_ PFILE_LOCK FileLock
);
````


## -parameters




### -param FL

TBD




#### - FileLock [in]

Pointer to the FILE_LOCK structure for the file. This structure must have been initialized by a previous call to <a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlallocatefilelock~r1.md">FsRtlAllocateFileLock</a> or <a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlinitializefilelock~r2.md">FsRtlInitializeFileLock</a>.


## -remarks


File systems and filter drivers often call <b>FsRtlAreThereCurrentFileLocks</b> from their FastIoCheckIfPossible routines. 
<div class="alert"><b>Note</b>  If a byte-range lock has existed since the specified file was opened, the <b>FsRtlAreThereCurrentFileLocks </b>routine returns <b>TRUE</b>,  unless the relevant FILE_LOCK is reinitialized. If a lock was established, and then released, the use of <b>FsRtlAreThereCurrentFileLocks</b>  can prevent the assignment of oplocks unnecessarily. Use <a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlaretherecurrentorinprogressfilelocks.md">FsRtlAreThereCurrentOrInProgressFileLocks</a> to avoid this problem.</div><div> </div>


## -see-also

<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlallocatefilelock~r1.md">FsRtlAllocateFileLock</a>

<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlinitializefilelock~r2.md">FsRtlInitializeFileLock</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FsRtlAreThereCurrentFileLocks function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

