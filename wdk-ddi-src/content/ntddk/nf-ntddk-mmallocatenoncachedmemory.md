---
UID: NF:ntddk.MmAllocateNonCachedMemory
title: MmAllocateNonCachedMemory function (ntddk.h)
description: The MmAllocateNonCachedMemory routine allocates a virtual address range of noncached and cache-aligned memory.
old-location: kernel\mmallocatenoncachedmemory.htm
tech.root: kernel
ms.assetid: aabad72e-2636-47cd-9986-f50ab5101e68
ms.date: 04/30/2018
keywords: ["MmAllocateNonCachedMemory function"]
ms.keywords: MmAllocateNonCachedMemory, MmAllocateNonCachedMemory routine [Kernel-Mode Driver Architecture], k106_a52baa62-3e10-4158-98e5-5e4dce16ee6a.xml, kernel.mmallocatenoncachedmemory, ntddk/MmAllocateNonCachedMemory
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: IrqlMmApcLte, HwStorPortProhibitedDDIs, SpNoWait, StorPortStartIo
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <=APC_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - MmAllocateNonCachedMemory
 - ntddk/MmAllocateNonCachedMemory
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - MmAllocateNonCachedMemory
---

# MmAllocateNonCachedMemory function


## -description

The <b>MmAllocateNonCachedMemory</b> routine allocates a virtual address range of noncached and cache-aligned memory.

## -parameters

### -param NumberOfBytes 

[in]
Specifies the size in bytes of the range to be allocated.

## -returns

If the requested memory cannot be allocated, the return value is <b>NULL</b>. Otherwise, it is the base virtual address of the allocated range.

## -remarks

<b>MmAllocateNonCachedMemory</b> can be called from a <a href="/windows-hardware/drivers/storage/driverentry-of-ide-controller-minidriver">DriverEntry</a> routine to allocate a noncached block of virtual memory for various device-specific buffers. The function always returns a full multiple of the virtual memory page size, of nonpaged system-address-space memory, regardless of the requested allocation size.

Noncached allocations are aligned on an integral multiple of the processor's data-cache-line size to prevent cache and coherency problems.

The physical memory pages that <b>MmAllocateNonCachedMemory</b> returns are typically not contiguous pages.

<div class="alert"><b>Note</b>  Memory that <b>MmAllocateNonCachedMemory</b> allocates is uninitialized. A kernel-mode driver must first zero this memory if it is going to make it visible to user-mode software (to avoid leaking potentially privileged contents).</div>
<div> </div>

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-pallocate_common_buffer">AllocateCommonBuffer</a>



<a href="/windows-hardware/drivers/kernel/mmcreatemdl">KeGetDcacheFillSize</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-mmallocatecontiguousmemory">MmAllocateContiguousMemory</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-mmallocatecontiguousmemoryspecifycache">MmAllocateContiguousMemorySpecifyCache</a>



<a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-mmfreenoncachedmemory">MmFreeNonCachedMemory</a>