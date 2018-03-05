---
UID: NF:ntifs._FSRTL_ADVANCED_FCB_HEADER.FsRtlFreeFileLock
title: FsRtlFreeFileLock function
author: windows-driver-content
description: The FsRtlFreeFileLock routine uninitializes and frees a file lock structure.
old-location: ifsk\fsrtlfreefilelock.htm
old-project: ifsk
ms.assetid: 191a7964-4359-4b7f-8760-74f537b0737f
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: FsRtlFreeFileLock, FsRtlFreeFileLock routine [Installable File System Drivers], fsrtlref_112afa00-3370-4671-ad22-0743f8dd1c52.xml, ifsk.fsrtlfreefilelock, ntifs/FsRtlFreeFileLock
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: This routine is available on Microsoft Windows 2000 and later.
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	FsRtlFreeFileLock
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# FsRtlFreeFileLock function


## -description


The <b>FsRtlFreeFileLock</b> routine uninitializes and frees a file lock structure. 


## -syntax


````
VOID FsRtlFreeFileLock(
  _In_ PFILE_LOCK FileLock
);
````


## -parameters




### -param FileLock [in]

Pointer to the FILE_LOCK structure. This structure must have been allocated by a previous call to <b>FsRtlAllocateFileLock</b>.


## -returns



None




## -remarks



<b>FsRtlFreeFileLock</b> should be used only for file locks that were allocated and initialized by <b>FsRtlAllocateFileLock</b>.

It is a programming error to call <b>FsRtlFreeFileLock</b> for a FILE_LOCK structure that has already been uninitialized by a call to <a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtluninitializefilelock.md">FsRtlUninitializeFileLock</a>.

Minifilters must call <a href="..\fltkernel\nf-fltkernel-fltfreefilelock.md">FltFreeFileLock</a> instead of <b>FsRtlFreeFileLock</b>. 




## -see-also

<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlfastunlockallbykey~r4.md">FsRtlFastUnlockAllByKey</a>



<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlchecklockforreadaccess~r1.md">FsRtlCheckLockForReadAccess</a>



<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlinitializefilelock~r2.md">FsRtlInitializeFileLock</a>



<a href="..\ntifs\nf-ntifs-fsrtlaretherecurrentfilelocks.md">FsRtlAreThereCurrentFileLocks</a>



<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlfastunlocksingle~r7.md">FsRtlFastUnlockSingle</a>



<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlchecklockforwriteaccess~r1.md">FsRtlCheckLockForWriteAccess</a>



<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlfastchecklockforread~r5.md">FsRtlFastCheckLockForRead</a>



<a href="..\fltkernel\nf-fltkernel-fltfreefilelock.md">FltFreeFileLock</a>



<a href="..\ntifs\nf-ntifs-fsrtlfastlock.md">FsRtlFastLock</a>



<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtluninitializefilelock.md">FsRtlUninitializeFileLock</a>



<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlprocessfilelock~r2.md">FsRtlProcessFileLock</a>



<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlgetnextfilelock~r1.md">FsRtlGetNextFileLock</a>



<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlfastunlockall~r3.md">FsRtlFastUnlockAll</a>



<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlfastchecklockforwrite~r5.md">FsRtlFastCheckLockForWrite</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FsRtlFreeFileLock routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

