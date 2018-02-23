---
UID: NF:ntifs.ZwAllocateVirtualMemory
title: ZwAllocateVirtualMemory function
author: windows-driver-content
description: The ZwAllocateVirtualMemory routine reserves, commits, or both, a region of pages within the user-mode virtual address space of a specified process.
old-location: kernel\zwallocatevirtualmemory.htm
old-project: kernel
ms.assetid: bb82c90d-9bd3-4a23-b171-06a3208e424b
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: k111_76257300-f41b-4dad-a81f-8ea1b187244a.xml, kernel.zwallocatevirtualmemory, NtAllocateVirtualMemory, ZwAllocateVirtualMemory, ntifs/NtAllocateVirtualMemory, ZwAllocateVirtualMemory routine [Kernel-Mode Driver Architecture], ntifs/ZwAllocateVirtualMemory
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	ZwAllocateVirtualMemory
-	NtAllocateVirtualMemory
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# ZwAllocateVirtualMemory function


## -description


The <b>ZwAllocateVirtualMemory</b> routine reserves, commits, or both, a region of pages within the user-mode virtual address space of a specified process.


## -syntax


````
NTSTATUS ZwAllocateVirtualMemory(
  _In_    HANDLE    ProcessHandle,
  _Inout_ PVOID     *BaseAddress,
  _In_    ULONG_PTR ZeroBits,
  _Inout_ PSIZE_T   RegionSize,
  _In_    ULONG     AllocationType,
  _In_    ULONG     Protect
);
````


## -parameters




### -param ProcessHandle [in]

A handle for the process for which the mapping should be done. Use the <b>NtCurrentProcess</b> macro, defined in Ntddk.h, to specify the current process.


### -param BaseAddress [in, out]

A pointer to a variable that will receive the base address of the allocated region of pages. If the initial value of this parameter is non-<b>NULL</b>, the region is allocated starting at the specified virtual address rounded down to the next host page size address boundary. If the initial value of this parameter is <b>NULL</b>, the operating system will determine where to allocate the region.


### -param ZeroBits [in]

The number of high-order address bits that must be zero in the base address of the section view. This value must be less than 21 and is used only when the operating system determines where to allocate the region, as when <i>BaseAddress</i> is <b>NULL</b>.


### -param RegionSize [in, out]

A pointer to a variable that will receive the actual size, in bytes, of the allocated region of pages. The initial value of this parameter specifies the size, in bytes, of the region and is rounded up to the next host page size boundary. <i>*RegionSize</i> cannot be zero on input. 


### -param AllocationType [in]

A bitmask containing flags that specify the type of allocation to be performed. The following table describes these flags.

<table>
<tr>
<th>Flag</th>
<th>Meaning</th>
</tr>
<tr>
<td>
MEM_COMMIT

</td>
<td>
The specified region of pages is to be committed. One of MEM_COMMIT, MEM_RESET, or MEM_RESERVE must be set.

</td>
</tr>
<tr>
<td>
MEM_PHYSICAL

</td>
<td>
Allocate physical memory. This flag is solely for use with Address Windowing Extensions (AWE) memory. 

If MEM_PHYSICAL is set, MEM_RESERVE must also be set. No other flags may be set.

If MEM_PHYSICAL is set, <i>Protect</i> must be set to PAGE_READWRITE.

</td>
</tr>
<tr>
<td>
MEM_RESERVE

</td>
<td>
The specified region of pages is to be reserved. One of MEM_COMMIT, MEM_RESET, or MEM_RESERVE must be set.

</td>
</tr>
<tr>
<td>
MEM_RESET

</td>
<td>
Reset the state of the specified region so that if the pages are in paging file, they are discarded and pages of zeros are brought in. If the pages are in memory and modified, they are marked as not modified so that they will not be written out to the paging file. The contents are <u>not</u> zeroed. The <i>Protect</i> parameter is not used, but it must be set to a valid value. 

One of MEM_COMMIT, MEM_RESET, or MEM_RESERVE must be set.

If MEM_RESET is set, no other flag may be set.

</td>
</tr>
<tr>
<td>
MEM_TOP_DOWN

</td>
<td>
The specified region should be created at the highest virtual address possible based on <i>ZeroBits</i>.

</td>
</tr>
</table>
 


### -param Protect [in]

A bitmask containing page protection flags that specify the protection desired for the committed region of pages. The following table describes these flags.

<table>
<tr>
<th>Flag</th>
<th>Meaning</th>
</tr>
<tr>
<td>
PAGE_NOACCESS

</td>
<td>
No access to the committed region of pages is allowed. An attempt to read, write, or execute the committed region results in an access violation exception, called a general protection (GP) fault.

</td>
</tr>
<tr>
<td>
PAGE_READONLY

</td>
<td>
Read-only and execute access to the committed region of pages is allowed. 

An attempt to write the committed region results in an access violation.

</td>
</tr>
<tr>
<td>
PAGE_READWRITE

