---
UID: NF:ntddk.MmFreeNonCachedMemory
title: MmFreeNonCachedMemory function (ntddk.h)
description: The MmFreeNonCachedMemory routine releases a range of noncached memory that was allocated by the MmAllocateNonCachedMemory routine.
old-location: kernel\mmfreenoncachedmemory.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["MmFreeNonCachedMemory function"]
ms.keywords: MmFreeNonCachedMemory, MmFreeNonCachedMemory routine [Kernel-Mode Driver Architecture], k106_29c317c1-955e-4d0c-9e65-e1aa511c7a8d.xml, kernel.mmfreenoncachedmemory, ntddk/MmFreeNonCachedMemory
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: IrqlMmApcLte, HwStorPortProhibitedDDIs
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
 - MmFreeNonCachedMemory
 - ntddk/MmFreeNonCachedMemory
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - MmFreeNonCachedMemory
---

# MmFreeNonCachedMemory function


## -description

The <b>MmFreeNonCachedMemory</b> routine releases a range of noncached memory that was allocated by the <a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-mmallocatenoncachedmemory">MmAllocateNonCachedMemory</a> routine.

## -parameters

### -param BaseAddress [in]


Pointer to the virtual address of the memory to be freed.

### -param NumberOfBytes [in]


Specifies the size of the range to be freed. This value must match the size passed in a preceding call to <b>MmAllocateNonCachedMemory</b>.

## -remarks

The <b>MmFreeNonCachedMemory</b> routine performs the opposite action of <a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-mmallocatenoncachedmemory">MmAllocateNonCachedMemory</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-mmallocatenoncachedmemory">MmAllocateNonCachedMemory</a>
