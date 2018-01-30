---
UID: NE:d3dkmddi._DXGK_RECOMMENDVIDPNTOPOLOGY_REASON
title: "_DXGK_RECOMMENDVIDPNTOPOLOGY_REASON"
author: windows-driver-content
description: Indicates the reason for calling the display miniport driver's DxgkDdiRecommendVidPnTopology function.
old-location: display\dxgk_recommendvidpntopology_reason.htm
old-project: display
ms.assetid: 2a67a119-863b-4cde-9308-e4862823bad1
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: DXGK_RVT_AUGMENTATION_NOLKG, DXGK_RECOMMENDVIDPNTOPOLOGY_REASON, _DXGK_RECOMMENDVIDPNTOPOLOGY_REASON, d3dkmddi/DXGK_RVT_INITIALIZATION_NOLKG, DXGK_RVT_UNINITIALIZED, display.dxgk_recommendvidpntopology_reason, d3dkmddi/DXGK_RVT_AUGMENTATION_LKGOVERRIDE, DXGK_RVT_INITIALIZATION_LKGOVERRIDE, d3dkmddi/DXGK_RVT_UNINITIALIZED, d3dkmddi/DXGK_RVT_AUGMENTATION_NOLKG, DmEnums_b03f6fe2-5501-45ef-b841-48c6c3cc729a.xml, DXGK_RVT_INITIALIZATION_NOLKG, DXGK_RVT_AUGMENTATION_LKGOVERRIDE, d3dkmddi/DXGK_RECOMMENDVIDPNTOPOLOGY_REASON, DXGK_RECOMMENDVIDPNTOPOLOGY_REASON enumeration [Display Devices], d3dkmddi/DXGK_RVT_INITIALIZATION_LKGOVERRIDE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dkmddi.h
apiname:
-	DXGK_RECOMMENDVIDPNTOPOLOGY_REASON
product: Windows
targetos: Windows
req.typenames: DXGK_RECOMMENDVIDPNTOPOLOGY_REASON
---

# _DXGK_RECOMMENDVIDPNTOPOLOGY_REASON enumeration


## -description


The <b>DXGK_RECOMMENDVIDPNTOPOLOGY_REASON</b> enumeration indicates the reason for calling the display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_recommendvidpntopology.md">DxgkDdiRecommendVidPnTopology</a> function.


## -syntax


````
typedef enum _DXGK_RECOMMENDVIDPNTOPOLOGY_REASON { 
  DXGK_RVT_UNINITIALIZED               = 0,
  DXGK_RVT_INITIALIZATION_NOLKG        = 1,
  DXGK_RVT_AUGMENTATION_NOLKG          = 2,
  DXGK_RVT_AUGMENTATION_LKGOVERRIDE    = 3,
  DXGK_RVT_INITIALIZATION_LKGOVERRIDE  = 4
} DXGK_RECOMMENDVIDPNTOPOLOGY_REASON;
````


## -enum-fields




### -field DXGK_RVT_UNINITIALIZED

Indicates that a variable of type <a href="..\d3dkmddi\ne-d3dkmddi-_dxgk_recommendvidpntopology_reason.md">DXGK_RECOMMENDVIDPNTOPOLOGY_REASON</a> has not yet been assigned a meaningful value.


### -field DXGK_RVT_INITIALIZATION_NOLKG

Indicates that the call is being made during the initialization of the display adapter after an attempt to use the last known good VidPN topology failed.


### -field DXGK_RVT_AUGMENTATION_NOLKG


      Indicates that the call is being made during the VidPN topology augmentation by the display mode manager (DMM) after an attempt to use the last known good VidPN topology failed.
     


### -field DXGK_RVT_AUGMENTATION_LKGOVERRIDE

Indicates that the call is being made during the VidPN topology augmentation by the display mode manager (DMM), giving the display miniport driver a chance to override the last known good VidPN topology.


### -field DXGK_RVT_INITIALIZATION_LKGOVERRIDE

Indicates that the call is being made during the initialization of the display adapter, giving the display miniport driver a chance to override the last known good VidPN topology.

