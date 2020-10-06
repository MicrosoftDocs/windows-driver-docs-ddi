---
UID: NS:dxgiddi.DXGI_DDI_MULTIPLANE_OVERLAY_GROUP_CAPS
title: DXGI_DDI_MULTIPLANE_OVERLAY_GROUP_CAPS (dxgiddi.h)
description: Used by the user-mode display driver to specify groups of overlay plane capabilities.
old-location: display\dxgi_ddi_multiplane_overlay_group_caps.htm
tech.root: display
ms.assetid: A8BAD8D4-1009-43D0-B82F-8252062A029C
ms.date: 05/10/2018
keywords: ["DXGI_DDI_MULTIPLANE_OVERLAY_GROUP_CAPS structure"]
ms.keywords: DXGI_DDI_MULTIPLANE_OVERLAY_GROUP_CAPS, DXGI_DDI_MULTIPLANE_OVERLAY_GROUP_CAPS structure [Display Devices], display.dxgi_ddi_multiplane_overlay_group_caps, dxgiddi/DXGI_DDI_MULTIPLANE_OVERLAY_GROUP_CAPS
req.header: dxgiddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
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
req.typenames: DXGI_DDI_MULTIPLANE_OVERLAY_GROUP_CAPS
f1_keywords:
 - DXGI_DDI_MULTIPLANE_OVERLAY_GROUP_CAPS
 - dxgiddi/DXGI_DDI_MULTIPLANE_OVERLAY_GROUP_CAPS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Dxgiddi.h
api_name:
 - DXGI_DDI_MULTIPLANE_OVERLAY_GROUP_CAPS
---

# DXGI_DDI_MULTIPLANE_OVERLAY_GROUP_CAPS structure


## -description

Used by the user-mode display driver to specify groups of overlay plane capabilities.

## -struct-fields

### -field NumPlanes

Specifies the number of overlay planes that are supported by the overlay planes within the capability group.

### -field MaxStretchFactor

Specifies the maximum stretch factor that is supported by the overlay planes within the capability group.

The stretch factor is the ratio of the final, stretched overlay plane size to the original size. For example, if the original overlay plane is 100 x 100 pixels, a value of 2.5 means that it can be stretched to 250 x 250 pixels.

It's not guaranteed that this stretch factor can be applied in all scenarios. For example, it might be possible to stretch only one overlay plane out of several using this factor.

### -field MaxShrinkFactor

Specifies the maximum shrink factor that is supported by the overlay planes within the capability group.

The shrink factor is the ratio of the final, shrunk overlay plane size to the original size. For example, if the original overlay plane is 100 x 100 pixels, a value of 0.25 means that it can be shrunk to 25 x 25 pixels.

It's not guaranteed that this shrink factor can be applied in all scenarios. For example, it might be possible to shrink only one overlay plane out of several using this factor.

### -field OverlayCaps

The overlay capabilities, given as a bitwise <b>OR</b> of values from the <a href="/windows-hardware/drivers/ddi/dxgiddi/ne-dxgiddi-dxgi_ddi_multiplane_overlay_feature_caps">DXGI_DDI_MULTIPLANE_OVERLAY_FEATURE_CAPS</a> enumeration.

### -field StereoCaps

Reserved for system use. Set this value to zero.