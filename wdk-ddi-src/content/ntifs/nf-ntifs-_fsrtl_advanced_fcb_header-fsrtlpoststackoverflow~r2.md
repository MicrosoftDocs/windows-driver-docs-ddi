---
UID: NF:ntifs._FSRTL_ADVANCED_FCB_HEADER.FsRtlPostStackOverflow~r2
title: FsRtlPostStackOverflow function
author: windows-driver-content
description: The FsRtlPostStackOverflow routine posts a stack overflow item to the stack overflow thread.
old-location: ifsk\fsrtlpoststackoverflow.htm
old-project: ifsk
ms.assetid: fbd6f3b5-ecf7-438e-8e28-a06eaa141fc3
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: FsRtlPostStackOverflow, FsRtlPostStackOverflow routine [Installable File System Drivers], fsrtlref_c2a888d0-ecfc-4b50-b6f0-753ef43375de.xml, ifsk.fsrtlpoststackoverflow, ntifs/FsRtlPostStackOverflow
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
-	FsRtlPostStackOverflow
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# FsRtlPostStackOverflow function


## -description


The <b>FsRtlPostStackOverflow</b> routine posts a stack overflow item to the stack overflow thread.


## -syntax


````
VOID FsRtlPostStackOverflow(
  _In_ PVOID                         Context,
  _In_ PKEVENT                       Event,
  _In_ PFSRTL_STACK_OVERFLOW_ROUTINE StackOverflowRoutine
);
````


## -parameters




### -param Context [in]

A context pointer to be passed to the stack overflow callback routine.


### -param Event [in]

A pointer to a caller-allocated notification event to pass to the stack overflow callback routine. Must have been initialized as nonsignaled by calling <a href="..\wdm\nf-wdm-keinitializeevent.md">KeInitializeEvent</a>.


### -param StackOverflowRoutine [in]

A pointer to a callback routine to be invoked when processing the request in the overflow thread.


## -returns



None




## -remarks



A file system typically calls <b>FsRtlPostStackOverflow</b> during a file I/O operation when the amount of remaining stack space returned by <a href="..\wdm\nf-wdm-iogetremainingstacksize.md">IoGetRemainingStackSize</a> is below the file system's stack overflow threshold for the operation. <b>FsRtlPostStackOverflow</b> posts the I/O request to a special stack overflow work queue. When the I/O operation has been completed, the caller's <i>Event</i> is set to a signaled state. 

File system filter drivers should use <a href="..\wdm\nf-wdm-ioqueueworkitem.md">IoQueueWorkItem</a> instead of <b>FsRtlPostStackOverflow</b>, because <b>IoQueueWorkItem</b> ensures that the device object that is associated with the specified work item is available for the processing of the work item. 

If a pool allocation failure occurs, <b>FsRtlPostStackOverflow</b> raises a STATUS_INSUFFICIENT_RESOURCES exception. To gain control if this pool allocation failure occurs, the driver should wrap the call to <b>FsRtlPostStackOverflow</b> in a <b>try-except</b> or <b>try-finally</b> statement.




## -see-also

<a href="..\wdm\nf-wdm-keinitializeevent.md">KeInitializeEvent</a>



<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlpostpagingfilestackoverflow~r2.md">FsRtlPostPagingFileStackOverflow</a>



<a href="..\wdm\nf-wdm-iogetremainingstacksize.md">IoGetRemainingStackSize</a>



<a href="..\wdm\nf-wdm-ioqueueworkitem.md">IoQueueWorkItem</a>



 

 


