---
UID: NC:d3dkmddi.DXGKCB_UNMAPPHYSICALMEMORY
tech.root: display
title: DXGKCB_UNMAPPHYSICALMEMORY
ms.date: 10/13/2021
targetos: Windows
description: The DxgkCbUnmapPhysicalMemory callback function unmaps a CPU-visible virtual address from the underlying physical memory.
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: d3dkmddi.h
req.idl: 
req.include-header: 
req.irql: PASSIVE_LEVEL
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: Windows Server 2022 (WDDM 2.9)
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - LibDef
api_location:
 - d3dkmddi.h
api_name:
 - DXGKCB_UNMAPPHYSICALMEMORY
f1_keywords:
 - DXGKCB_UNMAPPHYSICALMEMORY
 - d3dkmddi/DXGKCB_UNMAPPHYSICALMEMORY
dev_langs:
 - c++
---

## -description

**DXGKCB_UNMAPPHYSICALMEMORY** unmaps a CPU-visible virtual address from the underlying physical memory.

## -parameters

### -param pArgs [in]

Pointer to a [**DXGKARGCB_UNMAP_PHYSICAL_MEMORY**](ns-d3dkmddi-dxgkargcb_unmap_physical_memory.md) structure that contains information about the physical memory object from which the CPU-visible address is being unmapped.

## -remarks

*DXGKCB_XXX* functions are implemented by *Dxgkrnl*. To use this callback function, set the members of [**DXGKARGCB_UNMAP_PHYSICAL_MEMORY**](ns-d3dkmddi-dxgkargcb_unmap_physical_memory.md) and then call **DxgkCbUnmapPhysicalMemory** via the [**DXGKRNL_INTERFACE**](../dispmprt/ns-dispmprt-_dxgkrnl_interface.md).

## -see-also

[**DXGKARGCB_UNMAP_PHYSICAL_MEMORY**](ns-d3dkmddi-dxgkargcb_unmap_physical_memory.md)

[**DXGKCB_MAPPHYSICALMEMORY**](nc-d3dkmddi-dxgkcb_mapphysicalmemory.md)

[**DXGKRNL_INTERFACE**](../dispmprt/ns-dispmprt-_dxgkrnl_interface.md)
