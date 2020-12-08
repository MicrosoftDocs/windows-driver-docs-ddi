---
UID: NF:ntifs.FsRtlNotifyInitializeSync
title: FsRtlNotifyInitializeSync function (ntifs.h)
description: The FsRtlNotifyInitializeSync routine allocates and initializes a synchronization object for a notify list.
old-location: ifsk\fsrtlnotifyinitializesync.htm
tech.root: ifsk
ms.date: 04/16/2018
keywords: ["FsRtlNotifyInitializeSync function"]
ms.keywords: FsRtlNotifyInitializeSync, FsRtlNotifyInitializeSync routine [Installable File System Drivers], fsrtlref_3a247139-1c76-4947-8e6f-a5beeae504cd.xml, ifsk.fsrtlnotifyinitializesync, ntifs/FsRtlNotifyInitializeSync
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
req.irql: <= APC_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - FsRtlNotifyInitializeSync
 - ntifs/FsRtlNotifyInitializeSync
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - FsRtlNotifyInitializeSync
---

# FsRtlNotifyInitializeSync function


## -description

The <b>FsRtlNotifyInitializeSync</b> routine allocates and initializes a synchronization object for a notify list.

## -parameters

### -param NotifySync 

[in]
A pointer to a location in which to return a pointer to the opaque synchronization object.

## -remarks

The system allocates the synchronization object from nonpaged pool. If a pool allocation failure occurs, <b>FsRtlNotifyInitializeSync</b> raises a STATUS_INSUFFICIENT_RESOURCES exception. To gain control if this pool allocation failure occurs, the driver should wrap the call to <b>FsRtlNotifyInitializeSync</b> in a <b>try-except</b> or <b>try-finally</b> statement.

Every successful call to <b>FsRtlNotifyInitializeSync</b> must be matched by a subsequent call to <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlnotifyuninitializesync">FsRtlNotifyUninitializeSync</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlnotifyuninitializesync">FsRtlNotifyUninitializeSync</a>
