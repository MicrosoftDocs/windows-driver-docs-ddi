---
UID: NF:ntifs.FsRtlNotifyCleanup~r2
title: FsRtlNotifyCleanup function (ntifs.h)
description: When the last handle to a file object is released, the FsRtlNotifyCleanup routine removes the file object's notify structure, if present, from the specified notify list.
old-location: ifsk\fsrtlnotifycleanup.htm
tech.root: ifsk
ms.date: 03/29/2018
keywords: ["FsRtlNotifyCleanup function"]
ms.keywords: FsRtlNotifyCleanup, FsRtlNotifyCleanup routine [Installable File System Drivers], fsrtlref_7b5eea13-55d3-48de-baf3-4e16fcc1a755.xml, ifsk.fsrtlnotifycleanup, ntifs/FsRtlNotifyCleanup
f1_keywords:
 - "ntifs/FsRtlNotifyCleanup"
 - "FsRtlNotifyCleanup"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- FsRtlNotifyCleanup
targetos: Windows
req.typenames: TOKEN_TYPE
---

# FsRtlNotifyCleanup function


## -description


When the last handle to a file object is released, the <b>FsRtlNotifyCleanup</b> routine removes the file object's notify structure, if present, from the specified notify list.


## -parameters




### -param NotifySync 
[in]
A pointer to an opaque synchronization object for <i>NotifyList</i>.


### -param NotifyList 
[in]
A pointer to the head of a notify list. Each element in the list is an opaque notify structure.


### -param FsContext 
[in]
A unique value assigned by the file system to identify a notify structure as belonging to a particular file object.


## -returns



None




## -remarks



If a notify structure is found that matches <i>FsContext</i>, <b>FsRtlNotifyCleanup</b> completes all IRPs that are queued in the notify structure. When all the IRPs are completed, <b>FsRtlNotifyCleanup</b> removes the notify structure from the notify list and deallocates it.




## -see-also




<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlnotifyfilterchangedirectory">FsRtlNotifyFilterChangeDirectory</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlnotifyfilterreportchange">FsRtlNotifyFilterReportChange</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlnotifyfullchangedirectory">FsRtlNotifyFullChangeDirectory</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlnotifyfullreportchange">FsRtlNotifyFullReportChange</a>
 

 
