---
UID: NS:d3dkmddi._DXGK_DIRTY_BIT_TRACKING_SEGMENT_CAPS
tech.root: display
title: DXGK_DIRTY_BIT_TRACKING_SEGMENT_CAPS
ms.date: 03/28/2024
targetos: Windows
description: Learn more about the DXGK_DIRTY_BIT_TRACKING_SEGMENT_CAPS structure.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: d3dkmddi.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 11, version 24H2
req.target-min-winversvr: 
req.target-type: 
req.typenames: DXGK_DIRTY_BIT_TRACKING_SEGMENT_CAPS
typedef_isUnnamed: false
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGK_DIRTY_BIT_TRACKING_SEGMENT_CAPS
 - DXGK_DIRTY_BIT_TRACKING_SEGMENT_CAPS
f1_keywords:
 - _DXGK_DIRTY_BIT_TRACKING_SEGMENT_CAPS
 - d3dkmddi/_DXGK_DIRTY_BIT_TRACKING_SEGMENT_CAPS
 - DXGK_DIRTY_BIT_TRACKING_SEGMENT_CAPS
 - d3dkmddi/DXGK_DIRTY_BIT_TRACKING_SEGMENT_CAPS
dev_langs:
 - c++
helpviewer_keywords:
 - _DXGK_DIRTY_BIT_TRACKING_SEGMENT_CAPS
---

# DXGK_DIRTY_BIT_TRACKING_SEGMENT_CAPS structure (d3dkmddi.h)

## -description

A kernel-mode display miniport driver (KMD) returns its dirty bit tracking capabilities for a specified segment in **DXGK_DIRTY_BIT_TRACKING_SEGMENT_CAPS** when its [**DxgkDdiQueryAdapterInfo**](nc-d3dkmddi-dxgkddi_queryadapterinfo.md) function is called with the [**DXGKQAITYPE_DIRTYBITTRACKINGSEGMENTCAPS**](ne-d3dkmddi-_dxgk_queryadapterinfotype.md) query adapter info type.

## -struct-fields

### -field PageSize

The size of a single page, represented by each bit in the dirty bit plane. **PageSize** can be any power of two value greater than or equal to 4KB.

## -remarks

If dirty plane data is not available for the segment, [**DxgkDdiQueryAdapterInfo**](nc-d3dkmddi-dxgkddi_queryadapterinfo.md)  should return STATUS_NOT_IMPLEMENTED for that particular call. *Dxgkrnl* ignores the contents of the output in this case.

For more information, see [Dirty bit tracking](/windows-hardware/drivers/display/dirty-bit-tracking).

## -see-also

[**DXGK_DIRTY_BIT_TRACKING_CAPS**](ns-d3dkmddi-dxgk_dirty_bit_tracking_caps.md)

[**DXGK_QUERYADAPTERINFOTYPE**](ne-d3dkmddi-_dxgk_queryadapterinfotype.md)

[**DxgkDdiQueryAdapterInfo**](nc-d3dkmddi-dxgkddi_queryadapterinfo.md)
