---
UID: NF:ntifs._FSRTL_ADVANCED_FCB_HEADER.FsRtlPostPagingFileStackOverflow~r2
title: FsRtlPostPagingFileStackOverflow function
author: windows-driver-content
description: The FsRtlPostPagingFileStackOverflow routine posts a paging file stack overflow item to the stack overflow thread.
old-location: ifsk\fsrtlpostpagingfilestackoverflow.htm
old-project: ifsk
ms.assetid: 5054cc41-06af-48f0-b273-276bd639c16c
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: FsRtlPostPagingFileStackOverflow, FsRtlPostPagingFileStackOverflow routine [Installable File System Drivers], fsrtlref_167dd1d3-f49d-4393-9003-af16aa144e0b.xml, ifsk.fsrtlpostpagingfilestackoverflow, ntifs/FsRtlPostPagingFileStackOverflow
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	FsRtlPostPagingFileStackOverflow
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# FsRtlPostPagingFileStackOverflow function


## -description


The <b>FsRtlPostPagingFileStackOverflow</b> routine posts a paging file stack overflow item to the stack overflow thread.


## -parameters




### -param Context [in]

A context pointer to pass to the stack overflow callback routine. 


### -param Event [in]

A pointer to a caller-allocated notification event to pass to the stack overflow callback routine. Must have been initialized as nonsignaled by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff552137">KeInitializeEvent</a>.


### -param StackOverflowRoutine [in]

A pointer to a callback routine to be invoked when processing the request in the overflow thread.


## -returns



None




## -remarks



A file system typically calls <b>FsRtlPostPagingFileStackOverflow</b> during a paging file I/O operation when the amount of remaining stack space returned by <a href="https://msdn.microsoft.com/library/windows/hardware/ff549286">IoGetRemainingStackSize</a> is below the file system's stack overflow read threshold. <b>FsRtlPostPagingFileStackOverflow</b> posts the paging I/O request to a special paging stack overflow work queue. When the paging I/O operation has been completed, the caller's <i>Event</i> is set to a signaled state. 


<div class="alert"><b>Note</b>  Warning: File system filter drivers must never call <b>FsRtlPostPagingFileStackOverflow</b>, because doing so can halt the forward progress of paging file I/O operations.</div>
<div> </div>





## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff546873">FsRtlIsPagingFile</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547156">FsRtlPostStackOverflow</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549286">IoGetRemainingStackSize</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552137">KeInitializeEvent</a>
 

 

