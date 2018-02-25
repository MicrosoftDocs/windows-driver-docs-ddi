---
UID: NF:wdm.IoFreeErrorLogEntry
title: IoFreeErrorLogEntry function
author: windows-driver-content
description: The IoFreeErrorLogEntry routine frees an unused error log entry.
old-location: kernel\iofreeerrorlogentry.htm
old-project: kernel
ms.assetid: 7244a63b-404f-45e0-b2f7-6c4ea70e4a21
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , E, F, I, IoFreeErrorLogEntry, IoFreeErrorLogEntry routine [Kernel-Mode Driver Architecture], L, e, g, k104_33f7cbb2-e145-46f1-99a0-b53381704aad.xml, kernel.iofreeerrorlogentry, n, o, r, t, wdm/IoFreeErrorLogEntry, y"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows XP and later versions of the Windows operating system.
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
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	IoFreeErrorLogEntry
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# IoFreeErrorLogEntry function


## -description


The <b>IoFreeErrorLogEntry</b> routine frees an unused error log entry. 


## -syntax


````
VOID IoFreeErrorLogEntry(
  _In_ PVOID ElEntry
);
````


## -parameters




### -param ElEntry [in]

Pointer to an error log packet allocated by <a href="..\wdm\nf-wdm-ioallocateerrorlogentry.md">IoAllocateErrorLogEntry</a>. 


## -returns



None




## -remarks



Drivers use <b>IoFreeErrorLogEntry</b> to free an error log entry allocated by <a href="..\wdm\nf-wdm-ioallocateerrorlogentry.md">IoAllocateErrorLogEntry</a>. <a href="..\wdm\nf-wdm-iowriteerrorlogentry.md">IoWriteErrorLogEntry</a> also frees any error log entries passed to it, so drivers must not call both on the same log entry.




## -see-also

<a href="..\wdm\nf-wdm-ioallocateerrorlogentry.md">IoAllocateErrorLogEntry</a>



<a href="..\wdm\nf-wdm-iowriteerrorlogentry.md">IoWriteErrorLogEntry</a>



<a href="..\wdm\ns-wdm-_io_error_log_packet.md">IO_ERROR_LOG_PACKET</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoFreeErrorLogEntry routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

