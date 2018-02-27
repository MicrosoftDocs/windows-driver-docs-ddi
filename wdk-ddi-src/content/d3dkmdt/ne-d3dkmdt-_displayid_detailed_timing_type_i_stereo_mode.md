---
UID: NE:d3dkmdt._DISPLAYID_DETAILED_TIMING_TYPE_I_STEREO_MODE
title: "_DISPLAYID_DETAILED_TIMING_TYPE_I_STEREO_MODE"
author: windows-driver-content
description: The DISPLAYID_DETAILED_TIMING_TYPE_I_STEREO_MODE enumeration indicates the display device's stereo vision mode.
old-location: display\displayid_detailed_timing_type_i_stereo_mode.htm
old-project: display
ms.assetid: 7e40ddf4-0098-4ea6-ab93-17515849b6cd
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: DIDDT1_Dependent, DIDDT1_Monoscopic, DIDDT1_Stereo, DmEnums_011fdd6c-ba90-40f7-ad26-d1fe075d21c3.xml, _DISPLAYID_DETAILED_TIMING_TYPE_I_STEREO_MODE, _DISPLAYID_DETAILED_TIMING_TYPE_I_STEREO_MODE enumeration [Display Devices], d3dkmdt/DIDDT1_Dependent, d3dkmdt/DIDDT1_Monoscopic, d3dkmdt/DIDDT1_Stereo, d3dkmdt/_DISPLAYID_DETAILED_TIMING_TYPE_I_STEREO_MODE, display.displayid_detailed_timing_type_i_stereo_mode
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3dkmdt.h
req.include-header: D3dkmdt.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 7 and later versions of the Windows operating systems.
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
-	d3dkmdt.h
api_name:
-	_DISPLAYID_DETAILED_TIMING_TYPE_I_STEREO_MODE
product: Windows
targetos: Windows
req.typenames: 
---

# _DISPLAYID_DETAILED_TIMING_TYPE_I_STEREO_MODE enumeration


## -description


The DISPLAYID_DETAILED_TIMING_TYPE_I_STEREO_MODE enumeration indicates the display device's stereo vision mode.


## -syntax


````
enum _DISPLAYID_DETAILED_TIMING_TYPE_I_STEREO_MODE {
  DIDDT1_Monoscopic  = 0, 
  DIDDT1_Stereo      = 1, 
  DIDDT1_Dependent   = 2 

};
````


## -enum-fields




### -field DIDDT1_Monoscopic

Indicates monoscopic mode (no stereo vision).


### -field DIDDT1_Stereo

Indicates stereo mode.


### -field DIDDT1_Dependent

Indicates that the mode depends upon user action.

