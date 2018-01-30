---
UID: NS:d3dkmthk._D3DKMT_BRIGHTNESS_POSSIBLE_LEVELS
title: "_D3DKMT_BRIGHTNESS_POSSIBLE_LEVELS"
author: windows-driver-content
description: Contains information about all possible brightness levels that an integrated display panel supports.
old-location: display\d3dkmt_brightness_possible_levels.htm
old-project: display
ms.assetid: d7402839-2afe-43d3-9747-7b2e98d1c238
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: "_D3DKMT_BRIGHTNESS_POSSIBLE_LEVELS, d3dkmthk/D3DKMT_BRIGHTNESS_POSSIBLE_LEVELS, display.d3dkmt_brightness_possible_levels, D3DKMT_BRIGHTNESS_POSSIBLE_LEVELS structure [Display Devices], D3DKMT_BRIGHTNESS_POSSIBLE_LEVELS"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	D3dkmthk.h
apiname:
-	D3DKMT_BRIGHTNESS_POSSIBLE_LEVELS
product: Windows
targetos: Windows
req.typenames: D3DKMT_BRIGHTNESS_POSSIBLE_LEVELS
---

# _D3DKMT_BRIGHTNESS_POSSIBLE_LEVELS structure


## -description


Contains information about all possible brightness levels that an integrated display panel supports.


## -syntax


````
typedef struct _D3DKMT_BRIGHTNESS_POSSIBLE_LEVELS {
  UCHAR LevelCount;
  UCHAR BrightnessLevels[256];
} D3DKMT_BRIGHTNESS_POSSIBLE_LEVELS;
````


## -struct-fields




### -field LevelCount

The number of brightness levels that the integrated display panel supports.


### -field BrightnessLevels

The specific brightness levels that the integrated display panel supports.

