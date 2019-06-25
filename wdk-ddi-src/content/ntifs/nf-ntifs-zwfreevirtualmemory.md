---
UID: NF:ntifs.ZwFreeVirtualMemory
title: ZwFreeVirtualMemory function (ntifs.h)
description: The ZwFreeVirtualMemory routine releases, decommits, or both, a region of pages within the virtual address space of a specified process.
old-location: kernel\zwfreevirtualmemory.htm
tech.root: kernel
ms.assetid: ca6675cf-3482-4e62-8f7c-801c1deacd37
ms.date: 04/30/2018
ms.keywords: NtFreeVirtualMemory, ZwFreeVirtualMemory, ZwFreeVirtualMemory routine [Kernel-Mode Driver Architecture], k111_c7ea9516-a020-4840-aa18-7f98470cc142.xml, kernel.zwfreevirtualmemory, ntifs/NtFreeVirtualMemory, ntifs/ZwFreeVirtualMemory
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h, Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: PowerIrpDDis, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- ZwFreeVirtualMemory
- NtFreeVirtualMemory
product:
- Windows
targetos: Windows
req.typenames: 
---

# ZwFreeVirtualMemory function


## -description


The <b>ZwFreeVirtualMemory</b> routine releases, decommits, or both, a region of pages within the virtual address space of a specified process.


## -parameters




### -param ProcessHandle [in]

A handle for the process in whose context the pages to be freed reside. Use the <b>NtCurrentProcess</b> macro, defined in Ntddk.h, to specify the current process.


### -param BaseAddress [in, out]

A pointer to a variable that will receive the virtual address of the freed region of pages. 

If the MEM_RELEASE flag is set in the <i>FreeType</i> parameter, <i>BaseAddress</i> must be the base address returned by <a href="https://msdn.microsoft.com/library/windows/hardware/ff566416">ZwAllocateVirtualMemory</a> when the region was reserved.


### -param RegionSize [in, out]

A pointer to a variable that will receive the actual size, in bytes, of the freed region of pages. The routine rounds the initial value of this variable up to the next host page size boundary and writes the rounded value back to this variable.

If the MEM_RELEASE flag is set in the <i>FreeType</i> parameter, the variable pointed to by <i>RegionSize</i> must be zero. <b>ZwFreeVirtualMemory</b> frees the entire region that was reserved in the initial allocation call to <b>ZwAllocateVirtualMemory</b>.

If the MEM_DECOMMIT flag is set in the <i>FreeType</i> parameter, <b>ZwFreeVirtualMemory</b> decommits all memory pages that contain one or more bytes in the range from the <i>BaseAddress</i> parameter to (<i>BaseAddress</i> + *<i>RegionSize</i>). This means, for example, that if a two-byte region of memory straddles a page boundary, both pages are decommitted.

<b>ZwFreeVirtualMemory</b> decommits the entire region that was reserved by <b>ZwAllocateVirtualMemory</b>. If the following three conditions are met, the entire region enters the reserved state:

<ul>
<li>
The MEM_DECOMMIT flag is set.

</li>
<li>
<i>BaseAddress</i> is the base address returned by <b>ZwAllocateVirtualMemory</b> when the region was reserved.

</li>
<li>

         *<i>RegionSize</i> is zero.

</li>
</ul>

### -param FreeType [in]

A bitmask that contains flags that describe the type of free operation that <b>ZwFreeVirtualMemory</b> will perform for the specified region of pages. The possible values are listed in the following table.

<table>
<tr>
<th><i>FreeType</i> flags</th>
<th>Description</th>
</tr>
<tr>
<td>
MEM_DECOMMIT

</td>
<td>
<b>ZwFreeVirtualMemory</b> will decommit the specified region of pages. The pages enter the reserved state.

<b>ZwFreeVirtualMemory</b> does not fail if you attempt to decommit an uncommitted page. This means that you can decommit a range of pages without first determining their current commitment state.

</td>
</tr>
<tr>
<td>
MEM_RELEASE

</td>
<td>
<b>ZwFreeVirtualMemory</b> will release the specified region of pages. The pages enter the free state.

If you specify this flag, *<i>RegionSize</i> must be zero, and <i>BaseAddress </i>must point to the base address returned by <a href="https://msdn.microsoft.com/library/windows/hardware/ff566416">ZwAllocateVirtualMemory</a> when the region was reserved. <b>ZwFreeVirtualMemory</b> fails if either of these conditions is not met.

