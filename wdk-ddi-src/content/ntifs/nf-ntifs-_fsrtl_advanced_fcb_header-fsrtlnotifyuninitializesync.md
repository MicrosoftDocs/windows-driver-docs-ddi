---
UID: NF:ntifs.FsRtlNotifyUninitializeSync
title: FsRtlNotifyUninitializeSync function (ntifs.h)
description: The FsRtlNotifyUninitializeSync routine deallocates the synchronization object for a notify list.
old-location: ifsk\fsrtlnotifyuninitializesync.htm
tech.root: ifsk
ms.date: 04/16/2018
keywords: ["FsRtlNotifyUninitializeSync function"]
ms.keywords: FsRtlNotifyUninitializeSync, FsRtlNotifyUninitializeSync routine [Installable File System Drivers], fsrtlref_bb1d0439-691c-4a2d-8d0f-750f26d75995.xml, ifsk.fsrtlnotifyuninitializesync, ntifs/FsRtlNotifyUninitializeSync
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
 - FsRtlNotifyUninitializeSync
 - ntifs/FsRtlNotifyUninitializeSync
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - FsRtlNotifyUninitializeSync
---

# FsRtlNotifyUninitializeSync function


## -description

The <b>FsRtlNotifyUninitializeSync</b> routine deallocates the synchronization object for a notify list.

## -parameters

### -param NotifySync 

[in]
A pointer to a location that contains a pointer to the opaque synchronization object.

## -remarks

The <b>FsRtlNotifyUninitializeSync</b> routine deallocates an opaque synchronization object that was allocated by an earlier call to <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlnotifyinitializesync">FsRtlNotifyInitializeSync</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlnotifyinitializesync">FsRtlNotifyInitializeSync</a>
