---
UID: NF:ntifs._FSRTL_ADVANCED_FCB_HEADER.FsRtlProcessFileLock~r2
title: FsRtlProcessFileLock function
description: The FsRtlProcessFileLock routine processes and completes an IRP for a file lock operation.
old-location: ifsk\fsrtlprocessfilelock.htm
tech.root: ifsk
ms.assetid: 370e9dfd-ef2f-4bba-a0ec-5ebc6fbecb7a
ms.date: 03/29/2018
ms.keywords: FsRtlProcessFileLock, FsRtlProcessFileLock routine [Installable File System Drivers], fsrtlref_93a3a663-fe0b-45c2-ab32-af4fe94b9697.xml, ifsk.fsrtlprocessfilelock, ntifs/FsRtlProcessFileLock
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
-	FsRtlProcessFileLock
product:
- Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# FsRtlProcessFileLock function


## -description


The <b>FsRtlProcessFileLock</b> routine processes and completes an IRP for a file lock operation.


## -parameters




### -param FileLock [in]

Pointer to the FILE_LOCK structure for the file. This structure must have been initialized by a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff545640">FsRtlAllocateFileLock</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff546122">FsRtlInitializeFileLock</a>.


### -param Irp [in]

Pointer to the IRP. Must be an IRP for a file-lock operation.


### -param Context [in, optional]

Optional context pointer to be used when completing IRPs.


## -returns



<b>FsRtlProcessFileLock</b> returns STATUS_SUCCESS or an error status code. Error status codes include the following:




## -remarks



<b>FsRtlProcessFileLock</b> performs the specified lock operation on behalf of the process associated with thread that originally requested the operation.

On Microsoft Windows XP and later, this is the process to which the thread is currently attached.

On Microsoft Windows 2000 and earlier, it is the process that created the thread.

Callers of <b>FsRtlProcessFileLock</b> relinquish control of the input IRP.

Minifilters must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff543427">FltProcessFileLock</a> instead of <b>FsRtlProcessFileLock</b>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff543427">FltProcessFileLock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545640">FsRtlAllocateFileLock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546122">FsRtlInitializeFileLock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549251">IRP_MJ_LOCK_CONTROL</a>
 

 

