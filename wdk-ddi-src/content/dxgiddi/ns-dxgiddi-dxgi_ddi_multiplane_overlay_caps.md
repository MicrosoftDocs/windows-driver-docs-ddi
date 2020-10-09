---
UID: NS:dxgiddi.DXGI_DDI_MULTIPLANE_OVERLAY_CAPS
title: DXGI_DDI_MULTIPLANE_OVERLAY_CAPS (dxgiddi.h)
description: Used by the user-mode display driver to specify overlay plane capabilities.
old-location: display\dxgi_ddi_multiplane_overlay_caps.htm
tech.root: display
ms.assetid: 269d9a51-bc01-4de4-b160-35c725c174f7
ms.date: 05/10/2018
keywords: ["DXGI_DDI_MULTIPLANE_OVERLAY_CAPS structure"]
ms.keywords: DXGI_DDI_MULTIPLANE_OVERLAY_CAPS, DXGI_DDI_MULTIPLANE_OVERLAY_CAPS structure [Display Devices], display.dxgi_ddi_multiplane_overlay_caps, dxgiddi/DXGI_DDI_MULTIPLANE_OVERLAY_CAPS
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
req.typenames: DXGI_DDI_MULTIPLANE_OVERLAY_CAPS
f1_keywords:
 - DXGI_DDI_MULTIPLANE_OVERLAY_CAPS
 - dxgiddi/DXGI_DDI_MULTIPLANE_OVERLAY_CAPS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Dxgiddi.h
api_name:
 - DXGI_DDI_MULTIPLANE_OVERLAY_CAPS
---

# DXGI_DDI_MULTIPLANE_OVERLAY_CAPS structure


## -description

Used by the user-mode display driver to specify overlay plane capabilities.

## -struct-fields

### -field MaxPlanes

The maximum number of inputs, including the primary surface, to the display hardware that can be supported in the current mode. This value can change if the mode changes.

For example, if the hardware allows one overlay plane and one normal primary surface, the driver should set <b>MaxPlanes</b> to 2.

### -field NumCapabilityGroups

The number of different types of overlay planes that can be supported.

Here are 2 examples:

<ul>
<li>If the hardware supports 2 RGB-only planes with limited stretching capabilities, plus 2 YUV planes with more flexible stretching capabilities, then the driver should set <b>NumCapabilityGroups</b> to 2.</li>
<li>If the hardware supports one RGB-only plane with no stretching capabilities, plus 2 RGB-only planes with full  stretching capabilities, plus 2 RGB/YUV planes with full stretching capabilities, then the driver should set <b>NumCapabilityGroups</b> to 3.</li>
</ul>

