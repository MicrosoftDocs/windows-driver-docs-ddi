---
UID: NE:d3dumddi._D3DDDI_MULTIPLANE_OVERLAY_FEATURE_CAPS
title: "_D3DDDI_MULTIPLANE_OVERLAY_FEATURE_CAPS"
author: windows-driver-content
description: Identifies overlay capabilities.
old-location: display\d3dddi_multiplane_overlay_feature_caps.htm
tech.root: display
ms.assetid: 51e44c1c-ca56-4fe3-a27b-d0957df203cf
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: D3DDDI_MULTIPLANE_OVERLAY_FEATURE_CAPS, D3DDDI_MULTIPLANE_OVERLAY_FEATURE_CAPS enumeration [Display Devices], D3DDDI_MULTIPLANE_OVERLAY_FEATURE_CAPS_BILINEAR_FILTER, D3DDDI_MULTIPLANE_OVERLAY_FEATURE_CAPS_DEINTERLACE, D3DDDI_MULTIPLANE_OVERLAY_FEATURE_CAPS_HIGH_FILTER, D3DDDI_MULTIPLANE_OVERLAY_FEATURE_CAPS_HORIZONTAL_FLIP, D3DDDI_MULTIPLANE_OVERLAY_FEATURE_CAPS_RGB, D3DDDI_MULTIPLANE_OVERLAY_FEATURE_CAPS_ROTATION, D3DDDI_MULTIPLANE_OVERLAY_FEATURE_CAPS_VERTICAL_FLIP, D3DDDI_MULTIPLANE_OVERLAY_FEATURE_CAPS_YUV, _D3DDDI_MULTIPLANE_OVERLAY_FEATURE_CAPS, d3dumddi/D3DDDI_MULTIPLANE_OVERLAY_FEATURE_CAPS, d3dumddi/D3DDDI_MULTIPLANE_OVERLAY_FEATURE_CAPS_BILINEAR_FILTER, d3dumddi/D3DDDI_MULTIPLANE_OVERLAY_FEATURE_CAPS_DEINTERLACE, d3dumddi/D3DDDI_MULTIPLANE_OVERLAY_FEATURE_CAPS_HIGH_FILTER, d3dumddi/D3DDDI_MULTIPLANE_OVERLAY_FEATURE_CAPS_HORIZONTAL_FLIP, d3dumddi/D3DDDI_MULTIPLANE_OVERLAY_FEATURE_CAPS_RGB, d3dumddi/D3DDDI_MULTIPLANE_OVERLAY_FEATURE_CAPS_ROTATION, d3dumddi/D3DDDI_MULTIPLANE_OVERLAY_FEATURE_CAPS_VERTICAL_FLIP, d3dumddi/D3DDDI_MULTIPLANE_OVERLAY_FEATURE_CAPS_YUV, display.d3dddi_multiplane_overlay_feature_caps
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3dumddi.h
req.include-header: D3dumddi.h
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	D3dumddi.h
api_name:
-	D3DDDI_MULTIPLANE_OVERLAY_FEATURE_CAPS
product:
- Windows
targetos: Windows
req.typenames: D3DDDI_MULTIPLANE_OVERLAY_FEATURE_CAPS
---

# _D3DDDI_MULTIPLANE_OVERLAY_FEATURE_CAPS enumeration


## -description


Identifies overlay capabilities.


## -enum-fields




### -field D3DDDI_MULTIPLANE_OVERLAY_FEATURE_CAPS_ROTATION

The overlay plane can rotate the data 90, 180, and 270 degrees.


### -field D3DDDI_MULTIPLANE_OVERLAY_FEATURE_CAPS_VERTICAL_FLIP

The overlay plane can flip the data vertically, making it appear upside-down.


### -field D3DDDI_MULTIPLANE_OVERLAY_FEATURE_CAPS_HORIZONTAL_FLIP

The overlay plane can flip the data horizontally, making it appear as a right-to-left mirror image.


### -field D3DDDI_MULTIPLANE_OVERLAY_FEATURE_CAPS_DEINTERLACE

Reserved for system use. The user-mode display driver should not use this value.


### -field D3DDDI_MULTIPLANE_OVERLAY_FEATURE_CAPS_RGB

The overlay plane supports RGB format.


### -field D3DDDI_MULTIPLANE_OVERLAY_FEATURE_CAPS_YUV

The overlay plane supports YUV format.


### -field D3DDDI_MULTIPLANE_OVERLAY_FEATURE_CAPS_BILINEAR_FILTER

The overlay plane supports stretching and shrinking using bilinear filtering.


### -field D3DDDI_MULTIPLANE_OVERLAY_FEATURE_CAPS_HIGH_FILTER

The overlay plane supports stretching and shrinking using filtering that is better than bilinear filtering.

