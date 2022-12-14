---
UID: NF:ntddk.MmAllocateNonCachedMemory
title: MmAllocateNonCachedMemory function (ntddk.h)
description: The MmAllocateNonCachedMemory routine allocates a virtual address range of non-cached and cache-aligned memory.
tech.root: kernel
ms.date: 12/07/2022
keywords: ["MmAllocateNonCachedMemory function"]
ms.keywords: MmAllocateNonCachedMemory, MmAllocateNonCachedMemory routine [Kernel-Mode Driver Architecture], k106_a52baa62-3e10-4158-98e5-5e4dce16ee6a.xml, kernel.mmallocatenoncachedmemory, ntddk/MmAllocateNonCachedMemory
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Universal
req.target-min-winverclnt:
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

## -description

The **MmAllocateNonCachedMemory** routine allocates a virtual address range of non-cached and cache-aligned memory.

## -parameters

### -param NumberOfBytes [in]

Specifies the size in bytes of the range to be allocated.

## -returns

If the requested memory cannot be allocated, the return value is **NULL**. Otherwise, it is the base virtual address of the allocated range.

## -remarks

**MmAllocateNonCachedMemory** can be called from a [DriverEntry](/windows-hardware/drivers/storage/driverentry-of-ide-controller-minidriver) routine to allocate a non-cached block of virtual memory for various device-specific buffers. The function always returns a full multiple of the virtual memory page size, of nonpaged system-address-space memory, regardless of the requested allocation size.

Non-cached allocations are aligned on an integral multiple of the processor's data-cache-line size to prevent cache and coherency problems.

The physical memory pages that **MmAllocateNonCachedMemory** returns are typically not contiguous pages.

Memory that **MmAllocateNonCachedMemory** allocates is uninitialized. A kernel-mode driver must first zero this memory if it is going to make it visible to user-mode software (to avoid leaking potentially privileged contents).

## -see-also

[AllocateCommonBuffer](/windows-hardware/drivers/ddi/wdm/nc-wdm-pallocate_common_buffer)

[KeGetDcacheFillSize](/windows-hardware/drivers/kernel/mmcreatemdl)

[MmAllocateContiguousMemory](/windows-hardware/drivers/ddi/wdm/nf-wdm-mmallocatecontiguousmemory)

[MmAllocateContiguousMemorySpecifyCache](/windows-hardware/drivers/ddi/wdm/nf-wdm-mmallocatecontiguousmemoryspecifycache)

[MmFreeNonCachedMemory](/windows-hardware/drivers/ddi/ntddk/nf-ntddk-mmfreenoncachedmemory)
