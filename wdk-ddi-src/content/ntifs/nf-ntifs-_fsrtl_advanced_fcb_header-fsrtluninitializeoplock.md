---
UID: NF:ntifs._FSRTL_ADVANCED_FCB_HEADER.FsRtlUninitializeOplock
title: FsRtlUninitializeOplock function
author: windows-driver-content
description: FsRtlUninitializeOplock uninitializes an opportunistic lock (oplock) pointer.
old-location: ifsk\fsrtluninitializeoplock.htm
old-project: ifsk
ms.assetid: 4891a13c-0c5c-4a38-8e1d-539f7675cccc
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: FsRtlUninitializeOplock function [Installable File System Drivers], FsRtlUninitializeOplock, ntifs/FsRtlUninitializeOplock, ifsk.fsrtluninitializeoplock, fsrtlref_b7e633fd-d91a-4db6-a1b6-2c695579a903.xml
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
-	FsRtlUninitializeOplock
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# FsRtlUninitializeOplock function


## -description


<b>FsRtlUninitializeOplock</b> uninitializes an opportunistic lock (oplock) pointer. 


## -syntax


````
VOID FsRtlUninitializeOplock(
  _Inout_ POPLOCK Oplock
);
````


## -parameters




### -param Oplock [in, out]

Opaque opportunistic lock pointer. This pointer must have been initialized by a previous call to <a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlinitializeoplock.md">FsRtlInitializeOplock</a>. 


## -returns


None 



## -remarks


File systems and filter drivers call <b>FsRtlUninitializeOplock</b> to uninitialize an initialized opportunistic lock (oplock) pointer. The uninitialized oplock pointer can be initialized for reuse by calling <a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlinitializeoplock.md">FsRtlInitializeOplock</a>. 

For detailed information about opportunistic locks, see the Microsoft Windows SDK documentation. 

Minifilters should call <a href="..\fltkernel\nf-fltkernel-fltuninitializeoplock.md">FltUninitializeOplock</a> instead of <b>FsRtlUninitializeOplock</b>. 



## -see-also

<a href="..\rxprocs\nf-rxprocs-fsrtlcheckoplock.md">FsRtlCheckOplock</a>

<a href="..\fltkernel\nf-fltkernel-fltuninitializeoplock.md">FltUninitializeOplock</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff545510">FSCTL_REQUEST_BATCH_OPLOCK</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff545476">FSCTL_OPLOCK_BREAK_ACK_NO_2</a>

<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlinitializeoplock.md">FsRtlInitializeOplock</a>

<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlcurrentbatchoplock.md">FsRtlCurrentBatchOplock</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff545538">FSCTL_REQUEST_OPLOCK_LEVEL_1</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff545485">FSCTL_OPLOCK_BREAK_NOTIFY</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff545462">FSCTL_OPBATCH_ACK_CLOSE_PENDING</a>

<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtloplockfsctrl~r2.md">FsRtlOplockFsctrl</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff545546">FSCTL_REQUEST_OPLOCK_LEVEL_2</a>

<a href="..\rxprocs\nf-rxprocs-fsrtloplockisfastiopossible.md">FsRtlOplockIsFastIoPossible</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff545468">FSCTL_OPLOCK_BREAK_ACKNOWLEDGE</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff545518">FSCTL_REQUEST_FILTER_OPLOCK</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FsRtlUninitializeOplock function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

