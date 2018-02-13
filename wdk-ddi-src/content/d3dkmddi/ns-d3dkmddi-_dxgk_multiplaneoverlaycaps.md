---
UID: NS:d3dkmddi._DXGK_MULTIPLANEOVERLAYCAPS
title: "_DXGK_MULTIPLANEOVERLAYCAPS"
author: windows-driver-content
description: Multiplane overlay capabilities returned by the DxgkDdiGetMultiPlaneOverlayCaps function.
old-location: display\dxgk_multiplaneoverlaycaps.htm
old-project: display
ms.assetid: E3F590EA-2B3B-464B-9D72-708B24CA3052
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: d3dkmddi/DXGK_MULTIPLANEOVERLAYCAPS, _DXGK_MULTIPLANEOVERLAYCAPS, DXGK_MULTIPLANEOVERLAYCAPS structure [Display Devices], display.dxgk_multiplaneoverlaycaps, DXGK_MULTIPLANEOVERLAYCAPS
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dkmddi.h
apiname:
-	DXGK_MULTIPLANEOVERLAYCAPS
product: Windows
targetos: Windows
req.typenames: DXGK_MULTIPLANEOVERLAYCAPS
---

# _DXGK_MULTIPLANEOVERLAYCAPS structure


## -description


Multiplane overlay capabilities returned by the DxgkDdiGetMultiPlaneOverlayCaps function.


## -syntax


````
typedef struct _DXGK_MULTIPLANEOVERLAYCAPS {
  union {
    struct {
      UINT Rotation  :1;
      UINT RotationWithoutIndependentFlip  :1;
      UINT VerticalFlip  :1;
      UINT HorizontalFlip  :1;
      UINT StretchRGB  :1;
      UINT StretchYUV  :1;
      UINT BilinearFilter  :1;
      UINT HighFilter  :1;
      UINT Shared  :1;
      UINT Immediate  :1;
      UINT Plane0ForVirtualModeOnly  :1;
      UINT Reserved  :21;
    };
    UINT Value;
  };
} DXGK_MULTIPLANEOVERLAYCAPS;
````


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

