---
UID: NF:ntifs.IoWriteErrorLogEntry
title: IoWriteErrorLogEntry function (ntifs.h)
description: The IoWriteErrorLogEntry routine queues a given error log packet to the system error logging thread.
old-location: kernel\iowriteerrorlogentry.htm
tech.root: kernel
ms.assetid: 1259c344-584c-410a-a152-5de1f433082c
ms.date: 04/30/2018
keywords: ["IoWriteErrorLogEntry function"]
ms.keywords: IoWriteErrorLogEntry, IoWriteErrorLogEntry routine [Kernel-Mode Driver Architecture], k104_1822a499-059a-41c8-b97b-aa3a5bfd22e3.xml, kernel.iowriteerrorlogentry, wdm/IoWriteErrorLogEntry
req.header: ntifs.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: IrqlDispatch
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - IoWriteErrorLogEntry
 - ntifs/IoWriteErrorLogEntry
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - IoWriteErrorLogEntry
---

# IoWriteErrorLogEntry function


## -description

The <b>IoWriteErrorLogEntry</b> routine queues a given error log packet to the system error logging thread.

## -parameters

### -param ElEntry 

[in]
Pointer to the error log packet the driver has allocated with <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ioallocateerrorlogentry">IoAllocateErrorLogEntry</a> and filled in by the caller.

## -remarks

<b>IoWriteErrorLogEntry</b> frees the error log entry. Drivers must not call <b>IoFreeErrorLogEntry</b> on a log entry that they have already passed to <b>IoWriteErrorLogEntry</b>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_io_error_log_packet">IO_ERROR_LOG_PACKET</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ioallocateerrorlogentry">IoAllocateErrorLogEntry</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iofreeerrorlogentry">IoFreeErrorLogEntry</a>

