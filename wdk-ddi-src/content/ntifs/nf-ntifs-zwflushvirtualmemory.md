---
UID: NF:ntifs._FSRTL_ADVANCED_FCB_HEADER.ZwFlushVirtualMemory
title: ZwFlushVirtualMemory function (ntifs.h)
description: The ZwFlushVirtualMemory routine flushes a range of virtual addresses within the virtual address space of a specified process which map to a data file back out to the data file if they have been modified.
old-location: kernel\zwflushvirtualmemory.htm
tech.root: kernel
ms.assetid: 86e04896-2921-4f77-9bee-283ceb9a66bc
ms.date: 04/30/2018
ms.keywords: NtFlushVirtualMemory, ZwFlushVirtualMemory, ZwFlushVirtualMemory routine [Kernel-Mode Driver Architecture], k111_536d2679-dc41-490f-be7b-171e0208a1fd.xml, kernel.zwflushvirtualmemory, ntifs/NtFlushVirtualMemory, ntifs/ZwFlushVirtualMemory
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows XP.
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
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- ZwFlushVirtualMemory
- NtFlushVirtualMemory
product:
- Windows
targetos: Windows
req.typenames: 
---

# ZwFlushVirtualMemory function


## -description


The <b>ZwFlushVirtualMemory</b> routine flushes a range of virtual addresses within the virtual address space of a specified process which map to a data file back out to the data file if they have been modified.


## -parameters




### -param ProcessHandle [in]

An open handle for the process in whose context the pages to be flushed reside. Use the <b>NtCurrentProcess</b> macro, defined in Ntddk.h, to specify the current process. 


### -param BaseAddress [in, out]

A pointer to the base address of the virtual address range.

On entry, this parameter specifies a pointer to the initial value of the base address of the region of pages to flush.

On return, this parameter provides a pointer to a variable that will receive the base address of the flushed region.


### -param RegionSize [in, out]

The size, in bytes, of the virtual address range.

On entry, this parameter specifies a pointer to the initial value of the size in bytes of the region of pages to flush to disk. This argument is rounded up to the next host-page-size boundary by the <b>ZwFlushVirtualMemory</b>. If this value is specified as zero, the mapped range from the base address to the end of the range is flushed.

On return, this parameter specifies a pointer to a variable that will receive the actual size in bytes of the flushed region of pages.


### -param IoStatus [out]

A pointer to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_io_status_block">IO_STATUS_BLOCK</a> structure. This structure is where the value of the I/O status for the last attempted I/O operation is stored on output.


## -returns



<b>ZwFlushVirtualMemory</b> returns either STATUS_SUCCESS or an error status code. Possible error status codes include the following:

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
The specified <i>ProcessHandle</i> parameter was not a valid process handle. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
Additional resources required by this function were not available. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER_2</b></dt>
</dl>
</td>
<td width="60%">
The <i>BaseAddress</i> specified was an invalid address within the virtual address space or the <i>RegionSize</i> was invalid. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_HANDLE</b></dt>
</dl>
</td>
<td width="60%">
The specified <i>ProcessHandle</i> parameter was not a valid process handle. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NOT_MAPPED_VIEW</b></dt>
</dl>
</td>
<td width="60%">
No virtual address space descriptor could be located for the supplied <i>BaseAddress</i>. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_PROCESS_IS_TERMINATING</b></dt>
</dl>
</td>
<td width="60%">
The process and the associated virtual address space was deleted. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_FILE_LOCK_CONFLICT</b></dt>
</dl>
</td>
<td width="60%">
The file system encountered a locking conflict. 

</td>
</tr>
</table>
 




## -remarks




     This routine accepts, as input parameters, a range of addresses in virtual memory that map a data file. If any memory in this range has been modified since the file was copied to memory, the routine flushes this memory back to the data file.

For more information about memory management support for kernel-mode drivers, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/managing-memory-for-drivers">Memory Management for Windows Drivers</a>. 

<div class="alert"><b>Note</b>  If the call to the <b>ZwFlushVirtualMemory</b> function occurs in user mode, you should use the name "<b>NtFlushVirtualMemory</b> " instead of "<b>ZwFlushVirtualMemory</b>".</div>
<div> </div>
For calls from kernel-mode drivers, the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a routine, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines">Using Nt and Zw Versions of the Native System Services Routines</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines">Using Nt and Zw Versions of the Native System Services Routines</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566416">ZwAllocateVirtualMemory</a>
 

 

