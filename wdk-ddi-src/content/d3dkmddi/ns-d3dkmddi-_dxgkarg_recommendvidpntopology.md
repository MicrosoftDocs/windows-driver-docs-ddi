---
UID: NS:d3dkmddi._DXGKARG_RECOMMENDVIDPNTOPOLOGY
title: _DXGKARG_RECOMMENDVIDPNTOPOLOGY (d3dkmddi.h)
description: The DXGKARG_RECOMMENDVIDPNTOPOLOGY structure contains arguments for the display miniport driver's DxgkDdiRecommendVidPnTopology function.
old-location: display\dxgkarg_recommendvidpntopology.htm
ms.date: 05/10/2018
keywords: ["DXGKARG_RECOMMENDVIDPNTOPOLOGY structure"]
ms.keywords: DXGKARG_RECOMMENDVIDPNTOPOLOGY, DXGKARG_RECOMMENDVIDPNTOPOLOGY structure [Display Devices], DmStructs_960673e2-caf0-4f46-9b8c-c1da025fb6bf.xml, _DXGKARG_RECOMMENDVIDPNTOPOLOGY, d3dkmddi/DXGKARG_RECOMMENDVIDPNTOPOLOGY, display.dxgkarg_recommendvidpntopology
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
req.typenames: DXGKARG_RECOMMENDVIDPNTOPOLOGY
f1_keywords:
 - _DXGKARG_RECOMMENDVIDPNTOPOLOGY
 - d3dkmddi/_DXGKARG_RECOMMENDVIDPNTOPOLOGY
 - DXGKARG_RECOMMENDVIDPNTOPOLOGY
 - d3dkmddi/DXGKARG_RECOMMENDVIDPNTOPOLOGY
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGKARG_RECOMMENDVIDPNTOPOLOGY
 - DXGKARG_RECOMMENDVIDPNTOPOLOGY
---

# _DXGKARG_RECOMMENDVIDPNTOPOLOGY structure


## -description

The DXGKARG_RECOMMENDVIDPNTOPOLOGY structure contains arguments for the display miniport driver's <a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_recommendvidpntopology">DxgkDdiRecommendVidPnTopology</a> function.

## -struct-fields

### -field hVidPn

A handle to a VidPN object. The <i>DxgkDdiRecommendVidPnTopology</i> function creates or augments the topology of this VidPN.

### -field VidPnSourceId

D3DDDI_ID_ALL or the identifier of a particular video present source on the display adapter. If this member is the identifier of a particular source, the <i>DxgkDdiRecommendVidPnTopology</i> function must augment the topology by adding at least one path that originates from that source. If this member is equal to D3DDDI_ID_ALL, <i>DxgkDdiRecommendVidPnTopology</i> must create the entire topology.

### -field RequestReason

      A value from the <a href="/windows-hardware/drivers/ddi/d3dkmddi/ne-d3dkmddi-_dxgk_recommendvidpntopology_reason">DXGK_RECOMMENDVIDPNTOPOLOGY_REASON</a> enumeration that indicates the reason that the <a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_recommendvidpntopology">DxgkDdiRecommendVidPnTopology</a> function is being called.

### -field hFallbackTopology

A handle to a VidPN topology object that represents the fallback VidPN topology that Windows will use if the miniport does not provide a topology recommendation.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dkmddi/ne-d3dkmddi-_dxgk_recommendvidpntopology_reason">DXGK_RECOMMENDVIDPNTOPOLOGY_REASON</a>



<a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_recommendvidpntopology">DxgkDdiRecommendVidPnTopology</a>

