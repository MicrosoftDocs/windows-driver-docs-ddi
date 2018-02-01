---
UID: NF:ntifs._FSRTL_ADVANCED_FCB_HEADER.FsRtlFastCheckLockForWrite~r5
title: FsRtlFastCheckLockForWrite function
author: windows-driver-content
description: The FsRtlFastCheckLockForWrite routine determines whether the specified process has write access to a locked byte range of a file.
old-location: ifsk\fsrtlfastchecklockforwrite.htm
old-project: ifsk
ms.assetid: 4b4295dd-0d4b-4d41-a2ca-f09fe2d8d8b2
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: fsrtlref_1f8feaa8-cc2d-47fb-af4a-00ef0efb4190.xml, ntifs/FsRtlFastCheckLockForWrite, FsRtlFastCheckLockForWrite, FsRtlFastCheckLockForWrite routine [Installable File System Drivers], ifsk.fsrtlfastchecklockforwrite
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	FsRtlFastCheckLockForWrite
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# FsRtlFastCheckLockForWrite function


## -description


The <b>FsRtlFastCheckLockForWrite</b> routine determines whether the specified process has write access to a locked byte range of a file.


## -syntax


````
BOOLEAN FsRtlFastCheckLockForWrite(
  _In_ PFILE_LOCK     FileLock,
  _In_ PLARGE_INTEGER StartingByte,
  _In_ PLARGE_INTEGER Length,
  _In_ ULONG          Key,
  _In_ PVOID          FileObject,
  _In_ PVOID          ProcessId
);
````


## -parameters




### -param FileLock [in]

A pointer to the FILE_LOCK structure for the file. This structure must have been initialized by a previous call to <a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlallocatefilelock~r1.md">FsRtlAllocateFileLock</a> or <a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlinitializefilelock~r2.md">FsRtlInitializeFileLock</a>.


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


The <a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlfastchecklockforread~r5.md">FsRtlFastCheckLockForWrite</a> routine returns <b>TRUE</b> if the specified process has write access, <b>FALSE</b> otherwise.



## -see-also

<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlinitializefilelock~r2.md">FsRtlInitializeFileLock</a>

<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlfastchecklockforread~r5.md">FsRtlFastCheckLockForRead</a>

<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlallocatefilelock~r1.md">FsRtlAllocateFileLock</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FsRtlFastCheckLockForWrite routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

