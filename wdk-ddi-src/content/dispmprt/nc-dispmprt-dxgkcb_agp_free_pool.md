---
UID: NC:dispmprt.DXGKCB_AGP_FREE_POOL
title: DXGKCB_AGP_FREE_POOL (dispmprt.h)
description: The AgpFreePool function frees AGP memory that was previously allocated by AgpAllocatePool.
old-location: display\agpfreepool.htm
tech.root: display
ms.date: 05/31/2022
keywords: ["DXGKCB_AGP_FREE_POOL callback function"]
ms.keywords: AgpFreePool, AgpFreePool callback function [Display Devices], DXGKCB_AGP_FREE_POOL, DXGKCB_AGP_FREE_POOL callback, DpFunctions_ffe16de5-aa04-4f4b-bae5-de5b25682f65.xml, display.agpfreepool, dispmprt/AgpFreePool
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
 - DXGKCB_AGP_FREE_POOL
 - dispmprt/DXGKCB_AGP_FREE_POOL
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - dispmprt.h
api_name:
 - DXGKCB_AGP_FREE_POOL
---

# DXGKCB_AGP_FREE_POOL callback function

## -description

The **DXGKCB_AGP_FREE_POOL** callback function frees AGP memory that was previously allocated by [**AgpAllocatePool**](nc-dispmprt-dxgkcb_agp_allocate_pool.md).

## -parameters

### -param Context [in]

A handle to a context block that is associated with an AGP interface. The display miniport driver previously received this handle in the **Context** member of the DXGK_AGP_INTERFACE structure that was filled in by [**DxgkCbQueryServices**](nc-dispmprt-dxgkcb_query_services.md).

### -param VirtualAddress [in]

The base virtual address of the AGP allocation that is to be freed. This is the virtual address that was previously returned in the **VirtualAddress** output parameter of the [**AgpAllocatePool**](nc-dispmprt-dxgkcb_agp_allocate_pool.md) function.

## -returns

**AgpFreePool** returns STATUS_SUCCESS if it succeeds. Otherwise, it returns one of the error codes defined in *Ntstatus.h*.

## -remarks

None.

## -see-also

[**AgpAllocatePool**](nc-dispmprt-dxgkcb_agp_allocate_pool.md)

[**AgpSetCommand**](nc-dispmprt-dxgkcb_agp_set_command.md)

[**DXGK_AGP_INTERFACE**](ns-dispmprt-_dxgk_agp_interface.md)

[**DxgkCbQueryServices**](nc-dispmprt-dxgkcb_query_services.md)
