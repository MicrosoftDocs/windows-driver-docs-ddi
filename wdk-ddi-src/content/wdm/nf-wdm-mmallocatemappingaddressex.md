---
UID: NF:wdm.MmAllocateMappingAddressEx
title: MmAllocateMappingAddressEx function
description: The MmAllocateMappingAddressEx function allocates a system PTE mapping of the requested length that can be used later to map arbitrary addresses.
tech.root: kernel
ms.date: 08/29/2025
ms.keywords: MmAllocateMappingAddressEx
req.header: wdm.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 2004
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.irql: <= APC_LEVEL
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
targetos: Windows
topic_type:
 - apiref
api_type:
 - DllExport
api_location:
 - wdm.h
api_name:
 - MmAllocateMappingAddressEx
f1_keywords:
 - MmAllocateMappingAddressEx
 - wdm/MmAllocateMappingAddressEx
---

# MmAllocateMappingAddressEx function

## -description

The **MmAllocateMappingAddressEx** function allocates a system PTE mapping of the requested length that can be used later to map arbitrary addresses.

## -parameters

### -param NumberOfBytes [in]

Supplies the maximum number of bytes the mapping can span.

### -param PoolTag [in]

Specifies a four-character tag used to identify the buffer. Use a distinct **PoolTag** tag for each allocation code path. For a description of pool tags, see [**ExAllocatePoolWithTag**](nf-wdm-exallocatepoolwithtag.md).

### -param Flags [in]

Specifies flags for this operation. Set this parameter to zero or to the bitwise-OR of one or more of the following flag bits:

| Flag | Meaning |
| ---- | ------- |
| MM_MAPPING_ADDRESS_DIVISIBLE | Indicates that the mapping address must be divisible by the size of the mapping. This flag is useful for ensuring that the mapping address aligns with certain hardware requirements. |

## -returns

**MmAllocateMappingAddressEx** returns a pointer to the beginning of the reserved memory buffer if the operation is successful; otherwise, it returns NULL.

## -remarks

**MmAllocateMappingAddressEx** provides an extended version of [**MmAllocateMappingAddress**](nf-wdm-mmallocatemappingaddress.md) with additional flag support. This function reserves a range of system virtual address space that can be used for later mapping operations with [**MmMapLockedPagesWithReservedMapping**](nf-wdm-mmmaplockedpageswithreservedmapping.md).

No physical memory is allocated by this function; it only reserves virtual address space. The reserved memory can't be accessed until it is mapped using [**MmMapLockedPagesWithReservedMapping**](nf-wdm-mmmaplockedpageswithreservedmapping.md).

Callers must provide a non-zero **PoolTag** to identify the allocation.

The reserved address range should be freed using [**MmFreeMappingAddress**](nf-wdm-mmfreemappingaddress.md) when no longer needed.

Very large allocations (>= 4GB pages) will fail. The function might fail if insufficient system PTEs are available

## -see-also

[**MmAllocateMappingAddress**](nf-wdm-mmallocatemappingaddress.md)

[**MmFreeMappingAddress**](nf-wdm-mmfreemappingaddress.md)

[**MmMapLockedPagesWithReservedMapping**](nf-wdm-mmmaplockedpageswithreservedmapping.md)

[**MmUnmapReservedMapping**](nf-wdm-mmunmapreservedmapping.md)
