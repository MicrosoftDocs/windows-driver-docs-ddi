---
UID: NF:ntifs._FSRTL_ADVANCED_FCB_HEADER.FsRtlInitializeOplock
title: FsRtlInitializeOplock function (ntifs.h)
description: FsRtlInitializeOplock initializes an opportunistic lock (oplock) pointer.
old-location: ifsk\fsrtlinitializeoplock.htm
tech.root: ifsk
ms.assetid: bfa6f6fd-ce50-40e0-9e98-81519260cc86
ms.date: 04/16/2018
ms.keywords: FsRtlInitializeOplock, FsRtlInitializeOplock function [Installable File System Drivers], fsrtlref_e9d22a89-79a8-4aae-9b5c-fca644d5f972.xml, ifsk.fsrtlinitializeoplock, ntifs/FsRtlInitializeOplock
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
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- FsRtlInitializeOplock
product:
- Windows
targetos: Windows
req.typenames: 
---

# FsRtlInitializeOplock function


## -description


<b>FsRtlInitializeOplock</b> initializes an opportunistic lock (oplock) pointer. 


## -parameters




### -param Oplock [in, out]

Caller-supplied pointer variable that receives the initialized opportunistic lock pointer. This variable must be initialized to <b>NULL</b> before the initial call to <b>FsRtlInitializeOplock</b>. 


## -returns



None 




## -remarks



File systems and filter drivers call <b>FsRtlInitializeOplock</b> to initialize an opaque opportunistic lock pointer. 

When the opportunistic lock pointer is no longer needed, it can be uninitialized by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff547328">FsRtlUninitializeOplock</a>. The uninitialized opportunistic lock pointer can then be initialized for reuse by calling <b>FsRtlInitializeOplock</b>. 

For detailed information about opportunistic locks, see the Microsoft Windows SDK documentation. 

Minifilters should call <a href="https://msdn.microsoft.com/library/windows/hardware/ff543289">FltInitializeOplock</a> instead of <b>FsRtlInitializeOplock</b>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff545462">FSCTL_OPBATCH_ACK_CLOSE_PENDING</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545468">FSCTL_OPLOCK_BREAK_ACKNOWLEDGE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545476">FSCTL_OPLOCK_BREAK_ACK_NO_2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545485">FSCTL_OPLOCK_BREAK_NOTIFY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545510">FSCTL_REQUEST_BATCH_OPLOCK</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545518">FSCTL_REQUEST_FILTER_OPLOCK</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545538">FSCTL_REQUEST_OPLOCK_LEVEL_1</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545546">FSCTL_REQUEST_OPLOCK_LEVEL_2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543289">FltInitializeOplock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545767">FsRtlCheckOplock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545825">FsRtlCurrentBatchOplock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547112">FsRtlOplockFsctrl</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547120">FsRtlOplockIsFastIoPossible</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547328">FsRtlUninitializeOplock</a>
 

 

