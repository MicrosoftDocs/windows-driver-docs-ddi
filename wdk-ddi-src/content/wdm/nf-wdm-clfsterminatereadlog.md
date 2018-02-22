---
UID: NF:wdm.ClfsTerminateReadLog
title: ClfsTerminateReadLog function
author: windows-driver-content
description: The ClfsTerminateReadLog routine invalidates a specified read context after freeing resources associated with the context.
old-location: kernel\clfsterminatereadlog.htm
old-project: kernel
ms.assetid: 47633903-0314-4d50-8dd5-ddb0eb934e09
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: wdm/ClfsTerminateReadLog, kernel.clfsterminatereadlog, ClfsTerminateReadLog routine [Kernel-Mode Driver Architecture], ClfsTerminateReadLog, Clfs_691e308a-56d7-498f-af11-8908cc13b1b7.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Server 2003 R2, Windows Vista, and later versions of Windows.
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
req.lib: Clfs.lib
req.dll: Clfs.sys
req.irql: "<= APC_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	Clfs.sys
-	Ext-MS-Win-fs-clfs-l1-1-0.dll
apiname:
-	ClfsTerminateReadLog
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# ClfsTerminateReadLog function


## -description


The <b>ClfsTerminateReadLog</b> routine invalidates a specified read context after freeing resources associated with the context.


## -syntax


````
NTSTATUS ClfsTerminateReadLog(
  _In_ PVOID pvCursorContext
);
````


## -parameters




### -param pvCursorContext [in]

A pointer to the read context to be invalidated. The caller previously obtained this pointer by calling <a href="..\wdm\nf-wdm-clfsreadlogrecord.md">ClfsReadLogRecord</a> or <a href="..\wdm\nf-wdm-clfsreadrestartarea.md">ClfsReadRestartArea</a>.


## -returns



<b>ClfsTerminateReadLog</b> returns STATUS_SUCCESS if it succeeds; otherwise, it returns one of the error codes defined in Ntstatus.h.




## -remarks



<div class="alert"><b>Warning</b>    Failure to call this routine can lead to memory leaks, premature exhaustion of log I/O blocks, and increased frequency of log flushes.<p class="note">Attempting to use <i>pvCursorContext</i> after it is freed is equivalent to accessing freed memory and can lead to unexpected behavior.

</div>
<div> </div>
For an explanation of CLFS concepts and terminology, see <a href="https://msdn.microsoft.com/a9685648-b08c-48ca-b020-e683068f2ea2">Common Log File System</a>. 




## -see-also

<a href="..\wdm\nf-wdm-clfsreadrestartarea.md">ClfsReadRestartArea</a>



<a href="..\wdm\nf-wdm-clfsreadlogrecord.md">ClfsReadLogRecord</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ClfsTerminateReadLog routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

