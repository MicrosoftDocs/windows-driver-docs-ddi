---
UID: NS:d3dkmddi._DXGK_STANDARD_COLORIMETRY_FLAGS
title: _DXGK_STANDARD_COLORIMETRY_FLAGS (d3dkmddi.h)
description: Flags describing standard colorimetry and related support.
old-location: display\dxgk_standard_colorimetry_flags.htm
ms.assetid: 473C5D7B-8FDD-49E2-981A-00ECCA67671A
ms.date: 05/10/2018
keywords: ["_DXGK_STANDARD_COLORIMETRY_FLAGS structure"]
ms.keywords: "*PDXGK_STANDARD_COLORIMETRY_FLAGS, DXGK_STANDARD_COLORIMETRY_FLAGS, DXGK_STANDARD_COLORIMETRY_FLAGS union [Display Devices], PDXGK_STANDARD_COLORIMETRY_FLAGS, PDXGK_STANDARD_COLORIMETRY_FLAGS union pointer [Display Devices], _DXGK_STANDARD_COLORIMETRY_FLAGS, d3dkmddi/DXGK_STANDARD_COLORIMETRY_FLAGS, d3dkmddi/PDXGK_STANDARD_COLORIMETRY_FLAGS, display.dxgk_standard_colorimetry_flags"
f1_keywords:
 - "d3dkmddi/DXGK_STANDARD_COLORIMETRY_FLAGS"
 - "DXGK_STANDARD_COLORIMETRY_FLAGS"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- d3dkmddi.h
api_name:
- DXGK_STANDARD_COLORIMETRY_FLAGS
targetos: Windows
tech.root: display
req.typenames: DXGK_STANDARD_COLORIMETRY_FLAGS, *PDXGK_STANDARD_COLORIMETRY_FLAGS
---

# _DXGK_STANDARD_COLORIMETRY_FLAGS structure


## -description


Flags describing standard colorimetry and related support.


## -struct-fields




### -field BT2020YCC

Flag which indicates device support for the color space defined by BT.2020 using a YCC signal format.


### -field BT2020RGB

Flag which indicates device support for the color space defined by BT.2020 using an RGB signal format.


### -field ST2084

Flag which indicates device support for the ST.2084 EOTF.


### -field Reserved

This value is reserved for system use.


### -field Value

The combined value that is operated on.

