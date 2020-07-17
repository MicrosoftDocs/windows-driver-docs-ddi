---
UID: NE:ntifs._RTL_MEMORY_TYPE
title: _RTL_MEMORY_TYPE (ntifs.h)
description: Defines the memory type the heap is supposed to use.
ms.assetid: ba671026-62dc-4e7e-aef4-bd2507d58ecb
tech.root: ifsk
ms.date: 10/19/2018
keywords: ["_RTL_MEMORY_TYPE enumeration"]
f1_keywords:
 - "ntifs/_RTL_MEMORY_TYPE"
 - "_RTL_MEMORY_TYPE"
ms.keywords: _RTL_MEMORY_TYPE, RTL_MEMORY_TYPE, *PRTL_MEMORY_TYPE, 
req.header: ntifs.h
req.include-header:
req.target-type:
req.target- min-winverclnt: Windows 10 (Version 1803)
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.ddi-compliance:
req.max-support:
req.typenames: RTL_MEMORY_TYPE, *PRTL_MEMORY_TYPE
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- ntifs.h
api_name: 
- _RTL_MEMORY_TYPE
product:
- Windows
targetos: Windows
---

# _RTL_MEMORY_TYPE enumeration

## -description

Defines the memory type the heap is supposed to use.

## -enum-fields

### -field MemoryTypePaged 

Specifies the memory type is paged.

### -field MemoryTypeNonPaged 

Specifies the memory type is non-paged.

### -field MemoryTypeLargePage

Specifies the memory type is a large page.
 
### -field MemoryTypeHugePage 

Specifies the memory type is a huge page. Not supported on 32-bit systems.

### -field MemoryTypeMax 


Specifies the memory type is the maximum page size.

## -remarks

## -see-also

[_RTL_SEGMENT_HEAP_MEMORY_SOURCE](ns-ntifs-_rtl_segment_heap_memory_source.md)
