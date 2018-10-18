---
UID: NF:ntifs.FsRtlFastLock
title: FsRtlFastLock macro
author: windows-driver-content
description: The FsRtlFastLock macro is used by file systems and filter drivers to request a byte-range lock for a file stream.
old-location: ifsk\fsrtlfastlock.htm
tech.root: ifsk
ms.assetid: c3e209b5-9925-4911-8c42-0f15c1c710be
ms.date: 4/16/2018
ms.keywords: FsRtlFastLock, FsRtlFastLock function [Installable File System Drivers], fsrtlref_c60db87b-ac5a-4c60-83f2-7381e0156806.xml, ifsk.fsrtlfastlock, ntifs/FsRtlFastLock
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
product:
- Windows
targetos: Windows
req.typenames: 
---

# FsRtlFastLock macro


## -description


The <b>FsRtlFastLock</b> macro is used by file systems and filter drivers to request a byte-range lock for a file stream. 


## -parameters




### -param A1

<p>Pointer to the FILE_LOCK structure for the file. This structure must have been initialized by a previous call to <a href="https://msdn.microsoft.com/library/Ff545640(v=VS.85).aspx"><b>FsRtlAllocateFileLock</b></a> or <a href="https://msdn.microsoft.com/library/Ff546122(v=VS.85).aspx"><b>FsRtlInitializeFileLock</b></a>.</p>


### -param A2

<p>Pointer to the file object for the open file. The file object must have been created with GENERIC_READ or GENERIC_WRITE access to the file (or both). </p>


### -param A3

<p>Pointer to a variable that specifies the starting byte offset within the file of the range to be locked.</p>


### -param A4

<p>Pointer to a variable that specifies the length in bytes of the range to be locked.</p>


### -param A5

<p>Pointer to the process ID for the process requesting the byte-range lock.</p>


### -param A6

<p>The key to be assigned to the byte-range lock.</p>


### -param A7

<p>Boolean value specifying whether the lock request should fail if the lock cannot be granted immediately. If the caller can be put into a wait state until the request is granted, set <i>FailImmediately</i> to <b>FALSE</b>. If it cannot, set <i>FailImmediately</i> to <b>TRUE</b>. </p>


### -param A8

<p>Set to <b>TRUE</b> if an exclusive lock is requested, <b>FALSE</b> if a shared lock is requested.</p>


### -param A9

<p>Pointer to a caller-allocated IO_STATUS_BLOCK structure that receives status information about the lock request. </p>


### -param A10

<p>Optional pointer to a context to use when releasing the byte-range lock. </p>


### -param A11

<p>This parameter is obsolete, but is retained for compatibility with legacy drivers.</p>






## -remarks



The <b>FsRtlFastLock</b> macro causes the caller to acquire a byte-range lock on a region of the specified file.

A return value of <b>TRUE</b> indicates that the IO_STATUS_BLOCK structure pointed to by <i>Iosb</i> received status information about the lock operation. To examine the contents of this structure, use the NT_STATUS macro.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff545640">FsRtlAllocateFileLock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546122">FsRtlInitializeFileLock</a>
 

 

