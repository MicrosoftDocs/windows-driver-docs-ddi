---
UID: NF:ntifs.IoWriteErrorLogEntry
title: IoWriteErrorLogEntry function (ntifs.h)
description: Learn more about the IoWriteErrorLogEntry routine.
tech.root: kernel
ms.date: 07/06/2023
keywords: ["IoWriteErrorLogEntry function"]
ms.keywords: IoWriteErrorLogEntry, kernel.iowriteerrorlogentry, wdm/IoWriteErrorLogEntry
req.header: ntifs.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Windows 2000
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

# IoWriteErrorLogEntry function (ntifs.h)

## -description

The **IoWriteErrorLogEntry** routine queues a given error log packet to the system error logging thread.

## -parameters

### -param ElEntry [in]

Pointer to the error log packet the driver has allocated with [**IoAllocateErrorLogEntry**](../wdm/nf-wdm-ioallocateerrorlogentry.md) and filled in by the caller.

## -remarks

**IoWriteErrorLogEntry** frees the error log entry. Drivers must not call **IoFreeErrorLogEntry** on a log entry that they have already passed to **IoWriteErrorLogEntry**.

## -see-also

[**IO_ERROR_LOG_PACKET**](../wdm/ns-wdm-_io_error_log_packet.md)

[**IoAllocateErrorLogEntry**](../wdm/nf-wdm-ioallocateerrorlogentry.md)

[**IoFreeErrorLogEntry**](../wdm/nf-wdm-iofreeerrorlogentry.md)
