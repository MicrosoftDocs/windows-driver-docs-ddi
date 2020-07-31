---
UID: NE:portabledevice.tagWPD_FOCUS_METERING_MODES
title: WPD_FOCUS_METERING_MODES (portabledevice.h)
description: The WPD_FOCUS_METERING_MODES enumeration type describes how a device should decide what part of a frame to use to set focus.
old-location: wpddk\wpd_focus_metering_modes.htm
tech.root: wpd_dk
ms.assetid: 44218c04-7f32-4e88-830a-8341b903a6c5
ms.date: 02/15/2018
keywords: ["tagWPD_FOCUS_METERING_MODES enumeration"]
ms.keywords: WPD_FOCUS_METERING_MODES, WPD_FOCUS_METERING_MODES enumeration, WPD_FOCUS_METERING_MODE_CENTER_SPOT, WPD_FOCUS_METERING_MODE_MULTI_SPOT, WPD_FOCUS_METERING_MODE_UNDEFINED, enumeration, portabledevice/WPD_FOCUS_METERING_MODES, portabledevice/WPD_FOCUS_METERING_MODE_CENTER_SPOT, portabledevice/WPD_FOCUS_METERING_MODE_MULTI_SPOT, portabledevice/WPD_FOCUS_METERING_MODE_UNDEFINED, tagWPD_FOCUS_METERING_MODES, wpddk.wpd_focus_metering_modes
f1_keywords:
 - "portabledevice/WPD_FOCUS_METERING_MODES"
 - "WPD_FOCUS_METERING_MODES"
req.header: portabledevice.h
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
- PortableDevice.h
api_name:
- WPD_FOCUS_METERING_MODES
targetos: Windows
req.typenames: WPD_FOCUS_METERING_MODES
ms.custom: RS5
---

# tagWPD_FOCUS_METERING_MODES enumeration


## -description



The <b>WPD_FOCUS_METERING_MODES</b> enumeration type describes how a device should decide what part of a frame to use to set focus.




## -enum-fields




### -field WPD_FOCUS_METERING_MODE_UNDEFINED

Indicates that no focusing mode has been specified.


### -field WPD_FOCUS_METERING_MODE_CENTER_SPOT

Focus on the center of the framed area.


### -field WPD_FOCUS_METERING_MODE_MULTI_SPOT

Determine focus by analyzing multiple parts of the framed area.


## -remarks



This enumeration is specified by the <a href="https://docs.microsoft.com/windows/desktop/wpd_sdk/still-image-properties">WPD_STILL_IMAGE_FOCUS_METERING_MODE</a> property.




## -see-also




<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff597672(v=vs.85)">Structures and Enumeration Types</a>
 

 

