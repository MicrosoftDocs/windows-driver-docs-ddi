---
UID: NF:ntifs.FsRtlNotifyCleanupAll~r1
title: FsRtlNotifyCleanupAll function (ntifs.h)
description: The FsRtlNotifyCleanupAll routine removes all members of the specified notification list.
old-location: ifsk\fsrtlnotifycleanupall.htm
tech.root: ifsk
ms.assetid: 850728bd-6758-4c21-9bfd-10a0f3d006d6
ms.date: 03/29/2018
keywords: ["FsRtlNotifyCleanupAll function"]
ms.keywords: FsRtlNotifyCleanupAll, FsRtlNotifyCleanupAll routine [Installable File System Drivers], fsrtlref_f0eea2f1-9bc9-41e1-843c-a69b3e63f452.xml, ifsk.fsrtlnotifycleanupall, ntifs/FsRtlNotifyCleanupAll
f1_keywords:
 - "ntifs/FsRtlNotifyCleanupAll"
 - "FsRtlNotifyCleanupAll"
req.header: ntifs.h
req.include-header: FltKernel.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later version of the Windows operating system.
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
req.irql: <=APC_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- FsRtlNotifyCleanupAll
product:
- Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# FsRtlNotifyCleanupAll function


## -description


The <b>FsRtlNotifyCleanupAll</b> routine removes all members of the specified notification list.


## -parameters




### -param NotifySync [in]

A pointer to the opaque synchronization object for <i>NotifyList</i>.


### -param NotifyList [in]

A pointer to the head of the notify list to be cleaned up. Each element in the list is an opaque notify structure.


## -returns



None




## -remarks



For each entry in the <i>NotifyList</i> list, <b>FsRtlNotifyCleanupAll</b> completes all pending IRPs. Then the routine removes the entry from the list and deallocates the entry.

Because a notify list is typically associated with a volume, the <b>FsRtlNotifyCleanupAll</b> routine can be used to complete all the IRP requests for the volume.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlnotifycleanup">FsRtlNotifyCleanup</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlnotifyfilterchangedirectory">FsRtlNotifyFilterChangeDirectory</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlnotifyfilterreportchange">FsRtlNotifyFilterReportChange</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlnotifyfullchangedirectory">FsRtlNotifyFullChangeDirectory</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlnotifyfullreportchange">FsRtlNotifyFullReportChange</a>
 

 

