---
UID: NC:dispmprt.DXGKCB_AGP_ALLOCATE_POOL
title: DXGKCB_AGP_ALLOCATE_POOL (dispmprt.h)
description: The AgpAllocatePool function reserves, commits, and maps AGP memory.
old-location: display\agpallocatepool.htm
tech.root: display
ms.date: 05/31/2022
keywords: ["DXGKCB_AGP_ALLOCATE_POOL callback function"]
ms.keywords: AgpAllocatePool, AgpAllocatePool callback function [Display Devices], DXGKCB_AGP_ALLOCATE_POOL, DXGKCB_AGP_ALLOCATE_POOL callback, DpFunctions_2bd4981c-c9f1-4b37-a921-9eb33d1b622b.xml, display.agpallocatepool, dispmprt/AgpAllocatePool
req.header: dispmprt.h
req.include-header: Dispmprt.h
req.target-type: Desktop
req.target-min-winverclnt: Windows Vista
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
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - DXGKCB_AGP_ALLOCATE_POOL
 - dispmprt/DXGKCB_AGP_ALLOCATE_POOL
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - dispmprt.h
api_name:
 - DXGKCB_AGP_ALLOCATE_POOL
---

# DXGKCB_AGP_ALLOCATE_POOL callback function

## -description

The **DXGKCB_AGP_ALLOCATE_POOL** callback function reserves, commits, and maps Accelerated Graphics Port (AGP) memory.

## -parameters

### -param Context [in]

A handle to a context block associated with an AGP interface. The display miniport driver previously received this handle in the **Context** member of the DXGK_AGP_INTERFACE structure that was filled in by [**DxgkCbQueryServices**](nc-dispmprt-dxgkcb_query_services.md).

### -param AllocationSize [in]

The size, in bytes, of the AGP memory to be allocated.

### -param CacheType [in]

A constant from the [**MEMORY_CACHING_TYPE**](../wdm/ne-wdm-_memory_caching_type.md) enumeration that specifies whether the CPU can use caching or write combining when it accesses the allocated AGP memory.

### -param PhysicalAddress [out]

A pointer to a PHYSICAL_ADDRESS structure that receives the base physical address of the AGP allocation. This is the base of the physical address range that the GPU will use to access the AGP memory.

### -param VirtualAddress [out]

A pointer to a variable that receives the base virtual address, in system space, of the AGP allocation. This is the base of the virtual address range that the CPU will use to access the AGP memory.

## -returns

**AgpAllocatePool** returns STATUS_SUCCESS if it succeeds. Otherwise, it returns one of the error codes defined in *Ntstatus.h*.

## -remarks

Call **AgpAllocatePool** in the display miniport driver's [**DxgkDdiStartDevice**](nc-dispmprt-dxgkddi_start_device.md) function. It is likely that **AgpAllocatePool** will fail if you call it after **DxgkDdiStartDevice** has executed.

## -see-also

[**AgpFreePool**](nc-dispmprt-dxgkcb_agp_free_pool.md)

[**AgpSetCommand**](nc-dispmprt-dxgkcb_agp_set_command.md)

[**DXGK_AGP_INTERFACE**](ns-dispmprt-_dxgk_agp_interface.md)

[**DxgkCbQueryServices**](nc-dispmprt-dxgkcb_query_services.md)
