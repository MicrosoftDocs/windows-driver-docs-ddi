---
UID: NF:ntifs.FsRtlFastLock
title: FsRtlFastLock macro
author: windows-driver-content
description: The FsRtlFastLock macro is used by file systems and filter drivers to request a byte-range lock for a file stream.
old-location: ifsk\fsrtlfastlock.htm
old-project: ifsk
ms.assetid: c3e209b5-9925-4911-8c42-0f15c1c710be
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: FsRtlFastLock, FsRtlFastLock function [Installable File System Drivers], fsrtlref_c60db87b-ac5a-4c60-83f2-7381e0156806.xml, ifsk.fsrtlfastlock, ntifs/FsRtlFastLock
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
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntifs.h
api_name:
-	FsRtlFastLock
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# FsRtlFastLock macro


## -description


The <b>FsRtlFastLock</b> macro is used by file systems and filter drivers to request a byte-range lock for a file stream. 


## -syntax


````
BOOLEAN FsRtlFastLock(
  _In_  PFILE_LOCK       FileLock,
  _In_  PFILE_OBJECT     FileObject,
  _In_  PLARGE_INTEGER   FileOffset,
  _In_  PLARGE_INTEGER   Length,
  _In_  PEPROCESS        ProcessId,
  _In_  ULONG            Key,
  _In_  BOOLEAN          FailImmediately,
  _In_  BOOLEAN          ExclusiveLock,
  _Out_ PIO_STATUS_BLOCK Iosb,
  _In_  PVOID            Context,
  _In_  BOOLEAN          AlreadySynchronized
);
````


## -parameters




### -param A1

TBD


### -param A2

TBD


### -param A3

TBD


### -param A4

TBD


### -param A5

TBD


### -param A6

TBD


### -param A7

TBD


### -param A8

TBD


### -param A9

TBD


### -param A10

TBD


### -param A11

TBD






#### - FileLock [in]

Pointer to the FILE_LOCK structure for the file. This structure must have been initialized by a previous call to <a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlallocatefilelock~r1.md">FsRtlAllocateFileLock</a> or <a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlinitializefilelock~r2.md">FsRtlInitializeFileLock</a>.


#### - FileObject [in]

Pointer to the file object for the open file. The file object must have been created with GENERIC_READ or GENERIC_WRITE access to the file (or both). 


#### - FileOffset [in]

Pointer to a variable that specifies the starting byte offset within the file of the range to be locked.


#### - Length [in]

Pointer to a variable that specifies the length in bytes of the range to be locked.


#### - ProcessId [in]

Pointer to the process ID for the process requesting the byte-range lock.


#### - Key [in]

The key to be assigned to the byte-range lock.


#### - FailImmediately [in]

Boolean value specifying whether the lock request should fail if the lock cannot be granted immediately. If the caller can be put into a wait state until the request is granted, set <i>FailImmediately</i> to <b>FALSE</b>. If it cannot, set <i>FailImmediately</i> to <b>TRUE</b>. 


#### - ExclusiveLock [in]

Set to <b>TRUE</b> if an exclusive lock is requested, <b>FALSE</b> if a shared lock is requested.


#### - Iosb [out]

Pointer to a caller-allocated IO_STATUS_BLOCK structure that receives status information about the lock request. 


#### - Context [in]

Optional pointer to a context to use when releasing the byte-range lock. 


#### - AlreadySynchronized [in]

This parameter is obsolete, but is retained for compatibility with legacy drivers.


## -remarks



The <b>FsRtlFastLock</b> macro causes the caller to acquire a byte-range lock on a region of the specified file.

A return value of <b>TRUE</b> indicates that the IO_STATUS_BLOCK structure pointed to by <i>Iosb</i> received status information about the lock operation. To examine the contents of this structure, use the NT_STATUS macro.




## -see-also

<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlinitializefilelock~r2.md">FsRtlInitializeFileLock</a>



<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlallocatefilelock~r1.md">FsRtlAllocateFileLock</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FsRtlFastLock function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

