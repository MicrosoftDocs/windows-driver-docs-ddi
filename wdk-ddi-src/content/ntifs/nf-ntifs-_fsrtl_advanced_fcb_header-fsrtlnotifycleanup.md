---
UID: NF:ntifs._FSRTL_ADVANCED_FCB_HEADER.FsRtlNotifyCleanup
title: FsRtlNotifyCleanup function
author: windows-driver-content
description: When the last handle to a file object is released, the FsRtlNotifyCleanup routine removes the file object's notify structure, if present, from the specified notify list.
old-location: ifsk\fsrtlnotifycleanup.htm
tech.root: ifsk
ms.assetid: 90cc2c3b-8fb2-4450-9c20-06e1e4d1fe47
ms.date: 04/16/2018
ms.keywords: FsRtlNotifyCleanup, FsRtlNotifyCleanup routine [Installable File System Drivers], fsrtlref_7b5eea13-55d3-48de-baf3-4e16fcc1a755.xml, ifsk.fsrtlnotifycleanup, ntifs/FsRtlNotifyCleanup
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
-	FsRtlNotifyCleanup
product:
-	Windows
targetos: Windows
req.typenames: 
---

# FsRtlNotifyCleanup function


## -description


When the last handle to a file object is released, the <b>FsRtlNotifyCleanup</b> routine removes the file object's notify structure, if present, from the specified notify list.


## -parameters




### -param NotifySync [in]

A pointer to an opaque synchronization object for <i>NotifyList</i>. 


### -param NotifyList [in]

A pointer to the head of a notify list. Each element in the list is an opaque notify structure.


### -param FsContext [in]

A unique value assigned by the file system to identify a notify structure as belonging to a particular file object.


## -returns



None




## -remarks



If a notify structure is found that matches <i>FsContext</i>, <b>FsRtlNotifyCleanup</b> completes all IRPs that are queued in the notify structure. When all the IRPs are completed, <b>FsRtlNotifyCleanup</b> removes the notify structure from the notify list and deallocates it.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff547010">FsRtlNotifyFilterChangeDirectory</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547018">FsRtlNotifyFilterReportChange</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547026">FsRtlNotifyFullChangeDirectory</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547041">FsRtlNotifyFullReportChange</a>
 

 

