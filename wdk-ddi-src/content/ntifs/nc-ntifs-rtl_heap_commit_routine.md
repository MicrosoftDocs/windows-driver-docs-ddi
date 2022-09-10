---
UID: NC:ntifs.RTL_HEAP_COMMIT_ROUTINE
tech.root: ifsk
title: RTL_HEAP_COMMIT_ROUTINE
ms.date: 07/26/2022
targetos: Windows
description: Learn more about the RTL_HEAP_COMMIT_ROUTINE callback routine.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: ntifs.h
req.idl: 
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Windows XP
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - LibDef
api_location:
 - ntifs.h
api_name:
 - RTL_HEAP_COMMIT_ROUTINE
f1_keywords:
 - RTL_HEAP_COMMIT_ROUTINE
 - ntifs/RTL_HEAP_COMMIT_ROUTINE
dev_langs:
 - c++
helpviewer_keywords:
 - RTL_HEAP_COMMIT_ROUTINE
---

## -description

A **RTL_HEAP_COMMIT_ROUTINE** callback routine commits pages from the heap.

## -parameters

### -param Base

Base address for the block of caller-allocated memory being used for the heap.

### -param CommitAddress

Pointer to a variable that will receive the base address of the committed region of pages.

### -param CommitSize

Pointer to a variable that will receive the actual size, in bytes, of the allocated region of pages.

## -returns

**RTL_HEAP_COMMIT_ROUTINE** returns STATUS_SUCCESS or an appropriate error status.

## -see-also

[**RtlCreateHeap**](nf-ntifs-rtlcreateheap.md)

[**RTL_HEAP_PARAMETERS**](ns-ntifs-rtl_heap_parameters.md)
