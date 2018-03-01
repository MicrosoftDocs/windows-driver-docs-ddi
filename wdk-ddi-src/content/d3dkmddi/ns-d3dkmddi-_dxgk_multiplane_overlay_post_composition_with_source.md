---
UID: NS:d3dkmddi._DXGK_MULTIPLANE_OVERLAY_POST_COMPOSITION_WITH_SOURCE
title: "_DXGK_MULTIPLANE_OVERLAY_POST_COMPOSITION_WITH_SOURCE"
author: windows-driver-content
description: Used in a call to the DxgkDdiCheckMultiPlaneOverlaySupport3 function to check details on hardware support for post composition transform support.
old-location: display\dxgk_multiplane_overlay_post_composition_with_source.htm
old-project: display
ms.assetid: F997E3DB-630D-41C8-B659-36376E05A6B7
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: DXGK_MULTIPLANE_OVERLAY_POST_COMPOSITION_WITH_SOURCE, DXGK_MULTIPLANE_OVERLAY_POST_COMPOSITION_WITH_SOURCE structure [Display Devices], _DXGK_MULTIPLANE_OVERLAY_POST_COMPOSITION_WITH_SOURCE, d3dkmddi/DXGK_MULTIPLANE_OVERLAY_POST_COMPOSITION_WITH_SOURCE, display.dxgk_multiplane_overlay_post_composition_with_source
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dkmddi.h
api_name:
-	DXGK_MULTIPLANE_OVERLAY_POST_COMPOSITION_WITH_SOURCE
product: Windows
targetos: Windows
req.typenames: DXGK_MULTIPLANE_OVERLAY_POST_COMPOSITION_WITH_SOURCE
---

# _DXGK_MULTIPLANE_OVERLAY_POST_COMPOSITION_WITH_SOURCE structure


## -description


Used in a call to the <b>DxgkDdiCheckMultiPlaneOverlaySupport3 </b>function to check details on hardware support for post composition transform support.


## -syntax


````
typedef struct _DXGK_MULTIPLANE_OVERLAY_POST_COMPOSITION_WITH_SOURCE {
  D3DDDI_VIDEO_PRESENT_SOURCE_ID            VidPnSourceId;
  DXGK_MULTIPLANE_OVERLAY_POST_COMPOSITION  PostComposition;
} DXGK_MULTIPLANE_OVERLAY_POST_COMPOSITION_WITH_SOURCE;
````


## -struct-fields




### -field VidPnSourceId

The zero-based video present network (VidPN) source identification number of the input for which the support levels are queried.


### -field PostComposition

A DXGK_MULTIPLANE_OVERLAY_POST_COMPOSITION structure that specifies additional transforms that should be applied after the planes are composed.

