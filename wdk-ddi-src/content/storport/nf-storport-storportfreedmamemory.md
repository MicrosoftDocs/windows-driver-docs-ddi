---
UID: NF:storport.StorPortFreeDmaMemory
title: StorPortFreeDmaMemory function (storport.h)
description: This function is the extended version of the StorPortFreeContiguousMemorySpecifyCache function. It deallocates a range of noncached memory in the nonpaged portion of the system address space.
tech.root: storage
ms.date: 05/24/2022
keywords: ["StorPortFreeDmaMemory function"]
ms.keywords: StorPortFreeDmaMemory
req.header: storport.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Windows 10 (Version 1803)
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.irql: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
targetos: Windows
f1_keywords:
 - StorPortFreeDmaMemory
 - storport/StorPortFreeDmaMemory
topic_type:
 - apiref
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - StorPortFreeDmaMemory
---

# StorPortFreeDmaMemory function

## -description

This function is the extended version of the [StorPortFreeContiguousMemorySpecifyCache function](./nf-storport-storportfreecontiguousmemoryspecifycache.md). It deallocates a range of noncached memory in the nonpaged portion of the system address space.

## -parameters

### -param HwDeviceExtension [in]

A pointer to the hardware device extension for the host bus adapter (HBA).

### -param BaseAddress [in]

The base virtual address to free.

### -param NumberOfBytes [in]

The number of bytes that are allocated to the request. This must be the same number that was supplied as a parameter when the [StorPortAllocateContiguousMemorySpecifyCacheNode](./nf-storport-storportallocatecontiguousmemoryspecifycachenode.md) routine was previously called.

### -param CacheType [in]

The cache type that is used in the call to the [StorPortAllocateContiguousMemorySpecifyCacheNode](./nf-storport-storportallocatecontiguousmemoryspecifycachenode.md) routine.

### -param PhysicalAddress [in_opt]

The physical address of the starting address of the memory block to be deallocated.

## -returns

This function returns one of the following status codes:

| Return code | Description |
| ----------- | ----------- |
| STOR_STATUS_NOT_IMPLEMENTED | This function is not implemented on the active operating system. |
| STOR_STATUS_SUCCESS         | The operation was successful.                                    |

## -see-also

[**StorPortAllocateContiguousMemorySpecifyCacheNode**](nf-storport-storportallocatecontiguousmemoryspecifycachenode.md)
