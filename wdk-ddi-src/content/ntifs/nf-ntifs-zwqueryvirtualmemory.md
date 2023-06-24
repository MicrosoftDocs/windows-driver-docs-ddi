---
UID: NF:ntifs.ZwQueryVirtualMemory
title: ZwQueryVirtualMemory function (ntifs.h)
description: The ZwQueryVirtualMemory routine determines the state, protection, and type of a region of pages within the virtual address space of the subject process.
old-location: kernel\zwqueryvirtualmemory.htm
tech.root: kernel
ms.date: 07/26/2022
keywords: ["ZwQueryVirtualMemory function"]
ms.keywords: NtQueryVirtualMemory, ZwQueryVirtualMemory, ZwQueryVirtualMemory routine [Kernel-Mode Driver Architecture], kernel.zwqueryvirtualmemory, ntifs/NtQueryVirtualMemory, ntifs/ZwQueryVirtualMemory
req.header: ntifs.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Windows 10
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
 - ZwQueryVirtualMemory
 - ntifs/ZwQueryVirtualMemory
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - ZwQueryVirtualMemory
---

# ZwQueryVirtualMemory function

## -description

The **ZwQueryVirtualMemory** routine determines the state, protection, and type of a region of pages within the virtual address space of the subject process.

## -parameters

### -param ProcessHandle [in]

A handle for the process in whose context the pages to be queried reside. Use the [**ZwCurrentProcess**](/windows-hardware/drivers/kernel/zwcurrentprocess) macro to specify the current process.

### -param BaseAddress [in, optional]

The base address of the region of pages to be queried. This value is rounded down to the next host-page address boundary.

### -param MemoryInformationClass [in]

The memory information class about which to retrieve information. Currently, the only supported [**MEMORY_INFORMATION_CLASS**](ne-ntifs-_memory_information_class.md) value is **MemoryBasicInformation**.

### -param MemoryInformation [out]

A pointer to a buffer that receives the specified information.  The format and content of the buffer depend on the specified information class specified in the **MemoryInformationClass** parameter. When the value **MemoryBasicInformation** is passed to **MemoryInformationClass**, the **MemoryInformation** parameter value is a [**MEMORY_BASIC_INFORMATION**](./ns-ntifs-_memory_basic_information.md) structure.

### -param MemoryInformationLength [in]

Specifies the length in bytes of the memory information buffer.

### -param ReturnLength [out, optional]

An optional pointer which, if specified, receives the number of bytes placed in the memory information buffer.

## -returns

Returns STATUS_SUCCESS if the call is successful. If the call fails, possible error codes include the following:

| Return code | Description |
| ----------- | ----------- |
| STATUS_INVALID_PARAMETER    | The specified base address is outside the range of accessible addresses. |
| STATUS_ACCESS_DENIED        | The caller had insufficient access rights to perform the requested action. |
| STATUS_INFO_LENGTH_MISMATCH | The **MemoryInformation** buffer is larger than **MemoryInformationLength.** |
| STATUS_INVALID_INFO_CLASS   | A value other than **MemoryBasicInformation** was passed to the **MemoryInformationClass**  parameter. |

## -remarks

**ZwQueryVirtualMemory** determines the state of the first page within the region and then scans subsequent entries in the process address map from the base address upward until either the entire range of pages has been scanned or until a page with a non-matching set of attributes is encountered. The region attributes, the length of the region of pages with matching attributes, and an appropriate status value are returned.

If the entire region of pages does not have a matching set of attributes, then the **ReturnLength** parameter value can be used to compute the address and length of the region of pages that was not scanned.

[**NtQueryVirtualMemory**](nf-ntifs-ntqueryvirtualmemory.md) and **ZwQueryVirtualMemory** are two versions of the same Windows Native System Services routine.

For calls from kernel-mode drivers, the **Nt**Xxx**** and **Zw**Xxx**** versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the **Nt*Xxx*** and **Zw*Xxx*** versions of a routine, see [Using Nt and Zw Versions of the Native System Services Routines](/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines).

## -see-also

[**POWER_PLATFORM_INFORMATION**](../wdm/ns-wdm-_power_platform_information.md)
