---
UID: NC:d3dkmddi.DXGKCB_MAPPHYSICALMEMORY
tech.root: display
title: DXGKCB_MAPPHYSICALMEMORY
ms.date: 05/13/2021
targetos: Windows
description: The DxgkCbMapPhysicalMemory callback function maps CPU-visible virtual addresses to the underlying physical memory.
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: d3dkmddi.h
req.idl: 
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: Windows Server 2022
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

The **DxgkCbMapPhysicalMemory** callback function maps CPU-visible virtual addresses to the underlying physical memory.

## -parameters

### -param pArgs

Pointer to a [**DXGKARGCB_MAP_PHYSICAL_MEMORY**](ns-d3dkmddi-dxgkargcb_map_physical_memory.md) structure that contains information about the physical memory to map.

## -returns

Returns STATUS_SUCCESS if the operation succeeds. Otherwise, returns an appropriate NTSTATUS error code.

## -prototype

```cpp
//Declaration

DXGKCB_MAPPHYSICALMEMORY DxgkCbMapPhysicalMemory;

// Definition

NTSTATUS
DxgkCbMapPhysicalMemory(
    DXGKARGCB_MAP_PHYSICAL_MEMORY *Args
    );
{...}

```

## -remarks

The cache type used for the mappings will be based on the **CacheType** specified when the physical memory object was created in a call to [**DxgkCbCreatePhysicalMemoryObject**](nc-d3dkmddi-dxgkcb_createphysicalmemoryobject.md).

## -see-also

[**DXGKARGCB_MAP_PHYSICAL_MEMORY**](ns-d3dkmddi-dxgkargcb_map_physical_memory.md)

[**DxgkCbCreatePhysicalMemoryObject**](nc-d3dkmddi-dxgkcb_createphysicalmemoryobject.md)

[**DxgkCbUnmapPhysicalMemory**](nc-d3dkmddi-dxgkcb_unmapphysicalmemory.md)
