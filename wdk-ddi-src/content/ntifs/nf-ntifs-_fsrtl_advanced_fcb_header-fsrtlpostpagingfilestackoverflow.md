---
UID: NF:ntifs.FsRtlPostPagingFileStackOverflow
title: FsRtlPostPagingFileStackOverflow function (ntifs.h)
description: The FsRtlPostPagingFileStackOverflow routine posts a paging file stack overflow item to the stack overflow thread.
old-location: ifsk\fsrtlpostpagingfilestackoverflow.htm
tech.root: ifsk
ms.assetid: 5054cc41-06af-48f0-b273-276bd639c16c
ms.date: 04/16/2018
keywords: ["FsRtlPostPagingFileStackOverflow function"]
ms.keywords: FsRtlPostPagingFileStackOverflow, FsRtlPostPagingFileStackOverflow routine [Installable File System Drivers], fsrtlref_167dd1d3-f49d-4393-9003-af16aa144e0b.xml, ifsk.fsrtlpostpagingfilestackoverflow, ntifs/FsRtlPostPagingFileStackOverflow
f1_keywords:
 - "ntifs/FsRtlPostPagingFileStackOverflow"
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
req.irql: <= DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- FsRtlPostPagingFileStackOverflow
product:
- Windows
targetos: Windows
req.typenames: 
dev_langs:
 - c++
ms.custom: RS5
---

# FsRtlPostPagingFileStackOverflow function


## -description


The <b>FsRtlPostPagingFileStackOverflow</b> routine posts a paging file stack overflow item to the stack overflow thread.


## -parameters




### -param Context [in]

A context pointer to pass to the stack overflow callback routine. 


### -param Event [in]

A pointer to a caller-allocated notification event to pass to the stack overflow callback routine. Must have been initialized as nonsignaled by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-keinitializeevent">KeInitializeEvent</a>.


### -param StackOverflowRoutine [in]

A pointer to a callback routine to be invoked when processing the request in the overflow thread.


## -remarks



A file system typically calls <b>FsRtlPostPagingFileStackOverflow</b> during a paging file I/O operation when the amount of remaining stack space returned by <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iogetremainingstacksize">IoGetRemainingStackSize</a> is below the file system's stack overflow read threshold. <b>FsRtlPostPagingFileStackOverflow</b> posts the paging I/O request to a special paging stack overflow work queue. When the paging I/O operation has been completed, the caller's <i>Event</i> is set to a signaled state. 


<div class="alert"><b>Note</b>  Warning: File system filter drivers must never call <b>FsRtlPostPagingFileStackOverflow</b>, because doing so can halt the forward progress of paging file I/O operations.</div>
<div> </div>





## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff546873">FsRtlIsPagingFile</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlpoststackoverflow">FsRtlPostStackOverflow</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iogetremainingstacksize">IoGetRemainingStackSize</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-keinitializeevent">KeInitializeEvent</a>
 

 

