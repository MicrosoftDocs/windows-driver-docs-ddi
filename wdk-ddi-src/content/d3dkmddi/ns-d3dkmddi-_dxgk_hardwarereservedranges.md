---
UID: NS:d3dkmddi._DXGK_HARDWARERESERVEDRANGES
title: _DXGK_HARDWARERESERVEDRANGES (d3dkmddi.h)
description: The hardware reserved memory ranges that was queried by the call the QueryAdapterInfo.
ms.assetid: c78d4d75-1775-407f-ac32-2e29a34389cd
ms.date: 10/19/2018
f1_keywords:
 - "d3dkmddi/_DXGK_HARDWARERESERVEDRANGES"
ms.keywords: _DXGK_HARDWARERESERVEDRANGES, DXGK_HARDWARERESERVEDRANGES,
req.header: d3dkmddi.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.typenames: DXGK_HARDWARERESERVEDRANGES
topic_type:
- apiref
api_type:
- HeaderDef
api_location:
- d3dkmddi.h
api_name:
- _DXGK_HARDWARERESERVEDRANGES
product: 
- Windows
targetos: Windows
tech.root: display
---

# _DXGK_HARDWARERESERVEDRANGES structure

## -description

The hardware reserved memory ranges that was queried by the call the QueryAdapterInfo.

The VidMm (Video Memory Manager) validates whether the ranges returned from QueryAdapterInfo overlaps any regions of memory used by the NTOS (Windows NT-based operating system) memory manager. This ensures that the driver does not accidentally report a region of physical memory that is outside the reserved range, as this would violate the security guarantees of the feature.

## -struct-fields

### -field NumRanges

The number of ranges that are reserved.

### -field pPhysicalRanges

Pointer to a DXGK_PHYSICAL_MEMORY_RANGE structure that contains information about the physical memory ranges.

