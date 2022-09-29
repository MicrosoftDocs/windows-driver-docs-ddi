---
UID: NF:ntifs.ZwFlushVirtualMemory
title: ZwFlushVirtualMemory function (ntifs.h)
description: The ZwFlushVirtualMemory routine flushes a range of virtual addresses within the virtual address space of a specified process which map to a data file back out to the data file if they have been modified.
old-location: kernel\zwflushvirtualmemory.htm
tech.root: kernel
ms.date: 07/26/2022
keywords: ["ZwFlushVirtualMemory function"]
ms.keywords: NtFlushVirtualMemory, ZwFlushVirtualMemory, ZwFlushVirtualMemory routine [Kernel-Mode Driver Architecture], k111_536d2679-dc41-490f-be7b-171e0208a1fd.xml, kernel.zwflushvirtualmemory, ntifs/NtFlushVirtualMemory, ntifs/ZwFlushVirtualMemory
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Windows XP
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
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - ZwFlushVirtualMemory
 - ntifs/ZwFlushVirtualMemory
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - ZwFlushVirtualMemory
---

# ZwFlushVirtualMemory function

## -description

The **ZwFlushVirtualMemory** routine flushes a range of virtual addresses within the virtual address space of a specified process which map to a data file back out to the data file if they have been modified.

## -parameters

### -param ProcessHandle [in]

An open handle for the process in whose context the pages to be flushed reside. Use the **NtCurrentProcess** macro, defined in Ntddk.h, to specify the current process.

### -param BaseAddress [in, out]

A pointer to the base address of the virtual address range.

On entry, this parameter specifies a pointer to the initial value of the base address of the region of pages to flush.

On return, this parameter provides a pointer to a variable that will receive the base address of the flushed region.

### -param RegionSize [in, out]

The size, in bytes, of the virtual address range.

On entry, this parameter specifies a pointer to the initial value of the size in bytes of the region of pages to flush to disk. This argument is rounded up to the next host-page-size boundary by the **ZwFlushVirtualMemory**. If this value is specified as zero, the mapped range from the base address to the end of the range is flushed.

On return, this parameter specifies a pointer to a variable that will receive the actual size in bytes of the flushed region of pages.

### -param IoStatus [out]

A pointer to an [**IO_STATUS_BLOCK**](../wdm/ns-wdm-_io_status_block.md) structure. This structure is where the value of the I/O status for the last attempted I/O operation is stored on output.

## -returns

**ZwFlushVirtualMemory** returns either STATUS_SUCCESS or an error status code. Possible error status codes include the following:

| Return code | Description |
| ----------- | ----------- |
| STATUS_ACCESS_DENIED | The specified **ProcessHandle** parameter was not a valid process handle. |
| STATUS_INSUFFICIENT_RESOURCES | Additional resources required by this function were not available. |
| STATUS_INVALID_PARAMETER_2 | The **BaseAddress** specified was an invalid address within the virtual address space or the **RegionSize** was invalid.  |
| STATUS_INVALID_HANDLE | The specified **ProcessHandle** parameter was not a valid process handle. |
| STATUS_NOT_MAPPED_VIEW | No virtual address space descriptor could be located for the supplied **BaseAddress**. |
| STATUS_PROCESS_IS_TERMINATING | The process and the associated virtual address space was deleted. |
| STATUS_FILE_LOCK_CONFLICT | The file system encountered a locking conflict. |

## -remarks

This routine accepts, as input parameters, a range of addresses in virtual memory that map a data file. If any memory in this range has been modified since the file was copied to memory, the routine flushes this memory back to the data file.

For more information about memory management support for kernel-mode drivers, see [Memory Management for Windows Drivers](/windows-hardware/drivers/kernel/managing-memory-for-drivers).

> [!NOTE]
> If the call to the **ZwFlushVirtualMemory** function occurs in user mode, you should use the name "**NtFlushVirtualMemory**" instead of "**ZwFlushVirtualMemory**".

For calls from kernel-mode drivers, the **Nt*Xxx*** and **Zw*Xxx*** versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the **Nt*Xxx*** and **Zw*Xxx*** versions of a routine, see [Using Nt and Zw Versions of the Native System Services Routines](/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines).

## -see-also

[**ZwAllocateVirtualMemory**](nf-ntifs-zwallocatevirtualmemory.md)
