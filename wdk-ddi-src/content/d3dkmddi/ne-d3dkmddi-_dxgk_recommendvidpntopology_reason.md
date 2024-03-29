---
UID: NE:d3dkmddi._DXGK_RECOMMENDVIDPNTOPOLOGY_REASON
title: _DXGK_RECOMMENDVIDPNTOPOLOGY_REASON (d3dkmddi.h)
description: Indicates the reason for calling the display miniport driver's DxgkDdiRecommendVidPnTopology function.
old-location: display\dxgk_recommendvidpntopology_reason.htm
ms.date: 05/10/2018
keywords: ["DXGK_RECOMMENDVIDPNTOPOLOGY_REASON enumeration"]
ms.keywords: DXGK_RECOMMENDVIDPNTOPOLOGY_REASON, DXGK_RECOMMENDVIDPNTOPOLOGY_REASON enumeration [Display Devices], DXGK_RVT_AUGMENTATION_LKGOVERRIDE, DXGK_RVT_AUGMENTATION_NOLKG, DXGK_RVT_INITIALIZATION_LKGOVERRIDE, DXGK_RVT_INITIALIZATION_NOLKG, DXGK_RVT_UNINITIALIZED, DmEnums_b03f6fe2-5501-45ef-b841-48c6c3cc729a.xml, _DXGK_RECOMMENDVIDPNTOPOLOGY_REASON, d3dkmddi/DXGK_RECOMMENDVIDPNTOPOLOGY_REASON, d3dkmddi/DXGK_RVT_AUGMENTATION_LKGOVERRIDE, d3dkmddi/DXGK_RVT_AUGMENTATION_NOLKG, d3dkmddi/DXGK_RVT_INITIALIZATION_LKGOVERRIDE, d3dkmddi/DXGK_RVT_INITIALIZATION_NOLKG, d3dkmddi/DXGK_RVT_UNINITIALIZED, display.dxgk_recommendvidpntopology_reason
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows Vista
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
tech.root: display
req.typenames: DXGK_RECOMMENDVIDPNTOPOLOGY_REASON
f1_keywords:
 - _DXGK_RECOMMENDVIDPNTOPOLOGY_REASON
 - d3dkmddi/_DXGK_RECOMMENDVIDPNTOPOLOGY_REASON
 - DXGK_RECOMMENDVIDPNTOPOLOGY_REASON
 - d3dkmddi/DXGK_RECOMMENDVIDPNTOPOLOGY_REASON
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGK_RECOMMENDVIDPNTOPOLOGY_REASON
 - DXGK_RECOMMENDVIDPNTOPOLOGY_REASON
---

# _DXGK_RECOMMENDVIDPNTOPOLOGY_REASON enumeration


## -description

The <b>DXGK_RECOMMENDVIDPNTOPOLOGY_REASON</b> enumeration indicates the reason for calling the display miniport driver's <a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_recommendvidpntopology">DxgkDdiRecommendVidPnTopology</a> function.

## -enum-fields

### -field DXGK_RVT_UNINITIALIZED

Indicates that a variable of type <a href="/windows-hardware/drivers/ddi/d3dkmddi/ne-d3dkmddi-_dxgk_recommendvidpntopology_reason">DXGK_RECOMMENDVIDPNTOPOLOGY_REASON</a> has not yet been assigned a meaningful value.

### -field DXGK_RVT_INITIALIZATION_NOLKG

Indicates that the call is being made during the initialization of the display adapter after an attempt to use the last known good VidPN topology failed.

### -field DXGK_RVT_AUGMENTATION_NOLKG

      Indicates that the call is being made during the VidPN topology augmentation by the display mode manager (DMM) after an attempt to use the last known good VidPN topology failed.

### -field DXGK_RVT_AUGMENTATION_LKGOVERRIDE

Indicates that the call is being made during the VidPN topology augmentation by the display mode manager (DMM), giving the display miniport driver a chance to override the last known good VidPN topology.

### -field DXGK_RVT_INITIALIZATION_LKGOVERRIDE

Indicates that the call is being made during the initialization of the display adapter, giving the display miniport driver a chance to override the last known good VidPN topology.

