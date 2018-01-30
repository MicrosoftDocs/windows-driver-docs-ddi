---
UID: NF:ntifs._FSRTL_ADVANCED_FCB_HEADER.FsRtlOplockIsFastIoPossible
title: FsRtlOplockIsFastIoPossible function
author: windows-driver-content
description: FsRtlOplockIsFastIoPossible checks a file's opportunistic lock (oplock) state to determine whether fast I/O can be performed on the file.
old-location: ifsk\fsrtloplockisfastiopossible.htm
old-project: ifsk
ms.assetid: ba482fbf-862c-48b4-b8f9-aaab6c5527ee
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: fsrtlref_94131dc4-e2ee-4ec0-92b9-39cd8a7d6e41.xml, rxprocs/FsRtlOplockIsFastIoPossible, FsRtlOplockIsFastIoPossible, FsRtlOplockIsFastIoPossible function [Installable File System Drivers], ifsk.fsrtloplockisfastiopossible
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
-	FsRtlOplockIsFastIoPossible
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# FsRtlOplockIsFastIoPossible function


## -description


<b>FsRtlOplockIsFastIoPossible</b> checks a file's opportunistic lock (oplock) state to determine whether fast I/O can be performed on the file. 


## -syntax


````
BOOLEAN FsRtlOplockIsFastIoPossible(
  _In_ POPLOCK Oplock
);
````


## -parameters




### -param Oplock [in]

Opaque opportunistic lock pointer for the file. This pointer must have been initialized by a previous call to <a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlinitializeoplock.md">FsRtlInitializeOplock</a>. 


## -returns


<b>FsRtlOplockIsFastIoPossible</b> returns <b>FALSE</b> if there are outstanding opportunistic locks on the file that prevent fast I/O from being performed; <b>TRUE</b> otherwise. 



## -remarks


<b>FsRtlOplockIsFastIoPossible</b> determines whether fast I/O can be performed on a file, according to the following conditions: 
<ul>
<li>
If the <i>Oplock</i> parameter is <b>NULL</b>, or if the value of *<i>Oplock</i> is <b>NULL</b>, there are no outstanding opportunistic locks on the file, and fast I/O can be performed on the file. 

</li>
<li>
If an exclusive opportunistic lock was granted for the file, but no oplock break is in progress, fast I/O can be performed on the file. 

</li>
</ul>For detailed information about opportunistic locks, see the Microsoft Windows SDK documentation. 

Minifilters should call <a href="..\fltkernel\nf-fltkernel-fltoplockisfastiopossible.md">FltOplockIsFastIoPossible</a> instead of <b>FsRtlOplockIsFastIoPossible</b>. 



## -see-also

<a href="..\fltkernel\nf-fltkernel-fltoplockisfastiopossible.md">FltOplockIsFastIoPossible</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff545462">FSCTL_OPBATCH_ACK_CLOSE_PENDING</a>

<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtluninitializeoplock.md">FsRtlUninitializeOplock</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff545485">FSCTL_OPLOCK_BREAK_NOTIFY</a>

<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlinitializeoplock.md">FsRtlInitializeOplock</a>

<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtloplockfsctrl~r2.md">FsRtlOplockFsctrl</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff545546">FSCTL_REQUEST_OPLOCK_LEVEL_2</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff545538">FSCTL_REQUEST_OPLOCK_LEVEL_1</a>

<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlcurrentbatchoplock.md">FsRtlCurrentBatchOplock</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff545510">FSCTL_REQUEST_BATCH_OPLOCK</a>

<a href="..\rxprocs\nf-rxprocs-fsrtlcheckoplock.md">FsRtlCheckOplock</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff545468">FSCTL_OPLOCK_BREAK_ACKNOWLEDGE</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff545476">FSCTL_OPLOCK_BREAK_ACK_NO_2</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff545518">FSCTL_REQUEST_FILTER_OPLOCK</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FsRtlOplockIsFastIoPossible function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

