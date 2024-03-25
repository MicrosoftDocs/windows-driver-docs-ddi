---
UID: NS:d3dkmddi._DXGK_GPUMMUCAPS
title: DXGK_GPUMMUCAPS (d3dkmddi.h)
description: The DXGK_GPUMMUCAPS structure is used by the kernel mode driver to express virtual memory addressing capabilities.
old-location: display\dxgk_gpummucaps.htm
ms.date: 08/24/2022
keywords: ["DXGK_GPUMMUCAPS structure"]
ms.keywords: DXGK_GPUMMUCAPS, DXGK_GPUMMUCAPS structure [Display Devices], _DXGK_GPUMMUCAPS, d3dkmddi/DXGK_GPUMMUCAPS, display.dxgk_gpummucaps
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
tech.root: display
req.typenames: DXGK_GPUMMUCAPS
ms.custom: 19H1
f1_keywords:
 - _DXGK_GPUMMUCAPS
 - d3dkmddi/_DXGK_GPUMMUCAPS
 - DXGK_GPUMMUCAPS
 - d3dkmddi/DXGK_GPUMMUCAPS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGK_GPUMMUCAPS
 - DXGK_GPUMMUCAPS
dev_langs:
 - c++
---

# DXGK_GPUMMUCAPS structure

## -description

The **DXGK_GPUMMUCAPS** structure is used by the kernel-mode driver to express virtual memory addressing capabilities.

## -struct-fields

### -field ReadOnlyMemorySupported

When set to 1, the driver supports read-only protection on memory pages.

### -field NoExecuteMemorySupported

When set to 1, the driver supports *no execute* protection on memory pages.

### -field ZeroInPteSupported

When set to 1, the GPU supports the *Zero DXGK_PTE* flag. This applies to all page table levels.

### -field ExplicitPageTableInvalidation

Indicates that all entries of a page table or page directory should be put into an invalid state explicitly, through **UpdatePageTable** before being freed. By default the video memory manager may free a page table, which contain previously valid entries, if these entries are no longer needed (ex. freeing a large GPU virtual address range resulting in the destruction of underlying page tables).

> [!NOTE]
> This flags is typically used by a software driver that needs to emulate page table and need to keep track of information on a per page table entry basis and require a clear init/deinit pair for all page table entry updates.

### -field CacheCoherentMemorySupported

Indicates that the driver supports the *CacheCoherent* bits in the page table entry and can do I/O coherent transfer to system memory.

### -field PageTableUpdateRequireAddressSpaceIdle

Indicates that the GPU doesn’t support updating page table entries or invalidating translation look-aside buffer for an address space that is currently in used by an engine. When this flags is set, video memory manager will ensure that all context sharing the address space are suspended when its page table entries are modified and when translation look-aside buffer is invalidated.

### -field LargePageSupported

When set to 1, all levels of page tables, except the leaf one, support large pages (**LargePage** bit in [**DXGK_PTE**](../d3dukmdt/ns-d3dukmdt-_dxgk_pte.md)).

### -field DualPteSupported

When set to 1, the GPU supports two pointers to page tables in the level one page table (4 KB page table and 64 KB page table).

### -field AllowNonAlignedLargePageAddress

When set to 1, the Operating System is able to set the **LargePage** flag when the physical address of the large page entry is not aligned to the leaf page table coverage. Available starting in Windows 10 version 1607 (WDDM 2.1).

### -field SysMem64KBPageSupported

The driver provides memory segment management at 64KB. Available starting in Windows 10 version 1607 (WDDM 2.1).

### -field InvalidTlbEntriesNotCached

When this bit is set, the driver will not receive calls to [**DxgkDdiBuildPagingBuffer**](nc-d3dkmddi-dxgkddi_buildpagingbuffer.md) for FlushTlb requests for VA ranges that are transitioning from an invalid to valid state. It is expected that the hardware’s TLB does not cache invalid translations

Available starting in Windows 10 version 1903 (WDDM 2.6).

### -field SysMemLargePageSupported

The driver provides large-page support. Available starting in Windows Server 2022 (WDDM 2.9).

### -field CachedPageTables

Cached page tables are supported. Available starting in WDDM 3.1.

### -field Reserved

Reserved for system use; don't use.

### -field Value

The value of the union's structure expressed as an integer.

### -field PageTableUpdateMode

Defines the type of addresses that are used in [**DxgkDdiUpdatePageTable**](/windows-hardware/drivers/display/dxgkddiupdatepagetable) operations. When **DXGK_PAGETABLEUPDATE_GPU_VIRTUAL** is set, all paging operation will occur in the virtual address space of the system context. When page directories are located in a local GPU memory segment, the update mode cannot be set to **DXGK_PAGETABLEUPDATE_CPU_VIRTUAL**.

### -field VirtualAddressBitCount

The number of bits in the GPU virtual address.

### -field LeafPageTableSizeFor64KPagesInBytes

The size of a leaf page table when 64KB pages are used. The size must be a multiple of CPU page size (4096).

### -field PageTableLevelCount

The number of page table levels supported. The minimum value is 2 (defined as **DXGK_MIN_PAGE_TABLE_LEVEL_COUNT**). The maximum value is **DXGK_MAX_PAGE_TABLE_LEVEL_COUNT**.

When **PageTableLevelCount** is 2, the root page table is dynamically resizable and the size of the page table is determined through [**DxgkDdiGetRootPageTableSize**](nc-d3dkmddi-dxgkddi_getrootpagetablesize.md). When **PageTableLevelCount** is greater than 2, all page table levels have a fixed size, which is described through [**DXGK_PAGE_TABLE_LEVEL_DESC**](ns-d3dkmddi-_dxgk_page_table_level_desc.md)**::PageTableSizeInBytes**.

### -field LegacyBehaviors

### -field LegacyBehaviors.SourcePageTableVaInTransfer

When set to 1, video memory manager sets **SourcePageTable** address in **TransferVirtual** during allocation eviction.

### -field LegacyBehaviors.Reserved

Reserved; do not use.
