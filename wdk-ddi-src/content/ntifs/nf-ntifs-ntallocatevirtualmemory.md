---
UID: NF:ntifs.NtAllocateVirtualMemory
title: NtAllocateVirtualMemory function (ntifs.h)
description: The NtAllocateVirtualMemory routine reserves, commits, or both, a region of pages within the user-mode virtual address space of a specified process.
tech.root: kernel
ms.assetid: bb82c90d-9bd3-4a23-b171-06a3208e424b
ms.date: 05/20/2020
keywords: ["NtAllocateVirtualMemory function"]
ms.keywords: NtAllocateVirtualMemory, ZwAllocateVirtualMemory, NtAllocateVirtualMemory routine [Kernel-Mode Driver Architecture], k111_76257300-f41b-4dad-a81f-8ea1b187244a.xml, kernel.ntallocatevirtualmemory, ntifs/NtAllocateVirtualMemory, ntifs/ZwAllocateVirtualMemory
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: PowerIrpDDis, HwStorPortProhibitedDDIs, SpNoWait, StorPortStartIo
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
 - NtAllocateVirtualMemory
 - ntifs/NtAllocateVirtualMemory
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - ZwAllocateVirtualMemory
 - NtAllocateVirtualMemory
---

# NtAllocateVirtualMemory function


## -description

The **NtAllocateVirtualMemory** routine reserves, commits, or both, a region of pages within the user-mode virtual address space of a specified process.

## -parameters

### -param ProcessHandle 

[in]
A handle for the process for which the mapping should be done. Use the **NtCurrentProcess** macro, defined in *Ntddk.h*, to specify the current process.

### -param BaseAddress 

[in, out]
A pointer to a variable that will receive the base address of the allocated region of pages. If the initial value of *BaseAddress* is non-**NULL**, the region is allocated starting at the specified virtual address rounded down to the next host page size address boundary. If the initial value of *BaseAddress* is **NULL**, the operating system will determine where to allocate the region.

### -param ZeroBits 

[in]
The number of high-order address bits that must be zero in the base address of the section view. Used only when the operating system determines where to allocate the region, as when *BaseAddress** is **NULL**. Note that when ZeroBits is larger than 32, it becomes a bitmask.

### -param RegionSize 

[in, out]
A pointer to a variable that will receive the actual size, in bytes, of the allocated region of pages. The initial value of *RegionSize* specifies the size, in bytes, of the region and is rounded up to the next host page size boundary. *RegionSize* cannot be zero on input.

### -param AllocationType 

[in]
A bitmask containing flags that specify the type of allocation to be performed for the specified region of pages. The following table describes the most common flags. See [**VirtualAlloc**](/windows/win32/api/memoryapi/nf-memoryapi-virtualalloc) for a full list of possible flags and descriptions.

> [!NOTE]
>
> One of MEM_COMMIT, MEM_RESET, or MEM_RESERVE must be set.

| Flag | Meaning |
| ---- | ------- |
| MEM_COMMIT | The specified region of pages is to be committed. |
| MEM_RESERVE | The specified region of pages is to be reserved. |
| MEM_RESET | Reset the state of the specified region so that if the pages are in paging file, they are discarded and pages of zeros are brought in. If the pages are in memory and modified, they are marked as not modified so that they will not be written out to the paging file. The contents are *not* zeroed. The **Protect** parameter is not used, but it must be set to a valid value. If MEM_RESET is set, no other flag may be set. |
| Other MEM_*XXX* flags | See [**VirtualAlloc**](/windows/win32/api/memoryapi/nf-memoryapi-virtualalloc). |

### -param Protect 

[in]
A bitmask containing page protection flags that specify the protection desired for the committed region of pages. The following table describes these flags.

