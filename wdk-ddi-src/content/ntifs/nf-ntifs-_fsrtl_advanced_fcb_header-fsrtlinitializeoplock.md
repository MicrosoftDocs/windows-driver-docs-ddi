---
UID: NF:ntifs._FSRTL_ADVANCED_FCB_HEADER.FsRtlInitializeOplock
title: FsRtlInitializeOplock function
author: windows-driver-content
description: FsRtlInitializeOplock initializes an opportunistic lock (oplock) pointer.
old-location: ifsk\fsrtlinitializeoplock.htm
old-project: ifsk
ms.assetid: bfa6f6fd-ce50-40e0-9e98-81519260cc86
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , F, FsRtlInitializeOplock, FsRtlInitializeOplock function [Installable File System Drivers], I, O, R, a, c, e, fsrtlref_e9d22a89-79a8-4aae-9b5c-fca644d5f972.xml, i, ifsk.fsrtlinitializeoplock, k, l, n, ntifs/FsRtlInitializeOplock, o, p, s, t, z"
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
-	FsRtlInitializeOplock
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# FsRtlInitializeOplock function


## -description


<b>FsRtlInitializeOplock</b> initializes an opportunistic lock (oplock) pointer. 


## -syntax


````
VOID FsRtlInitializeOplock(
  _Inout_ POPLOCK Oplock
);
````


## -parameters




### -param Oplock [in, out]

Caller-supplied pointer variable that receives the initialized opportunistic lock pointer. This variable must be initialized to <b>NULL</b> before the initial call to <b>FsRtlInitializeOplock</b>. 


## -returns



None 




## -remarks



File systems and filter drivers call <b>FsRtlInitializeOplock</b> to initialize an opaque opportunistic lock pointer. 

When the opportunistic lock pointer is no longer needed, it can be uninitialized by calling <a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtluninitializeoplock.md">FsRtlUninitializeOplock</a>. The uninitialized opportunistic lock pointer can then be initialized for reuse by calling <b>FsRtlInitializeOplock</b>. 

For detailed information about opportunistic locks, see the Microsoft Windows SDK documentation. 

Minifilters should call <a href="..\fltkernel\nf-fltkernel-fltinitializeoplock.md">FltInitializeOplock</a> instead of <b>FsRtlInitializeOplock</b>. 




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff545476">FSCTL_OPLOCK_BREAK_ACK_NO_2</a>



<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlcurrentbatchoplock.md">FsRtlCurrentBatchOplock</a>



<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtluninitializeoplock.md">FsRtlUninitializeOplock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545462">FSCTL_OPBATCH_ACK_CLOSE_PENDING</a>



<a href="..\fltkernel\nf-fltkernel-fltinitializeoplock.md">FltInitializeOplock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545485">FSCTL_OPLOCK_BREAK_NOTIFY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545510">FSCTL_REQUEST_BATCH_OPLOCK</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545518">FSCTL_REQUEST_FILTER_OPLOCK</a>



<a href="..\rxprocs\nf-rxprocs-fsrtloplockisfastiopossible.md">FsRtlOplockIsFastIoPossible</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545538">FSCTL_REQUEST_OPLOCK_LEVEL_1</a>



<a href="..\rxprocs\nf-rxprocs-fsrtlcheckoplock.md">FsRtlCheckOplock</a>



<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtloplockfsctrl~r2.md">FsRtlOplockFsctrl</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545546">FSCTL_REQUEST_OPLOCK_LEVEL_2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545468">FSCTL_OPLOCK_BREAK_ACKNOWLEDGE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FsRtlInitializeOplock function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

