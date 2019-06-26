---
UID: NF:wdm.IoFreeErrorLogEntry
title: IoFreeErrorLogEntry function (wdm.h)
description: The IoFreeErrorLogEntry routine frees an unused error log entry.
old-location: kernel\iofreeerrorlogentry.htm
tech.root: kernel
ms.assetid: 7244a63b-404f-45e0-b2f7-6c4ea70e4a21
ms.date: 04/30/2018
ms.keywords: IoFreeErrorLogEntry, IoFreeErrorLogEntry routine [Kernel-Mode Driver Architecture], k104_33f7cbb2-e145-46f1-99a0-b53381704aad.xml, kernel.iofreeerrorlogentry, wdm/IoFreeErrorLogEntry
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
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- IoFreeErrorLogEntry
product:
- Windows
targetos: Windows
req.typenames: 
---

# IoFreeErrorLogEntry function


## -description


The <b>IoFreeErrorLogEntry</b> routine frees an unused error log entry. 


## -parameters




### -param ElEntry [in]

Pointer to an error log packet allocated by <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-ioallocateerrorlogentry">IoAllocateErrorLogEntry</a>. 


## -returns



None




## -remarks



Drivers use <b>IoFreeErrorLogEntry</b> to free an error log entry allocated by <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-ioallocateerrorlogentry">IoAllocateErrorLogEntry</a>. <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-iowriteerrorlogentry">IoWriteErrorLogEntry</a> also frees any error log entries passed to it, so drivers must not call both on the same log entry.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_io_error_log_packet">IO_ERROR_LOG_PACKET</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-ioallocateerrorlogentry">IoAllocateErrorLogEntry</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-iowriteerrorlogentry">IoWriteErrorLogEntry</a>
 

 

