---
UID: NE:dxgiddi.DXGI_DDI_MULTIPLANE_OVERLAY_FEATURE_CAPS
title: DXGI_DDI_MULTIPLANE_OVERLAY_FEATURE_CAPS (dxgiddi.h)
description: Identifies overlay capabilities.
old-location: display\dxgi_ddi_multiplane_overlay_feature_caps.htm
tech.root: display
ms.assetid: f64b3470-b4ae-4d3a-87ac-249429f17dfe
ms.date: 04/16/2018
keywords: ["DXGI_DDI_MULTIPLANE_OVERLAY_FEATURE_CAPS enumeration"]
ms.keywords: DXGI_DDI_MULTIPLANE_OVERLAY_FEATURE_CAPS, DXGI_DDI_MULTIPLANE_OVERLAY_FEATURE_CAPS enumeration [Display Devices], DXGI_DDI_MULTIPLANE_OVERLAY_FEATURE_CAPS_DEINTERLACE, DXGI_DDI_MULTIPLANE_OVERLAY_FEATURE_CAPS_HORIZONTAL_FLIP, DXGI_DDI_MULTIPLANE_OVERLAY_FEATURE_CAPS_ROTATION, DXGI_DDI_MULTIPLANE_OVERLAY_FEATURE_CAPS_STEREO, DXGI_DDI_MULTIPLANE_OVERLAY_FEATURE_CAPS_VERTICAL_FLIP, display.dxgi_ddi_multiplane_overlay_feature_caps, dxgiddi/DXGI_DDI_MULTIPLANE_OVERLAY_FEATURE_CAPS, dxgiddi/DXGI_DDI_MULTIPLANE_OVERLAY_FEATURE_CAPS_DEINTERLACE, dxgiddi/DXGI_DDI_MULTIPLANE_OVERLAY_FEATURE_CAPS_HORIZONTAL_FLIP, dxgiddi/DXGI_DDI_MULTIPLANE_OVERLAY_FEATURE_CAPS_ROTATION, dxgiddi/DXGI_DDI_MULTIPLANE_OVERLAY_FEATURE_CAPS_STEREO, dxgiddi/DXGI_DDI_MULTIPLANE_OVERLAY_FEATURE_CAPS_VERTICAL_FLIP
f1_keywords:
 - "dxgiddi/DXGI_DDI_MULTIPLANE_OVERLAY_FEATURE_CAPS"
 - "DXGI_DDI_MULTIPLANE_OVERLAY_FEATURE_CAPS"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Dxgiddi.h
api_name:
- DXGI_DDI_MULTIPLANE_OVERLAY_FEATURE_CAPS
targetos: Windows
req.typenames: DXGI_DDI_MULTIPLANE_OVERLAY_FEATURE_CAPS
---

# DXGI_DDI_MULTIPLANE_OVERLAY_FEATURE_CAPS enumeration


## -description


Identifies overlay capabilities.


## -enum-fields




### -field DXGI_DDI_MULTIPLANE_OVERLAY_FEATURE_CAPS_ROTATION_WITHOUT_INDEPENDENT_FLIP


### -field DXGI_DDI_MULTIPLANE_OVERLAY_FEATURE_CAPS_VERTICAL_FLIP

The overlay plane can flip the data vertically, making it appear upside-down.


### -field DXGI_DDI_MULTIPLANE_OVERLAY_FEATURE_CAPS_HORIZONTAL_FLIP

The overlay plane can flip the data horizontally, making it appear as a right-to-left mirror image.


### -field DXGI_DDI_MULTIPLANE_OVERLAY_FEATURE_CAPS_DEINTERLACE

Reserved for system use. The user-mode display driver should not use this value.


### -field DXGI_DDI_MULTIPLANE_OVERLAY_FEATURE_CAPS_STEREO

Reserved for system use. The user-mode display driver should not use this value.


### -field DXGI_DDI_MULTIPLANE_OVERLAY_FEATURE_CAPS_RGB


### -field DXGI_DDI_MULTIPLANE_OVERLAY_FEATURE_CAPS_YUV


### -field DXGI_DDI_MULTIPLANE_OVERLAY_FEATURE_CAPS_BILINEAR_FILTER

Can do bilinear stretching.

### -field DXGI_DDI_MULTIPLANE_OVERLAY_FEATURE_CAPS_HIGH_FILTER

Can do better than bilinear stretching.

### -field DXGI_DDI_MULTIPLANE_OVERLAY_FEATURE_CAPS_ROTATION

The overlay plane can rotate the data 90, 180, and 270 degrees.


### -field DXGI_DDI_MULTIPLANE_OVERLAY_FEATURE_CAPS_FULLSCREEN_POST_COMPOSITION

Indicates that the caps reported in this group apply to a fullscreen plane and that all operation applied to this plane occur after composition with other MPO planes has occurred. This is useful for the following scenarios:

* Panel fitter HW can be employed to stretch the surface to match the screen. This is useful for supporting virtual modes.

    * It can stretch or shrink the desktop plane for the VidPnSourceId to match of a single monitor with the following limitations:

        * The entire allocation must be stretched – no sub rectangles are supported.
        * This must be plane 0 in the Z order.

    * If a HW cursor is supported, the HW cursor will get composed with the desktop plane prior to the stretching (i.e. the HW cursor will get stretched or shrunk with the rest of the desktop plane).
    * If other MPO planes are supported in addition to the panel fitter, the clip rectangles for the other MPO planes are bound to the source rect of the panel fitter plane.

* In HDR scenarios, the presenting the HDR allocation (potentially with metadata) will just look like an MPO present with a single plane that covers the entire screen.

This flag should not be reported in the same capability groups as normal MPO.

### -field DXGI_DDI_MULTIPLANE_OVERLAY_FEATURE_RESERVED1


### -field DXGI_DDI_MULTIPLANE_OVERLAY_FEATURE_CAPS_SHARED

Indicates that the hardware described in this capability group could be shared across outputs.

For example, if hardware supports a dedicated panel fitter per output, but also supports 4 additional MPO planes that are shared across multiple outputs, the driver would report the following capability groups on each output:

* One capability group for the panel fitter that does not set the DXGI_DDI_MULTIPLANE_OVERLAY_FEATURE_CAPS_SHARED capability flag.
* One or more capability groups describing the 4 MPO planes that do set the DXGI_DDI_MULTIPLANE_OVERLAY_FEATURE_CAPS_SHARED capability.


### -field DXGI_DDI_MULTIPLANE_OVERLAY_FEATURE_CAPS_IMMEDIATE

Indicates that the HW supports immediate flips of the MPO plane as long as the only change is the display start address.

### -field DXGI_DDI_MULTIPLANE_OVERLAY_FEATURE_CAPS_PLANE0_FOR_VIRTUAL_MODE_ONLY

Indicates that stretching/shrinking of plane 0 should only occur when plane 0 is the desktop plane and the stretching/shrinking is used for virtual mode support.


