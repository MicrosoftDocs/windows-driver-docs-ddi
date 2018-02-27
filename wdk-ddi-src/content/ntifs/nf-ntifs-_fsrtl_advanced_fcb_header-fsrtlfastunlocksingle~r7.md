---
UID: NF:ntifs._FSRTL_ADVANCED_FCB_HEADER.FsRtlFastUnlockSingle~r7
title: FsRtlFastUnlockSingle function
author: windows-driver-content
description: The FsRtlFastUnlockSingle routine releases a byte-range lock that was acquired by the specified process, with the specified key value, file offset, and length, for a file.
old-location: ifsk\fsrtlfastunlocksingle.htm
old-project: ifsk
ms.assetid: 8fd7aeea-f8b2-4f53-b4b6-65240ff0c7b6
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: FsRtlFastUnlockSingle, FsRtlFastUnlockSingle routine [Installable File System Drivers], fsrtlref_22b539f2-395b-4ecc-b182-36a1b8333290.xml, ifsk.fsrtlfastunlocksingle, ntifs/FsRtlFastUnlockSingle
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.irql: "<= APC_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	FsRtlFastUnlockSingle
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# FsRtlFastUnlockSingle function


## -description


The <b>FsRtlFastUnlockSingle</b> routine releases a byte-range lock that was acquired by the specified process, with the specified key value, file offset, and length, for a file. 


## -syntax


````
NTSTATUS FsRtlFastUnlockSingle(
  _In_     PFILE_LOCK              FileLock,
  _In_     PFILE_OBJECT            FileObject,
  _In_     LARGE_INTEGER UNALIGNED *FileOffset,
  _In_     PLARGE_INTEGER          Length,
  _In_     PEPROCESS               ProcessId,
  _In_     ULONG                   Key,
  _In_opt_ PVOID                   Context,
  _In_     BOOLEAN                 AlreadySynchronized
);
````


## -parameters




### -param FileLock [in]

A pointer to the FILE_LOCK structure for the file. This structure must have been initialized by a previous call to <a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlallocatefilelock~r1.md">FsRtlAllocateFileLock</a> or <a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlinitializefilelock~r2.md">FsRtlInitializeFileLock</a>.


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

<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlallocatefilelock~r1.md">FsRtlAllocateFileLock</a>



<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlinitializefilelock~r2.md">FsRtlInitializeFileLock</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FsRtlFastUnlockSingle routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

