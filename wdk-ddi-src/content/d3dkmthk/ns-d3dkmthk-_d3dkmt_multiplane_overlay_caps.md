---
UID: NS:d3dkmthk._D3DKMT_MULTIPLANE_OVERLAY_CAPS
title: _D3DKMT_MULTIPLANE_OVERLAY_CAPS (d3dkmthk.h)
description: Contains multiplane overlay capabilities.
ms.assetid: 15844fc5-e933-45dc-bbed-e57ed1a26668
ms.date: 10/19/2018
ms.topic: struct
ms.keywords: _D3DKMT_MULTIPLANE_OVERLAY_CAPS, D3DKMT_MULTIPLANE_OVERLAY_CAPS, 
req.header: d3dkmthk.h
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
req.typenames: D3DKMT_MULTIPLANE_OVERLAY_CAPS
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- d3dkmthk.h
api_name: 
- _D3DKMT_MULTIPLANE_OVERLAY_CAPS
product:
- Windows
targetos: Windows
ms.custom: RS5
tech.root: display
---

# _D3DKMT_MULTIPLANE_OVERLAY_CAPS structure

## -description

Contains multiplane overlay capabilities.

## -struct-fields

### -field Rotation

Specifies the clockwise rotation of the overlay plane.

### -field RotationWithoutIndependentFlip

When TRUE, indicates that the driver can perform plane rotation of 90, 180, or 270 degrees, but IndependentFlip cannot be used when rotating the plane.

### -field VerticalFlip

The overlay plane should flip the data vertically.

### -field HorizontalFlip

The overlay plane should flip the data horizontally.

### -field StretchRGB

When TRUE, the hardware supports stretching any plane containing RGB data.

### -field StretchYUV

When TRUE, the hardware supports stretching any plane containing YUV data.

### -field BilinearFilter

When TRUE, the hardware supports bilinear filtering.

### -field HighFilter

When TRUE, the hardware supports better than bilinear filtering.

### -field Shared

When TRUE, the multiplane overlay resources reported by the capabilities are shared across all VidPn sources.

When FALSE, the multiplane overlay resources reported by capabilities are dedicated to the specific VidPn source.

### -field Immediate

When TRUE, the HW supports immediate flips of the MPO plane.

If the flip contains changes that cannot be performed as an immediate flip, the driver can promote the flip to a VSYNC flip using the new HSync completion infrastructure.

### -field Plane0ForVirtualModeOnly

When TRUE, the hardware will always apply the stretch factor of plane 0 to the hardware cursor as well as the plane. This implies that stretching/shrinking of plane 0 should only occur when plane 0 is the desktop plane and when the stretching/shrinking is used for virtual mode support.

### -field Version3DDISupport

Driver supports the WDDM 2.2 MPO (multi-plane overlay) DDIs.

### -field Reserved

Reserved for internal use.

### -field Value
 
The value used to operate over the other members.

## -remarks

## -see-also
