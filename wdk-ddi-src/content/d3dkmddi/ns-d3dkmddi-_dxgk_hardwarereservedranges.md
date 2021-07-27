---
UID: NS:d3dkmddi._DXGK_HARDWARERESERVEDRANGES
title: DXGK_HARDWARERESERVEDRANGES (d3dkmddi.h)
description: The DXGK_HARDWARERESERVEDRANGES structure is used to store the hardware reserved memory ranges that were queried by a call to DXGKDDI_QUERYADAPTERINFO.
ms.date: 07/22/2021
keywords: ["DXGK_HARDWARERESERVEDRANGES structure"]
ms.keywords: _DXGK_HARDWARERESERVEDRANGES, DXGK_HARDWARERESERVEDRANGES,
req.header: d3dkmddi.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1803
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.ddi-compliance: 
req.unicode-ansi: 
req.max-support: 
req.typenames: DXGK_HARDWARERESERVEDRANGES
targetos: Windows
tech.root: display
f1_keywords:
 - _DXGK_HARDWARERESERVEDRANGES
 - d3dkmddi/_DXGK_HARDWARERESERVEDRANGES
 - DXGK_HARDWARERESERVEDRANGES
 - d3dkmddi/DXGK_HARDWARERESERVEDRANGES
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGK_HARDWARERESERVEDRANGES
 - DXGK_HARDWARERESERVEDRANGES
product:
 - Windows
---

# DXGK_HARDWARERESERVEDRANGES structure

## -description

The **DXGK_HARDWARERESERVEDRANGES** structure is used to store the hardware reserved memory ranges that were queried by the call the [**DXGKDDI_QUERYADAPTERINFO**](/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_queryadapterinfo).

## -struct-fields

### -field NumRanges

The number of ranges that are reserved.

### -field pPhysicalRanges

Pointer to a [**DXGK_PHYSICAL_MEMORY_RANGE**](ns-d3dkmddi-_dxgk_physical_memory_range.md) structure that contains information about the physical memory ranges.

## -remarks

The VidMm (Video Memory Manager) validates whether the ranges returned from [**DXGKDDI_QUERYADAPTERINFO**](/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_queryadapterinfo) overlap any regions of memory used by the NTOS (Windows NT-based operating system) memory manager. This validation ensures that the driver does not accidentally report a region of physical memory that is outside the reserved range, as this would violate the security guarantees of the feature.

See [IOMMU-based GPU isolation](/windows-hardware/drivers/display/iommu-based-gpu-isolation) for more information.
