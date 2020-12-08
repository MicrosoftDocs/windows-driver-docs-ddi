---
UID: NE:portabledevice.tagWPD_FOCUS_MODES
title: WPD_FOCUS_MODES (portabledevice.h)
description: The WPD_FOCUS_MODES enumeration type describes the focus mode used by a still image capture device.
old-location: wpddk\wpd_focus_modes.htm
tech.root: wpd_dk
ms.date: 02/15/2018
keywords: ["tagWPD_FOCUS_MODES enumeration"]
ms.keywords: WPD_FOCUS_AUTOMATIC, WPD_FOCUS_AUTOMATIC_MACRO, WPD_FOCUS_MANUAL, WPD_FOCUS_MODES, WPD_FOCUS_MODES enumeration, WPD_FOCUS_UNDEFINED, enumeration, portabledevice/WPD_FOCUS_AUTOMATIC, portabledevice/WPD_FOCUS_AUTOMATIC_MACRO, portabledevice/WPD_FOCUS_MANUAL, portabledevice/WPD_FOCUS_MODES, portabledevice/WPD_FOCUS_UNDEFINED, tagWPD_FOCUS_MODES, wpddk.wpd_focus_modes
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
targetos: Windows
req.typenames: WPD_FOCUS_MODES
ms.custom: RS5
f1_keywords:
 - tagWPD_FOCUS_MODES
 - portabledevice/tagWPD_FOCUS_MODES
 - WPD_FOCUS_MODES
 - portabledevice/WPD_FOCUS_MODES
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - PortableDevice.h
api_name:
 - WPD_FOCUS_MODES
---

# tagWPD_FOCUS_MODES enumeration


## -description

The <b>WPD_FOCUS_MODES</b> enumeration type describes the focus mode used by a still image capture device.

## -enum-fields

### -field WPD_FOCUS_UNDEFINED

The focus mode has not been specified.

### -field WPD_FOCUS_MANUAL

Specifies manual focus.

### -field WPD_FOCUS_AUTOMATIC

Specifies automatic focus, controlled by the device.

### -field WPD_FOCUS_AUTOMATIC_MACRO

Specifies that the device should automatically switch between macro and normal focus, as required.

## -remarks

This enumeration is used by the <a href="/windows/desktop/wpd_sdk/still-image-properties">WPD_STILL_IMAGE_FOCUS_MODE</a> property.

## -see-also

<a href="/previous-versions/windows/hardware/drivers/ff597672(v=vs.85)">Structures and Enumeration Types</a>
