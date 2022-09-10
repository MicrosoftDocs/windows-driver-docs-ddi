---
UID: NS:ntifs._RTL_HEAP_PARAMETERS
tech.root: ifsk
title: RTL_HEAP_PARAMETERS
ms.date: 07/26/2022
targetos: Windows
description: Learn more about the RTL_HEAP_PARAMETERS structure.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: ntifs.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows XP
req.target-min-winversvr: 
req.target-type: 
req.typenames: RTL_HEAP_PARAMETERS, *PRTL_HEAP_PARAMETERS
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - _RTL_HEAP_PARAMETERS
 - PRTL_HEAP_PARAMETERS
 - RTL_HEAP_PARAMETERS
f1_keywords:
 - _RTL_HEAP_PARAMETERS
 - ntifs/_RTL_HEAP_PARAMETERS
 - PRTL_HEAP_PARAMETERS
 - ntifs/PRTL_HEAP_PARAMETERS
 - RTL_HEAP_PARAMETERS
 - ntifs/RTL_HEAP_PARAMETERS
dev_langs:
 - c++
helpviewer_keywords:
 - _RTL_HEAP_PARAMETERS
---

## -description

The **RTL_HEAP_PARAMETERS** structure contains parameters to be applied when creating a heap.

## -struct-fields

### -field Length

Size, in bytes, of the **RTL_HEAP_PARAMETERS** structure.

### -field SegmentReserve

Segment reserve size, in bytes. If this value is not specified, 1 MB is used.

### -field SegmentCommit

Segment commit size, in bytes. If this value is not specified, PAGE_SIZE * 2 is used.

### -field DeCommitFreeBlockThreshold

Decommit free block threshold, in bytes. If this value is not specified, PAGE_SIZE is used.

### -field DeCommitTotalFreeThreshold

Decommit total free threshold, in bytes. If this value is not specified, 65536 is used.

### -field MaximumAllocationSize

Size, in bytes, of the largest block of memory that can be allocated from the heap. If this value is not specified, the difference between the highest and lowest addresses, less one page, is used.

### -field VirtualMemoryThreshold

Virtual memory threshold, in bytes. If this value is not specified, or if it is greater than the maximum heap block size, the maximum heap block size of 0x7F000 is used.

### -field InitialCommit

Initial amount of memory, in bytes, to commit for the heap. Must be less than or equal to **InitialReserve**. If **HeapBase** and **CommitRoutine** are non-NULL, this parameter, which overrides the value of **CommitSize**, must be a nonzero value; otherwise it is ignored.

### -field InitialReserve

Initial amount of memory, in bytes, to reserve for the heap. If **HeapBase** and **CommitRoutine** are non-NULL, this parameter, which overrides the value of **ReserveSize**, must be a nonzero value; otherwise it is ignored.

### -field CommitRoutine

Pointer to a [**RTL_HEAP_COMMIT_ROUTINE**](nc-ntifs-rtl_heap_commit_routine.md) routine to commit pages from the heap. If this parameter is non-NULL, the heap must be nongrowable. If **HeapBase** is NULL, **CommitRoutine** must also be NULL.

### -field Reserved

Reserved for system use. Drivers must set this parameter to zero.

## -see-also

[**RTL_HEAP_COMMIT_ROUTINE**](nc-ntifs-rtl_heap_commit_routine.md)
[**RtlCreateHeap**](nf-ntifs-rtlcreateheap.md)
