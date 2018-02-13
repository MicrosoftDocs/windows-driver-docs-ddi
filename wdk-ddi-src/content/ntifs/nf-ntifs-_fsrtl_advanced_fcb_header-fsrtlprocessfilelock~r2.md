---
UID: NF:ntifs._FSRTL_ADVANCED_FCB_HEADER.FsRtlProcessFileLock~r2
title: FsRtlProcessFileLock function
author: windows-driver-content
description: The FsRtlProcessFileLock routine processes and completes an IRP for a file lock operation.
old-location: ifsk\fsrtlprocessfilelock.htm
old-project: ifsk
ms.assetid: 370e9dfd-ef2f-4bba-a0ec-5ebc6fbecb7a
ms.author: windowsdriverdev
ms.date: 2/7/2018
ms.keywords: FsRtlProcessFileLock, FsRtlProcessFileLock routine [Installable File System Drivers], ifsk.fsrtlprocessfilelock, fsrtlref_93a3a663-fe0b-45c2-ab32-af4fe94b9697.xml, ntifs/FsRtlProcessFileLock
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	FsRtlProcessFileLock
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# FsRtlProcessFileLock function


## -description


The <b>FsRtlProcessFileLock</b> routine processes and completes an IRP for a file lock operation.


## -syntax


````
NTSTATUS FsRtlProcessFileLock(
  _In_     PFILE_LOCK FileLock,
  _In_     PIRP       Irp,
  _In_opt_ PVOID      Context
);
````


## -parameters




### -param FileLock [in]

Pointer to the FILE_LOCK structure for the file. This structure must have been initialized by a previous call to <a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlallocatefilelock~r1.md">FsRtlAllocateFileLock</a> or <a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlinitializefilelock~r2.md">FsRtlInitializeFileLock</a>.


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

Minifilters must call <a href="..\fltkernel\nf-fltkernel-fltprocessfilelock.md">FltProcessFileLock</a> instead of <b>FsRtlProcessFileLock</b>. 




## -see-also

<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlinitializefilelock~r2.md">FsRtlInitializeFileLock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549251">IRP_MJ_LOCK_CONTROL</a>



<a href="..\fltkernel\nf-fltkernel-fltprocessfilelock.md">FltProcessFileLock</a>



<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlallocatefilelock~r1.md">FsRtlAllocateFileLock</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FsRtlProcessFileLock routine%20 RELEASE:%20(2/7/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