</td>
<td>
Read, write, and execute access to the committed region of pages is allowed. 

If write access to the underlying section is allowed, then a single copy of the pages is shared. Otherwise the pages are shared read only/copy on write.

</td>
</tr>
<tr>
<td>
PAGE_EXECUTE

</td>
<td>
Execute access to the committed region of pages is allowed. An attempt to read or write to the committed region results in an access violation.

</td>
</tr>
<tr>
<td>
PAGE_EXECUTE_READ

</td>
<td>
Execute and read access to the committed region of pages are allowed. An attempt to write to the committed region results in an access violation.

</td>
</tr>
<tr>
<td>
PAGE_EXECUTE_READWRITE

</td>
<td>
Execute, read, and write access to the committed region of pages are allowed.

</td>
</tr>
<tr>
<td>
PAGE_GUARD

</td>
<td>
Pages in the region become guard pages. Any attempt to read from or write to a guard page causes the system to raise a STATUS_GUARD_PAGE exception. Guard pages thus act as a one-shot access alarm. 

This flag is a page protection modifier, valid only when used with one of the page protection flags other than PAGE_NOACCESS. When an access attempt leads the system to turn off guard page status, the underlying page protection takes over.

If a guard page exception occurs during a system service, the service typically returns a failure status indicator.

</td>
</tr>
<tr>
<td>
PAGE_NOCACHE

</td>
<td>
The region of pages should be allocated as noncacheable.

PAGE_NOCACHE is not allowed for sections.

</td>
</tr>
<tr>
<td>
PAGE_WRITECOMBINE

</td>
<td>
Enables write combining, that is, coalescing writes from cache to main memory, where the hardware supports it. This flag is used primarily for frame buffer memory so that writes to the same cache line are combined where possible before being written to the device. This can greatly reduce writes across the bus to (for example) video memory. If the hardware does not support write combining, the flag is ignored.

This flag is a page protection modifier, valid only when used with one of the page protection flags other than PAGE_NOACCESS.

</td>
</tr>
</table>
 


## -returns



<b>ZwAllocateVirtualMemory</b> returns either STATUS_SUCCESS or an error status code. Possible error status codes include the following:




## -remarks



<b>ZwAllocateVirtualMemory</b> can perform the following operations:

<ul>
<li>
Commit a region of pages reserved by a previous call to <b>ZwAllocateVirtualMemory</b>.

</li>
<li>
Reserve a region of free pages.

</li>
<li>
Reserve and commit a region of free pages.

</li>
</ul>
Kernel-mode drivers can use <b>ZwAllocateVirtualMemory</b> to reserve a range of application-accessible virtual addresses in the specified process and then make additional calls to <b>ZwAllocateVirtualMemory</b> to commit individual pages from the reserved range. This enables a process to reserve a range of its virtual address space without consuming physical storage until it is needed.

Each page in the process's virtual address space is in one of the three states described in the following table.

<table>
<tr>
<th>State</th>
<th>Meaning</th>
</tr>
<tr>
<td>
FREE

</td>
<td>
The page is not committed or reserved and is not accessible to the process. <b>ZwAllocateVirtualMemory</b> can reserve, or simultaneously reserve and commit, a free page.

</td>
</tr>
<tr>
<td>
RESERVED

</td>
<td>
The range of addresses cannot be used by other allocation functions, but the page is not accessible to the process and has no physical storage associated with it. <b>ZwAllocateVirtualMemory</b> can commit a reserved page, but it cannot reserve it a second time. <b>ZwFreeVirtualMemory</b> can release a reserved page, making it a free page.

</td>
</tr>
<tr>
<td>
COMMITTED

</td>
<td>
Physical storage is allocated for the page, and access is controlled by a protection code. The system initializes and loads each committed page into physical memory only at the first attempt to read or write to that page. When the process terminates, the system releases the storage for committed pages. <b>ZwAllocateVirtualMemory</b> can commit an already committed page. This means that you can commit a range of pages, regardless of whether they have already been committed, and the function will not fail. <b>ZwFreeVirtualMemory</b> can decommit a committed page, releasing the page's storage, or it can simultaneously decommit and release a committed page.

</td>
</tr>
</table>
 

Memory allocated by calling <b>ZwAllocateVirtualMemory</b> must be freed by calling <b>ZwFreeVirtualMemory</b>.

For more information about memory management, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff554389">Memory Management for Windows Drivers</a>.

<div class="alert"><b>Note</b>  If the call to the <b>ZwAllocateVirtualMemory </b>function occurs in user mode, you should use the name "<b>NtAllocateVirtualMemory</b>" instead of "<b>ZwAllocateVirtualMemory</b>".</div>
<div> </div>
For calls from kernel-mode drivers, the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a routine, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>.




## -see-also

<a href="..\ntifs\nf-ntifs-zwfreevirtualmemory.md">ZwFreeVirtualMemory</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ZwAllocateVirtualMemory routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

