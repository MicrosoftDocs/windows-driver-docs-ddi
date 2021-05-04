---
UID: NE:d3dkmddi._DXGK_ACCESS_MODE
tech.root: display
title: DXGK_ACCESS_MODE
ms.date: 05/13/2021
ms.topic: language-reference
targetos: Windows
description: DXGK_ACCESS_MODE describes the access mode that DxgkCbMapPhysicalMemory should provide when doing a mapping.
req.construct-type: enumeration
req.ddi-compliance: 
req.header: d3dkmddi.h
req.include-header: 
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: 
req.target-min-winversvr: Windows Server 2022
req.target-type: 
req.typenames: 
req.umdf-ver: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGK_ACCESS_MODE
 - DXGK_ACCESS_MODE
f1_keywords:
 - _DXGK_ACCESS_MODE
 - d3dkmddi/_DXGK_ACCESS_MODE
 - DXGK_ACCESS_MODE
 - d3dkmddi/DXGK_ACCESS_MODE
dev_langs:
 - c++
---

## -description

**DXGK_ACCESS_MODE** describes the access mode that [**DxgkCbMapPhysicalMemory**](nc-d3dkmddi-dxgkcb_mapphysicalmemory.md) will provide when doing a mapping.

## -enum-fields

### -field DXGK_ACCESS_MODE_KERNEL_MODE

The resulting mapping will be a kernel-mode virtual address. If the **hPhysicalMemoryObject** returned by [**DxgkCbCreatePhysicalMemoryObject**](nc-d3dkmddi-dxgkcb_createphysicalmemoryobject.md) is of type **DXGK_PHYSICAL_MEMORY_TYPE_IO_SPACE**, then **AccessMode** must be KernelMode.

### -field DXGK_ACCESS_MODE_USER_MODE

The resulting mapping will be made in the context of the current process. The caller is expected to be in the context of the correct process during both map and unmap.

## -remarks

**DXGK_ACCESS_MODE** is provided in the [**DXGKARGCB_MAP_PHYSICAL_MEMORY**](ns-d3dkmddi-dxgkargcb_map_physical_memory.md) structure that is passed to [**DxgkCbMapPhysicalMemory**](nc-d3dkmddi-dxgkcb_mapphysicalmemory.md).

## -see-also

[**DXGKARGCB_MAP_PHYSICAL_MEMORY**](ns-d3dkmddi-dxgkargcb_map_physical_memory.md)

[**DxgkCbCreatePhysicalMemoryObject**](nc-d3dkmddi-dxgkcb_createphysicalmemoryobject.md)

[**DxgkCbMapPhysicalMemory**](nc-d3dkmddi-dxgkcb_mapphysicalmemory.md)

[**DxgkCbUnmapPhysicalMemory**](nc-d3dkmddi-dxgkcb_unmapphysicalmemory.md)
