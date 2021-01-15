---
UID: NF:wdm.MmMapIoSpaceEx
title: MmMapIoSpaceEx function (wdm.h)
description: The MmMapIoSpaceEx routine maps the given physical address range to non-paged system space using the specified page protection.
old-location: kernel\mmmapiospaceex.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["MmMapIoSpaceEx function"]
ms.keywords: MmMapIoSpace, MmMapIoSpace routine [Kernel-Mode Driver Architecture], MmMapIoSpaceEx, kernel.mmmapiospaceex, wdm/MmMapIoSpace
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 10.
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
req.irql: <=DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - MmMapIoSpaceEx
 - wdm/MmMapIoSpaceEx
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - MmMapIoSpaceEx
---

# MmMapIoSpaceEx function


## -description

The <b>MmMapIoSpaceEx</b> routine maps the given physical address range to non-paged system space using the specified page protection.

## -parameters

### -param PhysicalAddress 

[in]
Specifies the starting physical address of the I/O range to be mapped.

### -param NumberOfBytes 

[in]
Specifies a value greater than zero, indicating the number of bytes to be mapped.

### -param Protect 

[in]
Flag bits that specify the protection to use for the mapped range. The caller must set one of the following flag bits in the <i>Protect</i> parameter.

<table>
<tr>
<th>Flag bit</th>
<th>Meaning</th>
</tr>
<tr>
<td>PAGE_READONLY</td>
<td>The mapped range can only be read, not written. </td>
</tr>
<tr>
<td>PAGE_READWRITE</td>
<td>The mapped range can be read or written. </td>
</tr>
<tr>
<td>PAGE_EXECUTE</td>
<td>The mapped range can be executed, but not read or written.</td>
</tr>
<tr>
<td>PAGE_EXECUTE_READ</td>
<td>The mapped range can be executed or read, but not written.</td>
</tr>
<tr>
<td>PAGE_EXECUTE_READWRITE</td>
<td>The mapped range can be executed, read, or written. </td>
</tr>
</table>
 

In addition, the caller can set one (but not both) of the following optional flag bits in the <i>Protect</i> parameter.

<table>
<tr>
<th>Flag bit</th>
<th>Meaning</th>
</tr>
<tr>
<td>PAGE_NOCACHE</td>
<td>Specifies non-cached memory.</td>
</tr>
<tr>
<td>PAGE_WRITECOMBINE</td>
<td>Specifies write-combined memory (the memory should not be cached by the processor, but writes to the memory can be combined by the processor).</td>
</tr>
</table>

## -returns

<b>MmMapIoSpaceEx</b> returns the base virtual address that maps the base physical address for the range. If space for mapping the range is insufficient, it returns <b>NULL</b>.

## -remarks

A driver must call this routine during device start-up if it receives translated resources of type <b>CmResourceTypeMemory</b> in a <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_cm_partial_resource_descriptor">CM_PARTIAL_RESOURCE_DESCRIPTOR</a> structure. <b>MmMapIoSpaceEx</b> maps the physical address returned in the resource list to a virtual address through which the driver can access device registers.

For example, drivers of PIO devices that allocate long-term I/O buffers can call this routine to make such buffers accessible or to make device memory accessible.

For more information about using this routine, see <a href="/windows-hardware/drivers/kernel/mapping-bus-relative-addresses-to-virtual-addresses">Mapping Bus-Relative Addresses to Virtual Addresses</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-mmallocatecontiguousmemory">MmAllocateContiguousMemory</a>



<a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-mmallocatenoncachedmemory">MmAllocateNonCachedMemory</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-mmmaplockedpages">MmMapLockedPages</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-mmunmapiospace">MmUnmapIoSpace</a>

