---
UID: NF:ntifs._FSRTL_ADVANCED_FCB_HEADER.FsRtlInitializeFileLock~r2
title: FsRtlInitializeFileLock function
author: windows-driver-content
description: The FsRtlInitializeFileLock routine initializes a FILE_LOCK structure.
old-location: ifsk\fsrtlinitializefilelock.htm
old-project: ifsk
ms.assetid: 0a476cd8-b0e6-4faa-bb97-3647a88ecded
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: ntifs/FsRtlInitializeFileLock, FsRtlInitializeFileLock routine [Installable File System Drivers], fsrtlref_227dc998-43e4-427b-afe5-6d26ff5d1c36.xml, ifsk.fsrtlinitializefilelock, FsRtlInitializeFileLock
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
req.irql: <= APC_LEVEL
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	DllExport
apilocation: 
-	NtosKrnl.exe
apiname: 
-	FsRtlInitializeFileLock
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# FsRtlInitializeFileLock function


## -description


The <b>FsRtlInitializeFileLock</b> routine initializes a FILE_LOCK structure.


## -syntax


````
VOID FsRtlInitializeFileLock(
  _In_     PFILE_LOCK                 FileLock,
  _In_opt_ PCOMPLETE_LOCK_IRP_ROUTINE CompleteLockIrpRoutine,
  _In_opt_ PUNLOCK_ROUTINE            UnlockRoutine
);
````


## -parameters




### -param FileLock [in]

Pointer to an uninitialized FILE_LOCK structure. 


### -param CompleteLockIrpRoutine [in, optional]

Pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff551032">PCOMPLETE_LOCK_IRP_ROUTINE</a>-typed callback routine to be called when an <a href="https://msdn.microsoft.com/library/windows/hardware/ff549251">IRP_MJ_LOCK_CONTROL</a> request is completed. This parameter is optional and can be <b>NULL</b>. 


### -param UnlockRoutine [in, optional]

Pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff551951">PUNLOCK_ROUTINE</a>-typed callback routine to be called when the byte range is unlocked. This parameter is optional and can be <b>NULL</b>. 


## -returns


None



## -remarks


<b>FsRtlInitializeFileLock</b> initializes an uninitialized FILE_LOCK structure. 

It is a programming error to call <b>FsRtlInitializeFileLock</b> for a FILE_LOCK structure that has already been initialized by <b>FsRtlInitializeFileLock</b> or <a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlallocatefilelock~r1.md">FsRtlAllocateFileLock</a>, unless the structure has been uninitialized by a subsequent call to <a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtluninitializefilelock.md">FsRtlUninitializeFileLock</a>.

Once initialized, the FILE_LOCK structure can be used to lock a byte range in a file by calling <a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlprocessfilelock~r2.md">FsRtlProcessFileLock</a> or <a href="..\ntifs\nf-ntifs-fsrtlfastlock.md">FsRtlFastLock</a>. <b>FsRtlProcessFileLock</b> processes lock IRPs. <b>FsRtlFastLock</b> performs non-IRP locking.

When the FILE_LOCK structure is no longer needed, it can be uninitialized by calling <a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtluninitializefilelock.md">FsRtlUninitializeFileLock</a>. The uninitialized FILE_LOCK structure can then be initialized for reuse by calling <b>FsRtlInitializeFileLock</b>.

Minifilters must call <a href="..\fltkernel\nf-fltkernel-fltinitializefilelock.md">FltInitializeFileLock</a> instead of <b>FsRtlInitializeFileLock</b>. 



## -see-also

<a href="..\ntifs\nf-ntifs-fsrtlaretherecurrentfilelocks.md">FsRtlAreThereCurrentFileLocks</a>

<a href="..\fltkernel\nf-fltkernel-fltinitializefilelock.md">FltInitializeFileLock</a>

<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtluninitializefilelock.md">FsRtlUninitializeFileLock</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff551951">PUNLOCK_ROUTINE</a>

<a href="..\wdm\nf-wdm-iocompleterequest.md">IoCompleteRequest</a>

<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlallocatefilelock~r1.md">FsRtlAllocateFileLock</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff551032">PCOMPLETE_LOCK_IRP_ROUTINE</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff549251">IRP_MJ_LOCK_CONTROL</a>

<a href="..\ntifs\nf-ntifs-fsrtlfastlock.md">FsRtlFastLock</a>

<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlprocessfilelock~r2.md">FsRtlProcessFileLock</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FsRtlInitializeFileLock routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

