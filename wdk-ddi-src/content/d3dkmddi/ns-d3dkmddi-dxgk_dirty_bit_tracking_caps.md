---
UID: NS:d3dkmddi._DXGK_DIRTY_BIT_TRACKING_CAPS
tech.root: display
title: DXGK_DIRTY_BIT_TRACKING_CAPS
ms.date: 03/28/2024
targetos: Windows
description: Learn more about the DXGK_DIRTY_BIT_TRACKING_CAPS structure.
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
req.typenames: DXGK_DIRTY_BIT_TRACKING_CAPS
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
 - _DXGK_DIRTY_BIT_TRACKING_CAPS
 - DXGK_DIRTY_BIT_TRACKING_CAPS
f1_keywords:
 - _DXGK_DIRTY_BIT_TRACKING_CAPS
 - d3dkmddi/_DXGK_DIRTY_BIT_TRACKING_CAPS
 - DXGK_DIRTY_BIT_TRACKING_CAPS
 - d3dkmddi/DXGK_DIRTY_BIT_TRACKING_CAPS
dev_langs:
 - c++
helpviewer_keywords:
 - _DXGK_DIRTY_BIT_TRACKING_CAPS
---

# DXGK_DIRTY_BIT_TRACKING_CAPS structure (d3dkmddi.h)

## -description

A kernel-mode display miniport driver (KMD) returns its dirty bit tracking capabilities in **DXGK_DIRTY_BIT_TRACKING_CAPS** when its [**DxgkDdiQueryAdapterInfo**](nc-d3dkmddi-dxgkddi_queryadapterinfo.md) function is called with the [**DXGKQAITYPE_DIRTYBITTRACKINGCAPS**](ne-d3dkmddi-_dxgk_queryadapterinfotype.md) query adapter info type.

## -struct-fields

### -field DirtyBitTrackingSupported

 When set TRUE, the adapter supports the ability to track dirty bit information. *Dxgkrnl* will, at a later time, call the followup **DXGKQAITYPE_DIRTYBITTRACKINGSEGMENTCAPS** call for each segment to determine the page size/granularity at which the data is tracked.

### -field DirtyBitTrackingPerformant

When set TRUE, the adapter is reporting the preference to track dirty content from the creation of the vDEV. This capability can drastically improve the performance of live migration scenarios by allowing only dirty content inside VRAM reserve to be transferred. If **DirtyBitTrackingPerformant** is FALSE, dirty tracking is only enabled during the live migration itself, and the initial transfer of content will be the entire reserved VRAM for the VF being migrated.

### -field Reserved

Reserved for system use.

### -field Value

An alternative way to access the structure's bitfields.

## -remarks

For more information, see [Dirty Bit Tracking](/windows-hardware/drivers/display/dirty-bit-tracking).

## -see-also

[**DXGK_QUERYADAPTERINFOTYPE**](ne-d3dkmddi-_dxgk_queryadapterinfotype.md)

[**DxgkDdiQueryAdapterInfo**](nc-d3dkmddi-dxgkddi_queryadapterinfo.md)