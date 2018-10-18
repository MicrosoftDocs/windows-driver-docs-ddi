---
UID: NF:ntifs._FSRTL_ADVANCED_FCB_HEADER.FsRtlFastUnlockAll
title: FsRtlFastUnlockAll function
author: windows-driver-content
description: The FsRtlFastUnlockAll routine releases all byte-range locks that were acquired by the specified process for a file.
old-location: ifsk\fsrtlfastunlockall.htm
tech.root: ifsk
ms.assetid: 5004fb3c-f2e3-4663-9b95-7fb7bb38364d
ms.date: 4/16/2018
ms.keywords: FsRtlFastUnlockAll, FsRtlFastUnlockAll routine [Installable File System Drivers], fsrtlref_713fc415-f52e-4e0f-8806-02f44fb9b3f4.xml, ifsk.fsrtlfastunlockall, ntifs/FsRtlFastUnlockAll
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
-	FsRtlFastUnlockAll
product:
-	Windows
targetos: Windows
req.typenames: 
---

# FsRtlFastUnlockAll function


## -description


The <b>FsRtlFastUnlockAll</b> routine releases all byte-range locks that were acquired by the specified process for a file. 


## -parameters




### -param FileLock [in]

Pointer to the FILE_LOCK structure for the file. This structure must have been initialized by a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff545640">FsRtlAllocateFileLock</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff546122">FsRtlInitializeFileLock</a>.


### -param FileObject [in]

Pointer to the file object for the file.


### -param ProcessId [in]

Pointer to the process ID for the process.


### -param Context [in, optional]

Optional context pointer to be used when completing IRPs. 


## -returns



<b>FsRtlFastUnlockAll</b> returns STATUS_SUCCESS or an error status code such as STATUS_RANGE_NOT_LOCKED. 




## -remarks



After releasing the byte-range locks, <b>FsRtlFastUnlockAll</b> completes any currently queued lock IRPs that can now be completed.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff545640">FsRtlAllocateFileLock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546122">FsRtlInitializeFileLock</a>
 

 

