---
UID: NF:ntifs._FSRTL_ADVANCED_FCB_HEADER.FsRtlFastUnlockAllByKey~r4
title: FsRtlFastUnlockAllByKey function
author: windows-driver-content
description: The FsRtlFastUnlockAllByKey routine releases all byte-range locks that were acquired by the specified process, with the specified key value, for a file.
old-location: ifsk\fsrtlfastunlockallbykey.htm
old-project: ifsk
ms.assetid: 57214e6a-cd29-4576-894a-9523ca3c7e7d
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: ntifs/FsRtlFastUnlockAllByKey, FsRtlFastUnlockAllByKey routine [Installable File System Drivers], ifsk.fsrtlfastunlockallbykey, FsRtlFastUnlockAllByKey, fsrtlref_193afe01-52f3-4dbc-8a33-bd058beb10ce.xml
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
-	FsRtlFastUnlockAllByKey
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# FsRtlFastUnlockAllByKey function


## -description


The <b>FsRtlFastUnlockAllByKey</b> routine releases all byte-range locks that were acquired by the specified process, with the specified key value, for a file. 


## -syntax


````
NTSTATUS FsRtlFastUnlockAllByKey(
  _In_     PFILE_LOCK   FileLock,
  _In_     PFILE_OBJECT FileObject,
  _In_     PEPROCESS    ProcessId,
  _In_     ULONG        Key,
  _In_opt_ PVOID        Context
);
````


## -parameters




### -param FileLock [in]

A pointer to the FILE_LOCK structure for the file. This structure must have been initialized by a previous call to <a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlallocatefilelock~r1.md">FsRtlAllocateFileLock</a> or <a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlinitializefilelock~r2.md">FsRtlInitializeFileLock</a>.


### -param FileObject [in]

A pointer to the file object for the file.


### -param ProcessId [in]

A pointer to the process ID for the process.


### -param Key [in]

The key value.


### -param Context [in, optional]

Optional context pointer to be used when completing IRPs. 


## -returns


<b>FsRtlFastUnlockAllByKey</b> returns STATUS_SUCCESS or an error status code such as STATUS_RANGE_NOT_LOCKED. 



## -remarks


After releasing the byte-range locks, <b>FsRtlFastUnlockAllByKey</b> completes any currently queued lock IRPs that can now be completed.



## -see-also

<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlinitializefilelock~r2.md">FsRtlInitializeFileLock</a>

<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlallocatefilelock~r1.md">FsRtlAllocateFileLock</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FsRtlFastUnlockAllByKey routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

