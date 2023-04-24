---
UID: NF:ntddk.PshedAllocateMemory
title: PshedAllocateMemory function (ntddk.h)
description: The PshedAllocateMemory function allocates a block of memory from the nonpaged pool.
tech.root: whea
ms.date: 01/04/2023
keywords: ["PshedAllocateMemory function"]
ms.keywords: PshedAllocateMemory, PshedAllocateMemory function [WHEA Drivers and Applications], ntddk/PshedAllocateMemory, whea.pshedallocatememory, whearef_e18a3aba-ca99-4b65-92de-1c6b8c740e31.xml
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Universal
req.target-min-winverclnt:
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
req.lib: Pshed.lib
req.dll: Pshed.dll
req.irql: IRQL <=DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - PshedAllocateMemory
 - ntddk/PshedAllocateMemory
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Pshed.dll
api_name:
 - PshedAllocateMemory
---

## -description

The **PshedAllocateMemory** function allocates a block of memory from the nonpaged pool.

## -parameters

### -param Size [in]

The size, in bytes, of the block of memory being allocated.

## -returns

**PshedAllocateMemory** returns a pointer to an initialized (nonzero) block of memory from the nonpaged pool or NULL if the memory allocation fails.

## -remarks

A PSHED plug-in calls the **PshedAllocateMemory** function to allocate a block of memory. When the PSHED plug-in is done using the allocated block of memory, it calls the [PshedFreeMemory](./nf-ntddk-pshedfreememory.md) function to free the memory.

If a single PSHED plug-in binary needs to run on versions of Windows prior to Windows 10, version 2004 as well as Windows 10, version 2004 and later and if this binary needs to make other paged or nonpaged pool allocations outside of the **PshedAllocateMemory** APIs then the plugin should use [**ExAllocatePoolUninitialized**](../wdm/nf-wdm-exallocatepooluninitialized.md) or [**ExAllocatePoolZero**](../wdm/nf-wdm-exallocatepoolzero.md) to allocate pool memory. See the note in the Remarks section of the latter page about defining **POOL_ZERO_DOWN_LEVEL_SUPPORT**.

## -see-also

[PshedFreeMemory](./nf-ntddk-pshedfreememory.md)