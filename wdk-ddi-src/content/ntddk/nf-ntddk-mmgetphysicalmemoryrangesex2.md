---
UID: NF:ntddk.MmGetPhysicalMemoryRangesEx2
title: MmGetPhysicalMemoryRangesEx2
tech.root: kernel
ms.date: 03/01/2020
ms.keywords: MmGetPhysicalMemoryRangesEx2
ms.topic: language-reference
targetos: Windows
product: Windows
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: ntddk.h
req.idl: 
req.include-header: 
req.irql: PASSIVE_LEVEL
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Windows 10, version 2004
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - 
api_location:
 - ntddk.h
api_name:
 - MmGetPhysicalMemoryRangesEx2
f1_keywords:
 - ntddk//MmGetPhysicalMemoryRangesEx2
 - MmGetPhysicalMemoryRangesEx2
dev_langs:
 - c++
---

## -description

 This routine returns the virtual address of a nonpaged pool block which contains the physical memory ranges in the system.

    

## -parameters

### -param PartitionObject

Optional pointer to the partition object to query.

### -param Flags

Whether the caller is interested in FileOnly ranges, and whether to include all partitions.

## -returns

NULL on failure.

## -remarks

The returned block contains physical address and page count pairs. The last entry contains zero for both.

The caller must understand that although the returned block cannot change after it is returned, the actual memory configuration can change (due to hot-add/remove) at any time.

It is the caller's responsibility to free this block.

## -see-also

