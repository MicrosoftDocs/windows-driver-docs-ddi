---
UID: NF:ntifs._FSRTL_ADVANCED_FCB_HEADER.FsRtlPostPagingFileStackOverflow~r2
title: FsRtlPostPagingFileStackOverflow function
author: windows-driver-content
description: The FsRtlPostPagingFileStackOverflow routine posts a paging file stack overflow item to the stack overflow thread.
old-location: ifsk\fsrtlpostpagingfilestackoverflow.htm
old-project: ifsk
ms.assetid: 5054cc41-06af-48f0-b273-276bd639c16c
ms.author: windowsdriverdev
ms.date: 2/16/2018
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


## -syntax


````
VOID FsRtlPostPagingFileStackOverflow(
  _In_ PVOID                         Context,
  _In_ PKEVENT                       Event,
  _In_ PFSRTL_STACK_OVERFLOW_ROUTINE StackOverflowRoutine
);
````


## -parameters




### -param Context [in]

A context pointer to pass to the stack overflow callback routine. 


### -param Event [in]

A pointer to a caller-allocated notification event to pass to the stack overflow callback routine. Must have been initialized as nonsignaled by calling <a href="..\wdm\nf-wdm-keinitializeevent.md">KeInitializeEvent</a>.


### -param StackOverflowRoutine [in]

A pointer to a callback routine to be invoked when processing the request in the overflow thread.


## -returns



None




## -remarks



A file system typically calls <b>FsRtlPostPagingFileStackOverflow</b> during a paging file I/O operation when the amount of remaining stack space returned by <a href="..\wdm\nf-wdm-iogetremainingstacksize.md">IoGetRemainingStackSize</a> is below the file system's stack overflow read threshold. <b>FsRtlPostPagingFileStackOverflow</b> posts the paging I/O request to a special paging stack overflow work queue. When the paging I/O operation has been completed, the caller's <i>Event</i> is set to a signaled state. 


<div class="alert"><b>Note</b>  Warning: File system filter drivers must never call <b>FsRtlPostPagingFileStackOverflow</b>, because doing so can halt the forward progress of paging file I/O operations.</div>
<div> </div>





## -see-also

<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlpoststackoverflow~r2.md">FsRtlPostStackOverflow</a>



<a href="..\ntifs\nf-ntifs-fsrtlispagingfile.md">FsRtlIsPagingFile</a>



<a href="..\wdm\nf-wdm-keinitializeevent.md">KeInitializeEvent</a>



<a href="..\wdm\nf-wdm-iogetremainingstacksize.md">IoGetRemainingStackSize</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FsRtlPostPagingFileStackOverflow routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

