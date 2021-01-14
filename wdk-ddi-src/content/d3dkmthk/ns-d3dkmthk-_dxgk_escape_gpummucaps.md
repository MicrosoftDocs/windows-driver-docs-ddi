---
UID: NS:d3dkmthk._DXGK_ESCAPE_GPUMMUCAPS
title: _DXGK_ESCAPE_GPUMMUCAPS (d3dkmthk.h)
description: The GPU memory management capabilities.
ms.date: 10/19/2018
keywords: ["DXGK_ESCAPE_GPUMMUCAPS structure"]
ms.keywords: _DXGK_ESCAPE_GPUMMUCAPS, DXGK_ESCAPE_GPUMMUCAPS,
req.header: d3dkmthk.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.ddi-compliance: 
req.unicode-ansi: 
req.max-support: 
req.typenames: DXGK_ESCAPE_GPUMMUCAPS
targetos: Windows
ms.custom: RS5
tech.root: display
f1_keywords:
 - _DXGK_ESCAPE_GPUMMUCAPS
 - d3dkmthk/_DXGK_ESCAPE_GPUMMUCAPS
 - DXGK_ESCAPE_GPUMMUCAPS
 - d3dkmthk/DXGK_ESCAPE_GPUMMUCAPS
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmthk.h
api_name:
 - _DXGK_ESCAPE_GPUMMUCAPS
 - DXGK_ESCAPE_GPUMMUCAPS
dev_langs:
 - c++
---

# _DXGK_ESCAPE_GPUMMUCAPS structure


## -description

The GPU memory management capabilities.

## -struct-fields

### -field ReadOnlyMemorySupported

Read-only memory is supported.

### -field NoExecuteMemorySupported

No execute memory is supported.

### -field ZeroInPteSupported

### -field CacheCoherentMemorySupported

Cache coherent memory is supported.

### -field LargePageSupported

When set to 1, all levels of page tables, except the leaf one, support large pages (LargePage bit in [DXGK_PTE](../d3dukmdt/ns-d3dukmdt-_dxgk_pte.md)).

### -field DualPteSupported

When set to 1, the GPU supports two pointers to page tables in the level one page table (4 KB page table and 64 KB page table).

### -field AllowNonAlignedLargePageAddress

When set to 1, the Operating System is able to set the **LargePage** flag when the physical address of the large page entry is not aligned to the leaf page table coverage.

### -field VirtualAddressBitCount

The virtual address bit count.

### -field PageTableLevelCount

The number of page table levels supported.

### -field PageTableLevelDesk

 
The page table level descriptions.

## -remarks

## -see-also

