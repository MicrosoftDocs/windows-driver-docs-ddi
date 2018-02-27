---
UID: NE:d3dkmdt._DXGK_DISPLAY_USAGE
title: "_DXGK_DISPLAY_USAGE"
author: windows-driver-content
description: Enum used to specify the display type being used.
old-location: display\dxgk_display_usage.htm
old-project: display
ms.assetid: 07B51679-4E9B-4360-AA4A-D5BD9BADB4FC
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PDXGK_DISPLAY_USAGE, DXGK_DISPLAY_USAGE, DXGK_DISPLAY_USAGE enumeration [Display Devices], DXGK_DU_AR, DXGK_DU_GENERIC, DXGK_DU_INVALID, DXGK_DU_VR, PDXGK_DISPLAY_USAGE, PDXGK_DISPLAY_USAGE enumeration pointer [Display Devices], _DXGK_DISPLAY_USAGE, d3dkmdt/DXGK_DISPLAY_USAGE, d3dkmdt/DXGK_DU_AR, d3dkmdt/DXGK_DU_GENERIC, d3dkmdt/DXGK_DU_INVALID, d3dkmdt/DXGK_DU_VR, d3dkmdt/PDXGK_DISPLAY_USAGE, display.dxgk_display_usage"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3dkmdt.h
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
-	d3dkmdt.h
apiname:
-	DXGK_DISPLAY_USAGE
product: Windows
targetos: Windows
req.typenames: DXGK_DISPLAY_USAGE, *PDXGK_DISPLAY_USAGE
---

# _DXGK_DISPLAY_USAGE enumeration


## -description


Enum used to specify the display type being used.


## -syntax


````
typedef enum _DXGK_DISPLAY_USAGE { 
  DXGK_DU_INVALID  = 0,
  DXGK_DU_GENERIC,
  DXGK_DU_AR,
  DXGK_DU_VR
} DXGK_DISPLAY_USAGE, *PDXGK_DISPLAY_USAGE;
````


## -enum-fields




### -field DXGK_DU_INVALID

Invalid type.


### -field DXGK_DU_GENERIC

Generic display type.


### -field DXGK_DU_AR

A head mounted augmented reality display.  


### -field DXGK_DU_VR

A head mounted virtual reality display.  


### -field DXGK_DU_MAX


### -field BYTE



