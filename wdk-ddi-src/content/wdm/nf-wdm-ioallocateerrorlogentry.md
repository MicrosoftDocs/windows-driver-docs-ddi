---
UID: NF:wdm.IoAllocateErrorLogEntry
title: IoAllocateErrorLogEntry function (wdm.h)
description: The IoAllocateErrorLogEntry routine allocates an error log entry, and returns a pointer to the packet that the caller uses to supply information about an I/O error.
tech.root: kernel
ms.date: 12/12/2022
keywords: ["IoAllocateErrorLogEntry function"]
ms.keywords: IoAllocateErrorLogEntry, IoAllocateErrorLogEntry routine [Kernel-Mode Driver Architecture], k104_e3257473-eeae-4912-b3e1-8dd5ceb7430e.xml, kernel.ioallocateerrorlogentry, wdm/IoAllocateErrorLogEntry
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt:
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
req.irql: IRQL <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - IoAllocateErrorLogEntry
 - wdm/IoAllocateErrorLogEntry
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - IoAllocateErrorLogEntry
---

## -description

The **IoAllocateErrorLogEntry** routine allocates an error log entry, and returns a pointer to the packet that the caller uses to supply information about an I/O error.

## -parameters

### -param IoObject [in]

Pointer to a device object representing the device on which an I/O error occurred, or to a driver object representing the driver that found an error.

### -param EntrySize [in]

Specifies the size, in bytes, of the error log entry to be allocated. This value cannot exceed ERROR_LOG_MAXIMUM_SIZE.

> [!WARNING]
> *EntrySize* is a **UCHAR** value. If you specify a larger value, the compiler will silently truncate that value to a (wrong) **UCHAR**.

## -returns

**IoAllocateErrorLogEntry** returns a pointer to the error log entry, or **NULL** if a log entry could not be allocated.

## -remarks

The driver must first fill in the packet with information about the error, then call [IoWriteErrorLogEntry](/windows-hardware/drivers/ddi/ntifs/nf-ntifs-iowriteerrorlogentry) to post the entry to the error log. The error log entry buffer is automatically freed once the log entry is recorded. Entry buffers that are not going to be written to the log can be freed by using [IoFreeErrorLogEntry](/windows-hardware/drivers/ddi/wdm/nf-wdm-iofreeerrorlogentry).

An error log entry consists of a variable-length [IO_ERROR_LOG_PACKET](/windows-hardware/drivers/ddi/wdm/ns-wdm-_io_error_log_packet) structure, possibly followed by one or more zero-counted Unicode strings. The Event Viewer inserts these strings into the error message it displays for the entry. **IO_ERROR_LOG_PACKET** contains one variable-length member, the **DumpData** member. Thus, the value for *EntrySize* must be **sizeof**(**IO_ERROR_LOG_PACKET**) + size of the **DumpData** member + combined size of any driver-supplied insertion strings.

Drivers should check that the value for *EntrySize* is less than ERROR_LOG_MAXIMUM_SIZE before calling **IoAllocateErrorLogEntry**. Since *EntrySize*  is declared as a UCHAR, and the compiler will silently truncate any value too big to fit into a UCHAR, the routine itself cannot reliably detect if the passed value is too large.

Drivers must not treat **IoAllocateErrorLogEntry** returning **NULL** as a fatal error. The driver must continue to function normally, regardless of whether it can log errors.

## -see-also

[IO_ERROR_LOG_PACKET](/windows-hardware/drivers/ddi/wdm/ns-wdm-_io_error_log_packet)

[IoFreeErrorLogEntry](/windows-hardware/drivers/ddi/wdm/nf-wdm-iofreeerrorlogentry)

[IoWriteErrorLogEntry](/windows-hardware/drivers/ddi/ntifs/nf-ntifs-iowriteerrorlogentry)
