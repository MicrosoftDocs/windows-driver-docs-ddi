---
UID: NF:wdm.MmAllocateMappingAddress
title: MmAllocateMappingAddress function (wdm.h)
description: The MmAllocateMappingAddress routine reserves a range of system virtual address space of the specified size.
tech.root: kernel
ms.date: 08/29/2025
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Windows XP
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <=APC_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - MmAllocateMappingAddress
 - wdm/MmAllocateMappingAddress
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - MmAllocateMappingAddress
---

# MmAllocateMappingAddress function

## -description

The **MmAllocateMappingAddress** routine reserves a range of system virtual address space of the specified size.

## -parameters

### -param NumberOfBytes [in]

Specifies the number of bytes to reserve.

### -param PoolTag [in]

Specifies a four-character tag used to identify the buffer. Use a distinct **PoolTag** tag for each allocation code path. For a description of pool tags, see [**ExAllocatePoolWithTag**](nf-wdm-exallocatepoolwithtag.md).

## -returns

**MmAllocateMappingAddress** returns a pointer to the beginning of the reserved memory buffer if the operation is successful; otherwise, it returns NULL.

## -remarks

**MmAllocateMappingAddress** reserves a system virtual address range for the caller to use. No physical memory is allocated for the virtual address range and the virtual memory can't be accessed until it is mapped by the [**MmMapLockedPagesWithReservedMapping**](nf-wdm-mmmaplockedpageswithreservedmapping.md) routine. The caller unmaps the reserved memory range by calling the [**MmUnmapReservedMapping**](nf-wdm-mmunmapreservedmapping.md) routine. Finally, the caller can free the reserved range by calling [**MmFreeMappingAddress**](nf-wdm-mmfreemappingaddress.md).

## -see-also

[**MmAllocateMappingAddressEx**](nf-wdm-mmallocatemappingaddressex.md)

[**MmFreeMappingAddress**](nf-wdm-mmfreemappingaddress.md)

[**MmMapLockedPagesWithReservedMapping**](nf-wdm-mmmaplockedpageswithreservedmapping.md)

[**MmUnmapReservedMapping**](nf-wdm-mmunmapreservedmapping.md)
