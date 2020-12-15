---
UID: NF:wdm.IoFreeErrorLogEntry
title: IoFreeErrorLogEntry function (wdm.h)
description: The IoFreeErrorLogEntry routine frees an unused error log entry.
old-location: kernel\iofreeerrorlogentry.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["IoFreeErrorLogEntry function"]
ms.keywords: IoFreeErrorLogEntry, IoFreeErrorLogEntry routine [Kernel-Mode Driver Architecture], k104_33f7cbb2-e145-46f1-99a0-b53381704aad.xml, kernel.iofreeerrorlogentry, wdm/IoFreeErrorLogEntry
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IoFreeErrorLogEntry
 - wdm/IoFreeErrorLogEntry
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - IoFreeErrorLogEntry
---

# IoFreeErrorLogEntry function


## -description

The <b>IoFreeErrorLogEntry</b> routine frees an unused error log entry.

## -parameters

### -param ElEntry 

[in]
Pointer to an error log packet allocated by <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ioallocateerrorlogentry">IoAllocateErrorLogEntry</a>.

## -remarks

Drivers use <b>IoFreeErrorLogEntry</b> to free an error log entry allocated by <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ioallocateerrorlogentry">IoAllocateErrorLogEntry</a>. <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-iowriteerrorlogentry">IoWriteErrorLogEntry</a> also frees any error log entries passed to it, so drivers must not call both on the same log entry.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_io_error_log_packet">IO_ERROR_LOG_PACKET</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ioallocateerrorlogentry">IoAllocateErrorLogEntry</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-iowriteerrorlogentry">IoWriteErrorLogEntry</a>
