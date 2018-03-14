---
UID: NF:ntifs._FSRTL_ADVANCED_FCB_HEADER.FsRtlUninitializeOplock
title: FsRtlUninitializeOplock function
author: windows-driver-content
description: FsRtlUninitializeOplock uninitializes an opportunistic lock (oplock) pointer.
old-location: ifsk\fsrtluninitializeoplock.htm
old-project: ifsk
ms.assetid: 4891a13c-0c5c-4a38-8e1d-539f7675cccc
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: FsRtlUninitializeOplock, FsRtlUninitializeOplock function [Installable File System Drivers], fsrtlref_b7e633fd-d91a-4db6-a1b6-2c695579a903.xml, ifsk.fsrtluninitializeoplock, ntifs/FsRtlUninitializeOplock
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

<a href="https://msdn.microsoft.com/library/windows/hardware/ff545518">FSCTL_REQUEST_FILTER_OPLOCK</a>



<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlinitializeoplock.md">FsRtlInitializeOplock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545538">FSCTL_REQUEST_OPLOCK_LEVEL_1</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545468">FSCTL_OPLOCK_BREAK_ACKNOWLEDGE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545476">FSCTL_OPLOCK_BREAK_ACK_NO_2</a>



<a href="..\rxprocs\nf-rxprocs-fsrtloplockisfastiopossible.md">FsRtlOplockIsFastIoPossible</a>



<a href="..\fltkernel\nf-fltkernel-fltuninitializeoplock.md">FltUninitializeOplock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545462">FSCTL_OPBATCH_ACK_CLOSE_PENDING</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545546">FSCTL_REQUEST_OPLOCK_LEVEL_2</a>



<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlcurrentbatchoplock.md">FsRtlCurrentBatchOplock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545510">FSCTL_REQUEST_BATCH_OPLOCK</a>



<a href="..\rxprocs\nf-rxprocs-fsrtlcheckoplock.md">FsRtlCheckOplock</a>



<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtloplockfsctrl~r2.md">FsRtlOplockFsctrl</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545485">FSCTL_OPLOCK_BREAK_NOTIFY</a>



 

 


