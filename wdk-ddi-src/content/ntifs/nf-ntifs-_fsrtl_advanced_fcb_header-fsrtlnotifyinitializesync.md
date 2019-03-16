---
UID: NF:ntifs._FSRTL_ADVANCED_FCB_HEADER.FsRtlNotifyInitializeSync
title: FsRtlNotifyInitializeSync function (ntifs.h)
description: The FsRtlNotifyInitializeSync routine allocates and initializes a synchronization object for a notify list.
old-location: ifsk\fsrtlnotifyinitializesync.htm
tech.root: ifsk
ms.assetid: 7db82e70-3090-4526-ba10-792ccdbef660
ms.date: 04/16/2018
ms.keywords: FsRtlNotifyInitializeSync, FsRtlNotifyInitializeSync routine [Installable File System Drivers], fsrtlref_3a247139-1c76-4947-8e6f-a5beeae504cd.xml, ifsk.fsrtlnotifyinitializesync, ntifs/FsRtlNotifyInitializeSync
ms.topic: function
req.header: ntifs.h
req.include-header: FltKernel.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: This routine is available on Microsoft Windows 2000 and later versions of Windows operating systems.
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
- FsRtlNotifyInitializeSync
product:
- Windows
targetos: Windows
req.typenames: 
---

# FsRtlNotifyInitializeSync function


## -description


The <b>FsRtlNotifyInitializeSync</b> routine allocates and initializes a synchronization object for a notify list.


## -parameters




### -param NotifySync [in]

A pointer to a location in which to return a pointer to the opaque synchronization object.


## -returns



None




## -remarks



The system allocates the synchronization object from nonpaged pool. If a pool allocation failure occurs, <b>FsRtlNotifyInitializeSync</b> raises a STATUS_INSUFFICIENT_RESOURCES exception. To gain control if this pool allocation failure occurs, the driver should wrap the call to <b>FsRtlNotifyInitializeSync</b> in a <b>try-except</b> or <b>try-finally</b> statement.

Every successful call to <b>FsRtlNotifyInitializeSync</b> must be matched by a subsequent call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff547055">FsRtlNotifyUninitializeSync</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff547055">FsRtlNotifyUninitializeSync</a>
 

 

