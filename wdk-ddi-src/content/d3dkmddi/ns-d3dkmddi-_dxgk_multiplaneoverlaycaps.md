---
UID: NS:d3dkmddi._DXGK_MULTIPLANEOVERLAYCAPS
title: "_DXGK_MULTIPLANEOVERLAYCAPS"
author: windows-driver-content
description: Multiplane overlay capabilities returned by the DxgkDdiGetMultiPlaneOverlayCaps function.
old-location: display\dxgk_multiplaneoverlaycaps.htm
ms.assetid: E3F590EA-2B3B-464B-9D72-708B24CA3052
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: DXGK_MULTIPLANEOVERLAYCAPS, DXGK_MULTIPLANEOVERLAYCAPS structure [Display Devices], _DXGK_MULTIPLANEOVERLAYCAPS, d3dkmddi/DXGK_MULTIPLANEOVERLAYCAPS, display.dxgk_multiplaneoverlaycaps
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmddi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dkmddi.h
api_name:
-	DXGK_MULTIPLANEOVERLAYCAPS
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: DXGK_MULTIPLANEOVERLAYCAPS
---

# _DXGK_MULTIPLANEOVERLAYCAPS structure


## -description


Multiplane overlay capabilities returned by the DxgkDdiGetMultiPlaneOverlayCaps function.


## -struct-fields




### -field Rotation

When TRUE, indicates that the hardware supports rotating the plane 90, 180, or 270 degrees. 

If TRUE, RotationWithoutIndependentFlip should be FALSE.



### -field RotationWithoutIndependentFlip

When TRUE, indicates that the driver can perform plane rotation of 90, 180, or 270 degrees, but IndependentFlip cannot be used when rotating the plane.

If TRUE, Rotation should be FALSE.



### -field VerticalFlip

When TRUE, the hardware supports flipping the plane vertically.


### -field HorizontalFlip

When TRUE, the hardware supports flipping the plane horizontally.


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




### -field Reserved

This member is reserved and should be set to zero. Setting this member to zero is equivalent to setting the remaining 21 bits (0xFFFFFFFC) of the 32-bit <b>Value</b> member to zeros.


### -field Value

