---
UID: NS:ntddvdeo._DISPLAY_BRIGHTNESS
title: "_DISPLAY_BRIGHTNESS"
author: windows-driver-content
description: The DISPLAY_BRIGHTNESS structure is reserved for system use.
old-location: display\display_brightness.htm
old-project: display
ms.assetid: 0e72c1a7-5712-46fc-a65f-20183830cb72
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: ntddvdeo/DISPLAY_BRIGHTNESS, ntddvdeo/PDISPLAY_BRIGHTNESS, Video_Structs_9be4657c-394e-4286-8157-e95f3ada36c8.xml, PDISPLAY_BRIGHTNESS structure pointer [Display Devices], *PDISPLAY_BRIGHTNESS, _DISPLAY_BRIGHTNESS, DISPLAY_BRIGHTNESS, DISPLAY_BRIGHTNESS structure [Display Devices], PDISPLAY_BRIGHTNESS, display.display_brightness
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddvdeo.h
req.include-header: Ntddvdeo.h
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntddvdeo.h
apiname:
-	DISPLAY_BRIGHTNESS
product: Windows
targetos: Windows
req.typenames: "*PDISPLAY_BRIGHTNESS, DISPLAY_BRIGHTNESS"
---

# _DISPLAY_BRIGHTNESS structure


## -description


The DISPLAY_BRIGHTNESS structure is reserved for system use.


## -syntax


````
typedef struct _DISPLAY_BRIGHTNESS {
  UCHAR ucDisplayPolicy;
  UCHAR ucACBrightness;
  UCHAR ucDCBrightness;
} DISPLAY_BRIGHTNESS, *PDISPLAY_BRIGHTNESS;
````


## -struct-fields




### -field ucDisplayPolicy

Reserved for system use.


### -field ucACBrightness

Reserved for system use.


### -field ucDCBrightness

Reserved for system use.

