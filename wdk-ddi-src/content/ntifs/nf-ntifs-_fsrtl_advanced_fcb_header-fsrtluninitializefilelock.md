---
UID: NF:ntifs._FSRTL_ADVANCED_FCB_HEADER.FsRtlUninitializeFileLock
title: FsRtlUninitializeFileLock function
author: windows-driver-content
description: The FsRtlUninitializeFileLock routine uninitializes a FILE_LOCK structure.
old-location: ifsk\fsrtluninitializefilelock.htm
old-project: ifsk
ms.assetid: e92763e2-a15a-41cd-9f69-ec759b254929
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: FsRtlUninitializeFileLock, FsRtlUninitializeFileLock routine [Installable File System Drivers], fsrtlref_d78c3eae-751c-4440-8915-455454886201.xml, ifsk.fsrtluninitializefilelock, ntifs/FsRtlUninitializeFileLock
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
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	FsRtlUninitializeFileLock
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# FsRtlUninitializeFileLock function


## -description


The <b>FsRtlUninitializeFileLock</b> routine uninitializes a FILE_LOCK structure.


## -syntax


````
VOID FsRtlUninitializeFileLock(
  _In_ PFILE_LOCK FileLock
);
````


## -parameters




### -param FileLock [in]

Pointer to the FILE_LOCK structure for the file. This structure must have been initialized by a previous call to <a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlallocatefilelock~r1.md">FsRtlAllocateFileLock</a> or <a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlinitializefilelock~r2.md">FsRtlInitializeFileLock</a>.


## -returns



None




## -remarks



<b>FsRtlUninitializeFileLock</b> uninitializes an initialized FILE_LOCK structure and completes any outstanding <a href="https://msdn.microsoft.com/library/windows/hardware/ff549251">IRP_MJ_LOCK_CONTROL</a> requests. The uninitialized FILE_LOCK structure can be initialized for reuse by a subsequent call to <a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlinitializefilelock~r2.md">FsRtlInitializeFileLock</a>.

<b>FsRtlUninitializeFileLock</b> can be used to uninitialize a FILE_LOCK structure that was initialized by a previous call to <a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlallocatefilelock~r1.md">FsRtlAllocateFileLock</a> or <a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlinitializefilelock~r2.md">FsRtlInitializeFileLock</a>. Do not use <b>FsRtlUninitializeFileLock</b> for such a FILE_LOCK structure unless the structure is to be initialized for reuse. It is a programming error to call <b>FsRtlFreeFileLock</b> for an uninitialized FILE_LOCK structure.

Minifilters must call <a href="..\fltkernel\nf-fltkernel-fltuninitializefilelock.md">FltUninitializeFileLock</a> instead of <b>FsRtlUninitializeFileLock</b>. 




## -see-also

<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlinitializefilelock~r2.md">FsRtlInitializeFileLock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549251">IRP_MJ_LOCK_CONTROL</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551032">PCOMPLETE_LOCK_IRP_ROUTINE</a>



<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlallocatefilelock~r1.md">FsRtlAllocateFileLock</a>



<a href="..\fltkernel\nf-fltkernel-fltuninitializefilelock.md">FltUninitializeFileLock</a>



 

 


