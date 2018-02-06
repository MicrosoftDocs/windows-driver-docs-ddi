---
UID: NE:d3dkmdt._DXGK_DISPLAY_TECHNOLOGY
title: "_DXGK_DISPLAY_TECHNOLOGY"
author: windows-driver-content
description: Enum used to specify the display technology being used.
old-location: display\dxgk_display_technology.htm
old-project: display
ms.assetid: 4612213A-E79F-4C3B-95B4-8C83C0B5FB32
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: d3dkmdt/DXGK_DT_OTHER, DXGK_DISPLAY_TECHNOLOGY enumeration [Display Devices], d3dkmdt/DXGK_DISPLAY_TECHNOLOGY, PDXGK_DISPLAY_TECHNOLOGY, DXGK_DISPLAY_TECHNOLOGY, DXGK_DT_OLED, display.dxgk_display_technology, PDXGK_DISPLAY_TECHNOLOGY enumeration pointer [Display Devices], d3dkmdt/DXGK_DT_LCD, DXGK_DT_OTHER, d3dkmdt/PDXGK_DISPLAY_TECHNOLOGY, *PDXGK_DISPLAY_TECHNOLOGY, d3dkmdt/DXGK_DT_INVALID, d3dkmdt/DXGK_DT_OLED, DXGK_DT_LCD, DXGK_DT_INVALID, _DXGK_DISPLAY_TECHNOLOGY
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
-	DXGK_DISPLAY_TECHNOLOGY
product: Windows
targetos: Windows
req.typenames: DXGK_DISPLAY_TECHNOLOGY, *PDXGK_DISPLAY_TECHNOLOGY
---

# _DXGK_DISPLAY_TECHNOLOGY enumeration


## -description


Enum used to specify the display technology being used.


## -syntax


````
typedef enum _DXGK_DISPLAY_TECHNOLOGY { 
  DXGK_DT_INVALID  = 0,
  DXGK_DT_OTHER,
  DXGK_DT_LCD,
  DXGK_DT_OLED
} DXGK_DISPLAY_TECHNOLOGY, *PDXGK_DISPLAY_TECHNOLOGY ;
````


## -enum-fields




### -field DXGK_DT_INVALID

Invalid type.


### -field DXGK_DT_OTHER

A display technology which does not match one of the defined, valid types.


### -field DXGK_DT_LCD

A display using an LCD panel.


### -field DXGK_DT_OLED

A display using an OLED panel.


### -field DXGK_DT_PROJECTOR



### -field DXGK_DT_MAX



### -field BYTE



