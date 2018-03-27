---
UID: NE:d3dkmddi._DXGK_RECOMMENDVIDPNTOPOLOGY_REASON
title: "_DXGK_RECOMMENDVIDPNTOPOLOGY_REASON"
author: windows-driver-content
description: Indicates the reason for calling the display miniport driver's DxgkDdiRecommendVidPnTopology function.
old-location: display\dxgk_recommendvidpntopology_reason.htm
old-project: display
ms.assetid: 2a67a119-863b-4cde-9308-e4862823bad1
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DXGK_RECOMMENDVIDPNTOPOLOGY_REASON, DXGK_RECOMMENDVIDPNTOPOLOGY_REASON enumeration [Display Devices], DXGK_RVT_AUGMENTATION_LKGOVERRIDE, DXGK_RVT_AUGMENTATION_NOLKG, DXGK_RVT_INITIALIZATION_LKGOVERRIDE, DXGK_RVT_INITIALIZATION_NOLKG, DXGK_RVT_UNINITIALIZED, DmEnums_b03f6fe2-5501-45ef-b841-48c6c3cc729a.xml, _DXGK_RECOMMENDVIDPNTOPOLOGY_REASON, d3dkmddi/DXGK_RECOMMENDVIDPNTOPOLOGY_REASON, d3dkmddi/DXGK_RVT_AUGMENTATION_LKGOVERRIDE, d3dkmddi/DXGK_RVT_AUGMENTATION_NOLKG, d3dkmddi/DXGK_RVT_INITIALIZATION_LKGOVERRIDE, d3dkmddi/DXGK_RVT_INITIALIZATION_NOLKG, d3dkmddi/DXGK_RVT_UNINITIALIZED, display.dxgk_recommendvidpntopology_reason
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dkmddi.h
api_name:
-	DXGK_RECOMMENDVIDPNTOPOLOGY_REASON
product: Windows
targetos: Windows
req.typenames: DXGK_RECOMMENDVIDPNTOPOLOGY_REASON
---

# _DXGK_RECOMMENDVIDPNTOPOLOGY_REASON enumeration


## -description


The <b>DXGK_RECOMMENDVIDPNTOPOLOGY_REASON</b> enumeration indicates the reason for calling the display miniport driver's <a href="https://msdn.microsoft.com/a7c31d2c-3893-4d25-837d-d4650aeb1cd1">DxgkDdiRecommendVidPnTopology</a> function.


## -enum-fields




### -field DXGK_RVT_UNINITIALIZED

Indicates that a variable of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff562023">DXGK_RECOMMENDVIDPNTOPOLOGY_REASON</a> has not yet been assigned a meaningful value.


### -field DXGK_RVT_INITIALIZATION_NOLKG

Indicates that the call is being made during the initialization of the display adapter after an attempt to use the last known good VidPN topology failed.


### -field DXGK_RVT_AUGMENTATION_NOLKG


      Indicates that the call is being made during the VidPN topology augmentation by the display mode manager (DMM) after an attempt to use the last known good VidPN topology failed.
     


### -field DXGK_RVT_AUGMENTATION_LKGOVERRIDE

Indicates that the call is being made during the VidPN topology augmentation by the display mode manager (DMM), giving the display miniport driver a chance to override the last known good VidPN topology.


### -field DXGK_RVT_INITIALIZATION_LKGOVERRIDE

Indicates that the call is being made during the initialization of the display adapter, giving the display miniport driver a chance to override the last known good VidPN topology.

