---
UID: NS:d3dkmddi._DXGKARGCB_UNMAP_PHYSICAL_MEMORY
tech.root: display
title: DXGKARGCB_UNMAP_PHYSICAL_MEMORY
ms.date: 10/13/2021
targetos: Windows
description: The DXGKARGCB_UNMAP_PHYSICAL_MEMORY structure contains information about the physical memory object from which the CPU-visible addresses are being unmapped by the DxgkCbUnmapPhysicalMemory callback function.
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: d3dkmddi.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: Windows Server 2022 (WDDM 2.9)
req.target-type: 
req.typenames: DXGKARGCB_UNMAP_PHYSICAL_MEMORY
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGKARGCB_UNMAP_PHYSICAL_MEMORY
 - DXGKARGCB_UNMAP_PHYSICAL_MEMORY
f1_keywords:
 - _DXGKARGCB_UNMAP_PHYSICAL_MEMORY
 - d3dkmddi/_DXGKARGCB_UNMAP_PHYSICAL_MEMORY
 - DXGKARGCB_UNMAP_PHYSICAL_MEMORY
 - d3dkmddi/DXGKARGCB_UNMAP_PHYSICAL_MEMORY
dev_langs:
 - c++
---

## -description

The **DXGKARGCB_UNMAP_PHYSICAL_MEMORY** structure contains information about the physical memory object from which the CPU-visible address is being unmapped by the [**DXGKCB_UNMAPPHYSICALMEMORY**](nc-d3dkmddi-dxgkcb_unmapphysicalmemory.md) callback function.

## -struct-fields

### -field hPhysicalMemoryObject

The physical memory object from which the CPU-visible address is being unmapped.

### -field pBaseAddress

The base address returned from [**DXGKCB_MAPPHYSICALMEMORY**](nc-d3dkmddi-dxgkcb_mapphysicalmemory.md) that is being unmapped.

### -field Size

The size, in bytes, of the mapped region. This should match the mapped **Size** parameter that was output from the corresponding map call.

## -see-also

[**DXGKCB_MAPPHYSICALMEMORY**](nc-d3dkmddi-dxgkcb_mapphysicalmemory.md)

[**DXGKCB_UNMAPPHYSICALMEMORY**](nc-d3dkmddi-dxgkcb_unmapphysicalmemory.md)
