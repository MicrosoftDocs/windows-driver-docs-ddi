---
UID: NF:ntifs._FSRTL_ADVANCED_FCB_HEADER.FsRtlFastCheckLockForRead~r5
title: FsRtlFastCheckLockForRead function
author: windows-driver-content
description: The FsRtlFastCheckLockForRead routine determines whether the specified process has read access to a locked byte range of a file.
old-location: ifsk\fsrtlfastchecklockforread.htm
old-project: ifsk
ms.assetid: c3003169-8437-4f43-b777-fcb4d43d4d72
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: FsRtlFastCheckLockForRead routine [Installable File System Drivers], ntifs/FsRtlFastCheckLockForRead, FsRtlFastCheckLockForRead, ifsk.fsrtlfastchecklockforread, fsrtlref_b0a3dc82-d734-44b8-8762-7e10478f60c6.xml
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
-	FsRtlFastCheckLockForRead
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# FsRtlFastCheckLockForRead function


## -description


The <b>FsRtlFastCheckLockForRead</b> routine determines whether the specified process has read access to a locked byte range of a file.


## -syntax


````
BOOLEAN FsRtlFastCheckLockForRead(
  _In_ PFILE_LOCK     FileLock,
  _In_ PLARGE_INTEGER StartingByte,
  _In_ PLARGE_INTEGER Length,
  _In_ ULONG          Key,
  _In_ PFILE_OBJECT   FileObject,
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


The <b>FsRtlFastCheckLockForRead</b> routine returns <b>TRUE</b> if the specified process has read access, <b>FALSE</b> otherwise.



## -see-also

<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlinitializefilelock~r2.md">FsRtlInitializeFileLock</a>

<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlallocatefilelock~r1.md">FsRtlAllocateFileLock</a>

<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlfastchecklockforwrite~r5.md">FsRtlFastCheckLockForWrite</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FsRtlFastCheckLockForRead routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

