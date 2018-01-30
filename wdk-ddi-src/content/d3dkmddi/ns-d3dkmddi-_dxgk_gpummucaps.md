---
UID: NS:d3dkmddi._DXGK_GPUMMUCAPS
title: "_DXGK_GPUMMUCAPS"
author: windows-driver-content
description: The DXGK_GPUMMUCAPS structure is used by the kernel mode driver to express virtual memory addressing capabilities.
old-location: display\dxgk_gpummucaps.htm
old-project: display
ms.assetid: 999820D0-FDEB-49FD-920A-75FD9886492A
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: "_DXGK_GPUMMUCAPS, d3dkmddi/DXGK_GPUMMUCAPS, DXGK_GPUMMUCAPS, DXGK_GPUMMUCAPS structure [Display Devices], display.dxgk_gpummucaps"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dkmddi.h
apiname:
-	DXGK_GPUMMUCAPS
product: Windows
targetos: Windows
req.typenames: DXGK_GPUMMUCAPS
---

# _DXGK_GPUMMUCAPS structure


## -description


The <b>DXGK_GPUMMUCAPS</b> structure is used by the kernel mode driver to express virtual memory addressing capabilities.


## -syntax


````
typedef struct _DXGK_GPUMMUCAPS {
  union {
    struct {
      UINT ReadOnlyMemorySupported  :1;
      UINT NoExecuteMemorySupported  :1;
      UINT ZeroInPteSupported  :1;
      UINT ExplicitPageTableInvalidation  :1;
      UINT CacheCoherentMemorySupported  :1;
      UINT PageTableUpdateRequireAddressSpaceIdle  :1;
      UINT LargePageSupported  :1;
      UINT DualPteSupported  :1;
#if (DXGKDDI_INTERFACE_VERSION >= DXGKDDI_INTERFACE_VERSION_WDDM2_1)
      UINT AllowNonAlignedLargePageAddress  :1;
      UINT Reserved  :23;
    };
    UINT   Value;
  };
  DXGK_PAGETABLEUPDATEMODE PageTableUpdateMode;
  UINT                     VirtualAddressBitCount;
  UINT                     LeafPageTableSizeFor64KPagesInBytes;
  UINT                     PageTableLevelCount;
  struct {
    UINT SourcePageTableVaInTransfer  :1;
    UINT Reserved  :31;
  } LegacyBehaviors;
} DXGK_GPUMMUCAPS;
````


## -struct-fields




### -field LegacyBehaviors



### -field LegacyBehaviors.SourcePageTableVaInTransfer

When set to 1, video memory manager sets <b>SourcePageTable</b> address in <b>TransferVirtual</b> during allocation eviction.


### -field LegacyBehaviors.Reserved

 


### -field ReadOnlyMemorySupported

When set to 1, the driver supports read-only protection on memory pages.


### -field NoExecuteMemorySupported

When set to 1, the driver supports <i>no execute</i> protection on memory pages.


### -field ZeroInPteSupported

When set to 1, the GPU supports the <i>Zero DXGK_PTE</i> flag. This applies to all page table levels.


### -field ExplicitPageTableInvalidation

This flag indicates that all entries of a page table or page directory should be put into an invalid state explicitly, through <b>UpdatePageTable</b> before being freed. By default the video memory manager may free a page table, which contain previously valid entries, if these entries are no longer needed (ex. freeing a large GPU virtual address range resulting in the destruction of underlying page tables).

<div class="alert"><b>Note</b>  This flags is typically used by a software driver that needs to emulate page table and need to keep track of information on a per page table entry basis and require a clear init/deinit pair for all page table entry updates.</div><div> </div>

### -field CacheCoherentMemorySupported

This flag indicates that the driver supports the <i>CacheCoherent</i> bits in the page table entry and can do I/O coherent transfer to system memory. 


### -field PageTableUpdateRequireAddressSpaceIdle

This flag indicates that the GPU doesn’t support updating page table entries or invalidating translation look-aside buffer for an address space that is currently in used by an engine. When this flags is set, video memory manager will ensure that all context sharing the address space are suspended when its page table entries are modified and when translation look-aside buffer is invalidated.


### -field LargePageSupported

When set to 1, all levels of page tables, except the leaf one, support large pages (<b>LargePage</b> bit in <a href="..\d3dukmdt\ns-d3dukmdt-_dxgk_pte.md">DXGK_PTE</a>).


### -field DualPteSupported

When set to 1, the GPU supports two pointers to page tables in the level one page table (4 KB page table and 64 KB page table). 


### -field AllowNonAlignedLargePageAddress

When set to 1, the Operating System is able to set the <b>LargePage</b> flag when the physical address of the large page entry is not aligned to the leaf page table coverage.


### -field SysMem64KBPageSupported

 


### -field Reserved

This member is reserved and should not be used.


### -field Value

The value of the structure expressed as an integer.


### -field PageTableUpdateMode

Defines the type of addresses which are used in <a href="https://msdn.microsoft.com/08328e82-d1cc-4c50-bc96-7382232676ab">DxgkDdiUpdatePageTable</a> operations. When <b>DXGK_PAGETABLEUPDATE_GPU_VIRTUAL</b> is set, all paging operation will occur in the virtual address space of the system context. When page directories are located in a local GPU memory segment, the update mode cannot be set to <b>DXGK_PAGETABLEUPDATE_CPU_VIRTUAL</b>.


### -field VirtualAddressBitCount

The number of bits in the GPU virtual address.


### -field LeafPageTableSizeFor64KPagesInBytes

The size of a leaf page table when 64KB pages are used. The size must be a multiple of CPU page size (4096).


### -field PageTableLevelCount

The number of page table levels supported. The minimum value is 2 (defined as <b>DXGK_MIN_PAGE_TABLE_LEVEL_COUNT</b>). The maximum value is <b>DXGK_MAX_PAGE_TABLE_LEVEL_COUNT</b>. 

When <b>PageTableLevelCount</b> is 2, the root page table is dynamically resizable and the size of the page table is determined through <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_getrootpagetablesize.md">DxgkDdiGetRootPageTableSize</a>. When <b>PageTableLevelCount</b> is greater than 2, all page table levels have a fixed size, which is described through <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_page_table_level_desc.md">DXGK_PAGE_TABLE_LEVEL_DESC</a><b>::PageTableSizeInBytes</b>.

