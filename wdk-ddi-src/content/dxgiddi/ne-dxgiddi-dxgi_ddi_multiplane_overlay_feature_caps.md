---
UID: NE:dxgiddi.DXGI_DDI_MULTIPLANE_OVERLAY_FEATURE_CAPS
title: DXGI_DDI_MULTIPLANE_OVERLAY_FEATURE_CAPS
author: windows-driver-content
description: Identifies overlay capabilities.
old-location: display\dxgi_ddi_multiplane_overlay_feature_caps.htm
old-project: display
ms.assetid: f64b3470-b4ae-4d3a-87ac-249429f17dfe
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: DXGI_DDI_MULTIPLANE_OVERLAY_FEATURE_CAPS, DXGI_DDI_MULTIPLANE_OVERLAY_FEATURE_CAPS enumeration [Display Devices], DXGI_DDI_MULTIPLANE_OVERLAY_FEATURE_CAPS_DEINTERLACE, DXGI_DDI_MULTIPLANE_OVERLAY_FEATURE_CAPS_HORIZONTAL_FLIP, DXGI_DDI_MULTIPLANE_OVERLAY_FEATURE_CAPS_ROTATION, DXGI_DDI_MULTIPLANE_OVERLAY_FEATURE_CAPS_STEREO, DXGI_DDI_MULTIPLANE_OVERLAY_FEATURE_CAPS_VERTICAL_FLIP, display.dxgi_ddi_multiplane_overlay_feature_caps, dxgiddi/DXGI_DDI_MULTIPLANE_OVERLAY_FEATURE_CAPS, dxgiddi/DXGI_DDI_MULTIPLANE_OVERLAY_FEATURE_CAPS_DEINTERLACE, dxgiddi/DXGI_DDI_MULTIPLANE_OVERLAY_FEATURE_CAPS_HORIZONTAL_FLIP, dxgiddi/DXGI_DDI_MULTIPLANE_OVERLAY_FEATURE_CAPS_ROTATION, dxgiddi/DXGI_DDI_MULTIPLANE_OVERLAY_FEATURE_CAPS_STEREO, dxgiddi/DXGI_DDI_MULTIPLANE_OVERLAY_FEATURE_CAPS_VERTICAL_FLIP
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Dxgiddi.h
api_name:
-	DXGI_DDI_MULTIPLANE_OVERLAY_FEATURE_CAPS
product: Windows
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


### -field DXGI_DDI_MULTIPLANE_OVERLAY_FEATURE_CAPS_HIGH_FILTER


### -field DXGI_DDI_MULTIPLANE_OVERLAY_FEATURE_CAPS_ROTATION

The overlay plane can rotate the data 90, 180, and 270 degrees.


### -field DXGI_DDI_MULTIPLANE_OVERLAY_FEATURE_CAPS_FULLSCREEN_POST_COMPOSITION


### -field DXGI_DDI_MULTIPLANE_OVERLAY_FEATURE_RESERVED1


### -field DXGI_DDI_MULTIPLANE_OVERLAY_FEATURE_CAPS_SHARED


### -field DXGI_DDI_MULTIPLANE_OVERLAY_FEATURE_CAPS_IMMEDIATE


### -field DXGI_DDI_MULTIPLANE_OVERLAY_FEATURE_CAPS_PLANE0_FOR_VIRTUAL_MODE_ONLY