If any pages in the region are currently committed, <b>ZwFreeVirtualMemory</b> first decommits and then releases them.

<b>ZwFreeVirtualMemory</b> does not fail if you attempt to release pages that are in different states, some reserved and some committed. This means that you can release a range of pages without first determining their current commitment state.

</td>
</tr>
</table>
 


## -returns



<b>ZwFreeVirtualMemory</b> returns either STATUS_SUCCESS or an error status code. Possible error status codes include the following.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_ACCESS_DENIED</b></dt>
</dl>
</td>
<td width="60%">
A process has requested access to an object, but has not been granted those access rights.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_HANDLE</b></dt>
</dl>
</td>
<td width="60%">
An invalid <i>ProcessHandle</i> value was specified.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_OBJECT_TYPE_MISMATCH</b></dt>
</dl>
</td>
<td width="60%">
There is a mismatch between the type of object required by the requested operation and the type of object that is specified in the request.

</td>
</tr>
</table>
 




## -remarks



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
The page is neither committed nor reserved. The page is not accessible to the process. Attempting to read from or write to a free page results in an access violation exception. 

You can use <b>ZwFreeVirtualMemory</b> to put reserved or committed pages into the free state.

</td>
</tr>
<tr>
<td>
RESERVED

</td>
<td>
The page is reserved. The range of addresses cannot be used by other allocation functions. The page is not accessible to the process and has no physical storage associated with it. Attempting to read from or write to a reserved page results in an access violation exception. 

You can use <b>ZwFreeVirtualMemory</b> to put committed memory pages into the reserved state, and to put reserved memory pages into the free state. 

</td>
</tr>
<tr>
<td>
COMMITTED

</td>
<td>
The page is committed. Physical storage in memory or in the paging file on disk is allocated for the page, and access is controlled by a protection code. 

The system initializes and loads each committed page into physical memory only at the first attempt to read from or write to that page. 

When a process terminates, the system releases all storage for committed pages.

You can use <a href="https://msdn.microsoft.com/library/windows/hardware/ff566416">ZwAllocateVirtualMemory</a> to put committed memory pages into either the reserved or free state.

</td>
</tr>
</table>
 

<b>ZwFreeVirtualMemory</b> can perform the following operations:

<ul>
<li>
Decommit a region of committed or uncommitted pages. After this operation, the pages are in the reserved state. 

</li>
<li>
Release a region of reserved pages. After this operation, the pages are in the free state.

</li>
<li>
Decommit and release a region of committed or uncommitted pages. After this operation, the pages are in the free state. 

</li>
</ul>
<b>ZwFreeVirtualMemory</b> can decommit a range of pages that are in different states, some committed and some uncommitted. This means that you can decommit a range of pages without first determining the current commitment state of each page. Decommitting a page releases its physical storage, either in memory or in the paging file on disk.

If a page is decommitted but not released, its state changes to reserved. You can subsequently call <b>ZwAllocateVirtualMemory</b> to commit it, or <b>ZwFreeVirtualMemory</b> to release it. Attempting to read from or write to a reserved page results in an access violation exception.

<b>ZwFreeVirtualMemory</b> can release a range of pages that are in different states, some reserved and some committed. This means that you can release a range of pages without first determining the current commitment state of each page. The entire range of pages originally reserved by <a href="https://msdn.microsoft.com/library/windows/hardware/ff566416">ZwAllocateVirtualMemory</a> must be released at the same time.

If a page is released, its state changes to free, and it is available for subsequent allocation operations. After memory has been released or decommitted, you can never refer to the memory again. Any information that may have been in that memory is gone forever. Attempting to read from or write to a free page results in an access violation exception. If you require information, do not decommit or free memory that contains that information.

For more information about memory management support for kernel-mode drivers, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/managing-memory-for-drivers">Memory Management for Windows Drivers</a>.

<div class="alert"><b>Note</b>  If the call to the <b>ZwFreeVirtualMemory</b> function occurs in user mode, you should use the name "<b>NtFreeVirtualMemory</b>" instead of "<b>ZwFreeVirtualMemory</b>".</div>
<div> </div>
For calls from kernel-mode drivers, the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a routine, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines">Using Nt and Zw Versions of the Native System Services Routines</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines">Using Nt and Zw Versions of the Native System Services Routines</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566416">ZwAllocateVirtualMemory</a>
 

 

