---
UID: NE:lamp.LAMP_MODE
title: LAMP_MODE
author: windows-driver-content
description: This enumeration contains the operating modes of a lamp device.
old-location: stream\lamp_mode.htm
old-project: stream
ms.assetid: B379B6EF-C3AD-4E6F-B32D-F85228DB6A72
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: ",  , ,, A, D, E, L, LAMP_MODE, LAMP_MODE enumeration [Streaming Media Devices], LAMP_MODE_COLOR, LAMP_MODE_WHITE, M, O, P, _, lamp/LAMP_MODE, lamp/LAMP_MODE_COLOR, lamp/LAMP_MODE_WHITE, stream.lamp_mode"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: lamp.h
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	lamp.h
apiname:
-	LAMP_MODE
product: Windows
targetos: Windows
req.typenames: LAMP_MODE
---

# LAMP_MODE enumeration


## -description


This enumeration contains the operating modes of a lamp device.


## -syntax


````
typedef enum _LAMP_MODE { 
  LAMP_MODE_WHITE  = 0,
  LAMP_MODE_COLOR
} LAMP_MODE;
````


## -enum-fields




### -field LAMP_MODE_WHITE

Required. White light only.


### -field LAMP_MODE_COLOR

Optional. Color light.


## -remarks



This is the I/O parameter type of <a href="..\lamp\ni-lamp-ioctl_lamp_get_mode.md">IOCTL_LAMP_GET_MODE</a> and <a href="..\lamp\ni-lamp-ioctl_lamp_set_mode.md">IOCTL_LAMP_SET_MODE</a>.



