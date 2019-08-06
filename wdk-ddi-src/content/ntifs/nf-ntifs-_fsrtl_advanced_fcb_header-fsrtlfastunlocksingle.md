---
UID: NF:ntifs.FsRtlFastUnlockSingle
title: FsRtlFastUnlockSingle function (ntifs.h)
description: The FsRtlFastUnlockSingle routine releases a byte-range lock that was acquired by the specified process, with the specified key value, file offset, and length, for a file.
old-location: ifsk\fsrtlfastunlocksingle.htm
tech.root: ifsk
ms.assetid: 8fd7aeea-f8b2-4f53-b4b6-65240ff0c7b6
ms.date: 04/16/2018
ms.keywords: FsRtlFastUnlockSingle, FsRtlFastUnlockSingle routine [Installable File System Drivers], fsrtlref_22b539f2-395b-4ecc-b182-36a1b8333290.xml, ifsk.fsrtlfastunlocksingle, ntifs/FsRtlFastUnlockSingle
ms.topic: function
f1_keywords:
 - "ntifs/FsRtlFastUnlockSingle"
req.header: ntifs.h
req.include-header: FltKernel.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Microsoft Windows 2000 and later.
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
req.irql: <= APC_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- FsRtlFastUnlockSingle
product:
- Windows
targetos: Windows
req.typenames: 
ms.custom: RS5
---

# FsRtlFastUnlockSingle function


## -description


The <b>FsRtlFastUnlockSingle</b> routine releases a byte-range lock that was acquired by the specified process, with the specified key value, file offset, and length, for a file. 


## -parameters




### -param FileLock [in]

A pointer to the FILE_LOCK structure for the file. This structure must have been initialized by a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlallocatefilelock">FsRtlAllocateFileLock</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlinitializefilelock">FsRtlInitializeFileLock</a>.


### -param FileObject [in]

A pointer to the file object for the file.


### -param FileOffset [in]

A pointer to a variable that specifies the starting byte offset within the file of the range to be unlocked.


### -param Length [in]

A pointer to a variable that specifies the length, in bytes, of the range to be unlocked.


### -param ProcessId [in]

A pointer to the process ID for the process.


### -param Key [in]

The key for the byte-range lock.


### -param Context [in, optional]

An optional context pointer to be used when completing IRPs. 


### -param AlreadySynchronized [in]

This parameter is obsolete, but is retained for compatibility with legacy drivers.


## -returns



The <b>FsRtlFastUnlockSingle</b> routine returns STATUS_SUCCESS or an error status code such as STATUS_RANGE_NOT_LOCKED. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlallocatefilelock">FsRtlAllocateFileLock</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlinitializefilelock">FsRtlInitializeFileLock</a>
 

 

