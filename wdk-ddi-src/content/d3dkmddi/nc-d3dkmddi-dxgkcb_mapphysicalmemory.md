---
UID: NC:d3dkmddi.DXGKCB_MAPPHYSICALMEMORY
tech.root: display
title: DXGKCB_MAPPHYSICALMEMORY
ms.date: 06/24/2022
targetos: Windows
description: The DxgkCbMapPhysicalMemory callback function maps CPU-visible virtual addresses to the underlying physical memory.
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
 - DXGKCB_MAPPHYSICALMEMORY
f1_keywords:
 - DXGKCB_MAPPHYSICALMEMORY
 - d3dkmddi/DXGKCB_MAPPHYSICALMEMORY
dev_langs:
 - c++
---

## -description

A kernel-mode display miniport driver calls **DXGKCB_MAPPHYSICALMEMORY** to map CPU-visible virtual addresses to the underlying physical memory.

## -parameters

### -param pArgs [in/out]

Pointer to a [**DXGKARGCB_MAP_PHYSICAL_MEMORY**](ns-d3dkmddi-dxgkargcb_map_physical_memory.md) structure that contains information about the physical memory to map.

## -returns

**DXGKCB_MAPPHYSICALMEMORY** returns STATUS_SUCCESS if the operation succeeds. Otherwise, returns an appropriate NTSTATUS error code.

## -remarks

*DXGKCB_XXX* functions are implemented by *Dxgkrnl*. To use this callback function, set the appropriate members of [**DXGKARGCB_MAP_PHYSICAL_MEMORY**](ns-d3dkmddi-dxgkargcb_map_physical_memory.md) and then call **DxgkCbMapPhysicalMemory** via the [**DXGKRNL_INTERFACE**](../dispmprt/ns-dispmprt-_dxgkrnl_interface.md).

The cache type used for the mappings will be based on the **CacheType** specified when the physical memory object was created in a call to [**DXGKCB_CREATEPHYSICALMEMORYOBJECT**](nc-d3dkmddi-dxgkcb_createphysicalmemoryobject.md).

See [IOMMU DMA remapping](/windows-hardware/drivers/display/iommu-dma-remapping) for more information.

## -see-also

[**DXGKARGCB_MAP_PHYSICAL_MEMORY**](ns-d3dkmddi-dxgkargcb_map_physical_memory.md)

[**DXGKCB_CREATEPHYSICALMEMORYOBJECT**](nc-d3dkmddi-dxgkcb_createphysicalmemoryobject.md)

[**DXGKCB_UNMAPPHYSICALMEMORY**](nc-d3dkmddi-dxgkcb_unmapphysicalmemory.md)

[**DXGKRNL_INTERFACE**](../dispmprt/ns-dispmprt-_dxgkrnl_interface.md)
