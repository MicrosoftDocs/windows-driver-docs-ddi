---
UID: NE:portabledevice.tagWPD_COLOR_CORRECTED_STATUS_VALUES
title: WPD_COLOR_CORRECTED_STATUS_VALUES (portabledevice.h)
description: The WPD_COLOR_CORRECTED_STATUS_VALUES enumeration type describes the color correction status of an image or video file.
old-location: wpddk\wpd_color_corrected_status_values.htm
tech.root: wpd_dk
ms.assetid: c3a975c7-9598-4b20-8b18-3b457c80467c
ms.date: 02/15/2018
ms.keywords: WPD_COLOR_CORRECTED_STATUS_CORRECTED, WPD_COLOR_CORRECTED_STATUS_NOT_CORRECTED, WPD_COLOR_CORRECTED_STATUS_SHOULD_NOT_BE_CORRECTED, WPD_COLOR_CORRECTED_STATUS_VALUES, WPD_COLOR_CORRECTED_STATUS_VALUES enumeration, enumeration, portabledevice/WPD_COLOR_CORRECTED_STATUS_CORRECTED, portabledevice/WPD_COLOR_CORRECTED_STATUS_NOT_CORRECTED, portabledevice/WPD_COLOR_CORRECTED_STATUS_SHOULD_NOT_BE_CORRECTED, portabledevice/WPD_COLOR_CORRECTED_STATUS_VALUES, tagWPD_COLOR_CORRECTED_STATUS_VALUES, wpddk.wpd_color_corrected_status_values
f1_keywords:
 - "portabledevice/WPD_COLOR_CORRECTED_STATUS_VALUES"
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
- WPD_COLOR_CORRECTED_STATUS_VALUES
product:
- Windows
targetos: Windows
req.typenames: WPD_COLOR_CORRECTED_STATUS_VALUES
ms.custom: RS5
---

# tagWPD_COLOR_CORRECTED_STATUS_VALUES enumeration


## -description



The <b>WPD_COLOR_CORRECTED_STATUS_VALUES</b> enumeration type describes the color correction status of an image or video file.




## -enum-fields




### -field WPD_COLOR_CORRECTED_STATUS_NOT_CORRECTED

The image has not been color corrected.


### -field WPD_COLOR_CORRECTED_STATUS_CORRECTED

The image has been color corrected.


### -field WPD_COLOR_CORRECTED_STATUS_SHOULD_NOT_BE_CORRECTED

The image has not been, and should not be, color corrected.


## -remarks



Indicates the color corrected status of an image. This enumeration is used by the [**WPD_IMAGE_COLOR_CORRECTED_STATUS**](https://docs.microsoft.com/windows/desktop/wpd_sdk/image-properties) property.




## -see-also




<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff597672(v=vs.85)">Structures and Enumeration Types</a>
 

 

