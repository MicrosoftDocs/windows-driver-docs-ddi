---
UID: NS:d3dkmddi._DXGKARGCB_MAP_PHYSICAL_MEMORY
tech.root: display
title: DXGKARGCB_MAP_PHYSICAL_MEMORY
ms.date: 10/13/2021
targetos: Windows
description: The DXGKARGCB_MAP_PHYSICAL_MEMORY structure contains the information used by the DxgkCbMapPhysicalMemory callback function to map CPU-visible virtual addresses to the underlying physical memory.
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
req.typenames: DXGKARGCB_MAP_PHYSICAL_MEMORY
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGKARGCB_MAP_PHYSICAL_MEMORY
 - DXGKARGCB_MAP_PHYSICAL_MEMORY
f1_keywords:
 - _DXGKARGCB_MAP_PHYSICAL_MEMORY
 - d3dkmddi/_DXGKARGCB_MAP_PHYSICAL_MEMORY
 - DXGKARGCB_MAP_PHYSICAL_MEMORY
 - d3dkmddi/DXGKARGCB_MAP_PHYSICAL_MEMORY
dev_langs:
 - c++
---

## -description

The **DXGKARGCB_MAP_PHYSICAL_MEMORY** structure contains the information used by the [**DXGKCB_MAPPHYSICALMEMORY**](nc-d3dkmddi-dxgkcb_mapphysicalmemory.md) callback function to map a CPU-visible virtual address to the underlying physical memory.

## -struct-fields

### -field hPhysicalMemoryObject

[in] The physical memory object that describes the underlying physical pages to be mapped. This object was created in a prior call to [**DXGKCB_CREATEPHYSICALMEMORYOBJECT**](nc-d3dkmddi-dxgkcb_createphysicalmemoryobject.md).

### -field AccessMode

[in] A [**DXGK_ACCESS_MODE**](ne-d3dkmddi-dxgk_access_mode.md) enum value that describes the access mode (user mode or kernel mode) for which the mapping should be made.

### -field Offset

[in/out] As an input, specifies the offset from the start of the physical memory object, in bytes. As an output, specifies the offset from the start of the mapped base address where the requested data resides, in bytes. See Remarks for more information.

### -field Size

[in] As an input, specifies the requested size of the mapped region, in bytes. As an output, specifies the actual mapped size, in bytes. See Remarks for more information.

### -field pMappedAddress

[out] On a successful call to [**DXGKCB_MAPPHYSICALMEMORY**](nc-d3dkmddi-dxgkcb_mapphysicalmemory.md), this is a pointer to the underlying physical memory mapping. The start of the mapped memory range might not be exactly equal to the offset requested by the driver if rounding or alignment was required. As a result, the output value of **Offset** refers to the offset from the base address to the data requested by the driver. That is, ActualAddress = BaseAddress + Offset.

## -remarks

**Offset** and **Size** are both input and output parameters. As an input, these describe the region of physical memory that is requested by the caller. On output, these describe the actual mapped view. This is because the address that is mapped to the corresponding physical memory may not be exactly at the requested offset. The actual data requested by the caller will be equal to **pMappedAddress** + **Offset**. The size of the virtual address range that was mapped will be the output value of **Size**, which may be larger than the requested size.

## -see-also

[**DXGK_ACCESS_MODE**](ne-d3dkmddi-dxgk_access_mode.md)

[**DXGKCB_MAPPHYSICALMEMORY**](nc-d3dkmddi-dxgkcb_mapphysicalmemory.md)
