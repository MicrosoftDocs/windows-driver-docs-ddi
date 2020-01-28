---
UID: NE:portabledevice.WPD_CAPTURE_MODES
title: WPD_CAPTURE_MODES (portabledevice.h)
description: The WPD_CAPTURE_MODES enumeration type describes the capture timing mode of a still image capture.
old-location: wpddk\wpd_capture_modes.htm
tech.root: wpd_dk
ms.assetid: 6aba61ed-e8b3-4fe1-a5f6-439165db4097
ms.date: 02/13/2019
ms.keywords: WPD_CAPTURE_MODES, WPD_CAPTURE_MODES enumeration, WPD_CAPTURE_MODE_BURST, WPD_CAPTURE_MODE_NORMAL, WPD_CAPTURE_MODE_TIMELAPSE, WPD_CAPTURE_MODE_UNDEFINED, enumeration, portabledevice/WPD_CAPTURE_MODES, portabledevice/WPD_CAPTURE_MODE_BURST, portabledevice/WPD_CAPTURE_MODE_NORMAL, portabledevice/WPD_CAPTURE_MODE_TIMELAPSE, portabledevice/WPD_CAPTURE_MODE_UNDEFINED, tagWPD_CAPTURE_MODES, wpddk.wpd_capture_modes
f1_keywords:
 - "portabledevice/WPD_CAPTURE_MODES"
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
- WPD_CAPTURE_MODES
product:
- Windows
targetos: Windows
req.typenames: WPD_CAPTURE_MODES
ms.custom: RS5
---

# tagWPD_CAPTURE_MODES enumeration


## -description



The <b>WPD_CAPTURE_MODES</b> enumeration type describes the capture timing mode of a still image capture.




## -enum-fields




### -field WPD_CAPTURE_MODE_UNDEFINED

The capture mode has not been defined.


### -field WPD_CAPTURE_MODE_NORMAL

No delay or burst mode should be used.


### -field WPD_CAPTURE_MODE_BURST

Specifies that a defined number of images should be captured with a defined interval between them. The number of images to capture and time delay between them are specified by the <a href="https://docs.microsoft.com/windows/desktop/wpd_sdk/still-image-properties">WPD_STILL_IMAGE_BURST_NUMBER</a> and <a href="https://docs.microsoft.com/windows/desktop/wpd_sdk/still-image-properties">WPD_STILL_IMAGE_BURST_INTERVAL</a> properties.


### -field WPD_CAPTURE_MODE_TIMELAPSE

Image capture should use time lapse photography. The number of images and interval between them are described by the <a href="https://docs.microsoft.com/windows/desktop/wpd_sdk/still-image-properties">WPD_STILL_IMAGE_TIMELAPSE_NUMBER</a> and <a href="https://docs.microsoft.com/windows/desktop/wpd_sdk/still-image-properties">WPD_STILL_IMAGE_TIMELAPSE_INTERVAL</a> properties.


## -remarks



This enumeration is used by the <a href="https://docs.microsoft.com/windows/desktop/wpd_sdk/still-image-properties">WPD_STILL_IMAGE_CAPTURE_MODE</a> property.




## -see-also




<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff597672(v=vs.85)">Structures and Enumeration Types</a>



<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff597900(v=vs.85)">WPD Properties and Attributes</a>
 

 

