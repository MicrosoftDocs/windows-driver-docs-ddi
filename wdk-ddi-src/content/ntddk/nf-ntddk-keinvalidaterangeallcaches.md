---
UID: NF:ntddk.KeInvalidateRangeAllCaches
tech.root: kernel
title: KeInvalidateRangeAllCaches function (ntddk.h)
ms.date: 07/27/2022
targetos: Windows
description: The KeInvalidateRangeAllCaches routine flushes the specified virtual address range from all processor caches.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: ntddk.h
req.idl: 
req.include-header: 
req.irql: <= DISPATCH_LEVEL
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Available in Windows Vista and later versions of Windows.
req.target-min-winversvr: Available in Windows Server 2008 and later versions of Windows.
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
 - KeInvalidateRangeAllCaches
f1_keywords:
 - KeInvalidateRangeAllCaches
 - ntddk/KeInvalidateRangeAllCaches
dev_langs:
 - c++
helpviewer_keywords:
 - KeInvalidateRangeAllCaches
---

# KeInvalidateRangeAllCaches function


## -description

The <b>KeInvalidateRangeAllCaches</b> routine flushes the specified virtual address range from all processor caches.

## -parameters

### -param BaseAddress

A pointer to the base of the region to be flushed.

### -param Length

The size of the region to be flushed, in bytes.

## -remarks

The <b>KeInvalidateRangeAllCaches</b> routine flushes the specified virtual address range on each processor's caches and marks each cache's contents invalid. The processor caches are guaranteed to have completed the flush operation before <b>KeInvalidateRangeAllCaches</b> returns.

This function is available on all platforms and supersedes <b><a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-keinvalidateallcaches">KeInvalidateAllCaches</a></b>. Not all architectures, such as Arm64, support a reliable way to flush the entire cache, so <b><a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-keinvalidateallcaches">KeInvalidateAllCaches</a></b> is not available on all platforms. It is also significantly more efficient to flush the particular memory range affected than the entire cache contents.

This function flushes the cache for all virtual mappings of the same underlying physical memory.

## -see-also

<b><a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-keinvalidateallcaches">KeInvalidateAllCaches</a></b>