| Flag | Meaning |
| ---- | ------- |
| PAGE_NOACCESS | No access to the committed region of pages is allowed. An attempt to read, write, or execute the committed region results in an access violation exception, called a general protection (GP) fault. |
| PAGE_READONLY | Read-only and execute access to the committed region of pages is allowed. An attempt to write the committed region results in an access violation. |
| PAGE_READWRITE | Read, write, and execute access to the committed region of pages is allowed. If write access to the underlying section is allowed, then a single copy of the pages is shared. Otherwise the pages are shared read only/copy on write. |
| PAGE_EXECUTE | Execute access to the committed region of pages is allowed. An attempt to read or write to the committed region results in an access violation. |
| PAGE_EXECUTE_READ | Execute and read access to the committed region of pages are allowed. An attempt to write to the committed region results in an access violation. |
| PAGE_GUARD | Pages in the region become guard pages. Any attempt to read from or write to a guard page causes the system to raise a STATUS_GUARD_PAGE exception. Guard pages thus act as a one-shot access alarm. This flag is a page protection modifier, valid only when used with one of the page protection flags other than PAGE_NOACCESS. When an access attempt leads the system to turn off guard page status, the underlying page protection takes over. If a guard page exception occurs during a system service, the service typically returns a failure status indicator. |
| PAGE_NOCACHE | The region of pages should be allocated as noncacheable. PAGE_NOCACHE is not allowed for sections. |
| PAGE_WRITECOMBINE | Enables write combining, that is, coalescing writes from cache to main memory, where the hardware supports it. This flag is used primarily for frame buffer memory so that writes to the same cache line are combined where possible before being written to the device. This can greatly reduce writes across the bus to (for example) video memory. If the hardware does not support write combining, the flag is ignored. This flag is a page protection modifier, valid only when used with one of the page protection flags other than PAGE_NOACCESS. |

## -returns

**NtAllocateVirtualMemory** returns either STATUS_SUCCESS or an error status code. Possible error status codes include the following:

* **STATUS_ACCESS_DENIED**
* **STATUS_ALREADY_COMMITTED**
* **STATUS_COMMITMENT_LIMIT**
* **STATUS_CONFLICTING_ADDRESSES**
* **STATUS_INSUFFICIENT_RESOURCES**
* **STATUS_INVALID_HANDLE**
* **STATUS_INVALID_PAGE_PROTECTION**
* **STATUS_NO_MEMORY**
* **STATUS_OBJECT_TYPE_MISMATCH**
* **STATUS_PROCESS_IS_TERMINATING**

## -remarks

**NtAllocateVirtualMemory** can perform the following operations:

* Commit a region of pages reserved by a previous call to **NtAllocateVirtualMemory**.
* Reserve a region of free pages.
* Reserve and commit a region of free pages.

Kernel-mode drivers can use **NtAllocateVirtualMemory** to reserve a range of application-accessible virtual addresses in the specified process and then make additional calls to **NtAllocateVirtualMemory** to commit individual pages from the reserved range. This enables a process to reserve a range of its virtual address space without consuming physical storage until it is needed.

Each page in the process's virtual address space is in one of the three states described in the following table.

| State | Meaning |
| ----- | ------- |
| FREE | The page is not committed or reserved and is not accessible to the process. **NtAllocateVirtualMemory** can reserve, or simultaneously reserve and commit, a free page. |
| RESERVED | The range of addresses cannot be used by other allocation functions, but the page is not accessible to the process and has no physical storage associated with it. **NtAllocateVirtualMemory** can commit a reserved page, but it cannot reserve it a second time. **NtFreeVirtualMemory** can release a reserved page, making it a free page. |
| COMMITTED | Physical storage is allocated for the page, and access is controlled by a protection code. The system initializes and loads each committed page into physical memory only at the first attempt to read or write to that page. When the process terminates, the system releases the storage for committed pages. **NtAllocateVirtualMemory** can commit an already committed page. This means that you can commit a range of pages, regardless of whether they have already been committed, and the function will not fail. **NtFreeVirtualMemory** can decommit a committed page, releasing the page's storage, or it can simultaneously decommit and release a committed page. |

Memory allocated by calling **NtAllocateVirtualMemory** must be freed by calling **NtFreeVirtualMemory**.

For more information about memory management, see [Memory Management for Windows Drivers](/windows-hardware/drivers/kernel/managing-memory-for-drivers).

> **Note**  If the call to the **NtAllocateVirtualMemory** function occurs in user mode, you should use the name "**NtAllocateVirtualMemory**" instead of "**ZwAllocateVirtualMemory**".

For calls from kernel-mode drivers, the **Nt*Xxx*** and **Zw*Xxx*** versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the **Nt*Xxx*** and **Zw*Xxx*** versions of a routine, see [Using Nt and Zw Versions of the Native System Services Routines](/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines).

## -see-also

[**NtFreeVirtualMemory**](./nf-ntifs-ntfreevirtualmemory.md)