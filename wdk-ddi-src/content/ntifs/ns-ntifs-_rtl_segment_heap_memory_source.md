---
UID: NS:ntifs._RTL_SEGMENT_HEAP_MEMORY_SOURCE
title: _RTL_SEGMENT_HEAP_MEMORY_SOURCE
author: windows-driver-content
description: The RTL_SEGMENT_HEAP_MEMORY_SOURCE structure specifies the segment heap memory source.
ms.assetid: ff6415d1-6ded-4470-99c7-2825c1d01cb3
ms.date: 10/19/2018
ms.topic: struct
ms.keywords: _RTL_SEGMENT_HEAP_MEMORY_SOURCE, RTL_SEGMENT_HEAP_MEMORY_SOURCE, *PRTL_SEGMENT_HEAP_MEMORY_SOURCE, 
req.header: ntifs.h
req.include-header:
req.target-type:
req.target- min-winverclnt: Windows 10 (Version 1803)
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.typenames: RTL_SEGMENT_HEAP_MEMORY_SOURCE, *PRTL_SEGMENT_HEAP_MEMORY_SOURCE
topic_type: 
-	apiref
api_type: 
-	HeaderDef
api_location: 
-	ntifs.h
api_name: 
-	_RTL_SEGMENT_HEAP_MEMORY_SOURCE
product:
-	Windows
targetos: Windows
---

# _RTL_SEGMENT_HEAP_MEMORY_SOURCE structure

The **RTL_SEGMENT_HEAP_MEMORY_SOURCE** structure specifies the segment heap memory source.

## -description


## -struct-fields

### -field Flags

The flags associated with the segment heap.


### -field MemoryTypeMask
 
Contains a mask of the [RTL_MEMORY_TYPE](ne-ntifs-_rtl_memory_type.md) members.

### -field NumaNode
Specifies the number of the NUMA node the memory resides on.

### -field PartitionHandle

Handle to the specified partition.

### -field Reserved
Reserved for future use.

## -remarks

## -see-also
