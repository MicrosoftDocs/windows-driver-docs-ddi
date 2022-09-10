---
UID: NE:ntifs._RTL_MEMORY_TYPE
title: RTL_MEMORY_TYPE (ntifs.h)
description: Defines the memory type the heap is supposed to use.
tech.root: ifsk
ms.date: 05/24/2022
keywords: ["RTL_MEMORY_TYPE enumeration"]
ms.keywords: _RTL_MEMORY_TYPE, RTL_MEMORY_TYPE, *PRTL_MEMORY_TYPE,
req.header: ntifs.h
req.include-header: 
req.target-type: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.max-support: 
req.typenames: RTL_MEMORY_TYPE, *PRTL_MEMORY_TYPE
targetos: Windows
f1_keywords:
 - _RTL_MEMORY_TYPE
 - ntifs/_RTL_MEMORY_TYPE
 - PRTL_MEMORY_TYPE
 - ntifs/PRTL_MEMORY_TYPE
 - RTL_MEMORY_TYPE
 - ntifs/RTL_MEMORY_TYPE
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - _RTL_MEMORY_TYPE
 - PRTL_MEMORY_TYPE
 - RTL_MEMORY_TYPE
---

# RTL_MEMORY_TYPE enumeration

## -description

Defines the memory type the heap is supposed to use.

## -enum-fields

### -field MemoryTypePaged

The memory type is paged.

### -field MemoryTypeNonPaged

The memory type is non-paged.

### -field MemoryTypeLargePage

The memory type is a large page.

### -field MemoryTypeHugePage

The memory type is a huge page. Not supported on 32-bit systems.

### -field MemoryTypeCustom

The memory type is a custom memory type.

### -field MemoryTypeMax

Maximum value for this enumeration.

## -see-also

[**RTL_SEGMENT_HEAP_MEMORY_SOURCE**](ns-ntifs-_rtl_segment_heap_memory_source.md)
