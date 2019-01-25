---
UID: NS:lamp.LAMP_INTENSITY_COLOR
title: LAMP_INTENSITY_COLOR (lamp.h)
description: This structure is the I/O parameter type of IOCTL_LAMP_GET_INTENSITY_COLOR and IOCTL_LAMP_SET_INTENSITY_COLOR.
old-location: stream\lamp_intensity_color.htm
tech.root: stream
ms.assetid: F87AFCA5-651C-4782-9F6F-C0AFB09010CB
ms.date: 04/23/2018
ms.keywords: LAMP_INTENSITY_COLOR, LAMP_INTENSITY_COLOR structure [Streaming Media Devices], lamp/LAMP_INTENSITY_COLOR, stream.lamp_intensity_color
ms.topic: struct
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	lamp.h
api_name:
-	LAMP_INTENSITY_COLOR
product:
- Windows
targetos: Windows
req.typenames: LAMP_INTENSITY_COLOR
---

# LAMP_INTENSITY_COLOR structure


## -description


This structure is the I/O parameter type of <a href="https://msdn.microsoft.com/library/windows/hardware/dn925069">IOCTL_LAMP_GET_INTENSITY_COLOR</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/dn925076">IOCTL_LAMP_SET_INTENSITY_COLOR</a>.


## -struct-fields




### -field Red

Red light intensity in percentage (0-100).


### -field Green

Green light intensity in percentage (0-100).


### -field Blue

Blue light intensity in percentage (0-100).

