---
UID: NE:portabledevice.tagWPD_EXPOSURE_METERING_MODES
title: WPD_EXPOSURE_METERING_MODES (portabledevice.h)
description: The WPD_EXPOSURE_METERING_MODES enumeration type describes the metering mode to use when estimating exposure for still image capture by a device.
old-location: wpddk\wpd_exposure_metering_modes.htm
tech.root: wpd_dk
ms.assetid: 629c85d4-d632-4340-a745-1a79a451e7b2
ms.date: 02/15/2018
keywords: ["tagWPD_EXPOSURE_METERING_MODES enumeration"]
ms.keywords: WPD_EXPOSURE_METERING_MODES, WPD_EXPOSURE_METERING_MODES enumeration, WPD_EXPOSURE_METERING_MODE_AVERAGE, WPD_EXPOSURE_METERING_MODE_CENTER_SPOT, WPD_EXPOSURE_METERING_MODE_CENTER_WEIGHTED_AVERAGE, WPD_EXPOSURE_METERING_MODE_MULTI_SPOT, WPD_EXPOSURE_METERING_MODE_UNDEFINED, enumeration, portabledevice/WPD_EXPOSURE_METERING_MODES, portabledevice/WPD_EXPOSURE_METERING_MODE_AVERAGE, portabledevice/WPD_EXPOSURE_METERING_MODE_CENTER_SPOT, portabledevice/WPD_EXPOSURE_METERING_MODE_CENTER_WEIGHTED_AVERAGE, portabledevice/WPD_EXPOSURE_METERING_MODE_MULTI_SPOT, portabledevice/WPD_EXPOSURE_METERING_MODE_UNDEFINED, tagWPD_EXPOSURE_METERING_MODES, wpddk.wpd_exposure_metering_modes
f1_keywords:
 - "portabledevice/WPD_EXPOSURE_METERING_MODES"
 - "WPD_EXPOSURE_METERING_MODES"
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
- WPD_EXPOSURE_METERING_MODES
product:
- Windows
targetos: Windows
req.typenames: WPD_EXPOSURE_METERING_MODES
ms.custom: RS5
---

# tagWPD_EXPOSURE_METERING_MODES enumeration


## -description



The <b>WPD_EXPOSURE_METERING_MODES</b> enumeration type describes the metering mode to use when estimating exposure for still image capture by a device.




## -enum-fields




### -field WPD_EXPOSURE_METERING_MODE_UNDEFINED

The metering mode is undefined.


### -field WPD_EXPOSURE_METERING_MODE_AVERAGE

Use averaged exposure across the full image.


### -field WPD_EXPOSURE_METERING_MODE_CENTER_WEIGHTED_AVERAGE

Use an averaged exposure, with the center of the image given more weight.


### -field WPD_EXPOSURE_METERING_MODE_MULTI_SPOT

Use a multi-spot averaging technique.


### -field WPD_EXPOSURE_METERING_MODE_CENTER_SPOT

Use a center-spot averaging technique.


## -remarks



Indicates the metering mode of the device. This enumeration is used by the <a href="https://docs.microsoft.com/windows/desktop/wpd_sdk/still-image-properties">WPD_STILL_IMAGE_EXPOSURE_METERING_MODE</a> property.




## -see-also




<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff597672(v=vs.85)">Structures and Enumeration Types</a>
 

 

