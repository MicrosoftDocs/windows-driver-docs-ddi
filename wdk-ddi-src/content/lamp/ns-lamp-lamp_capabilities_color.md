---
UID: NS:lamp.LAMP_CAPABILITIES_COLOR
title: LAMP_CAPABILITIES_COLOR (lamp.h)
description: This structure is the I/O parameter type of IOCTL_LAMP_GET_INTENSITY_COLOR and IOCTL_LAMP_SET_INTENSITY_COLOR.
old-location: stream\lamp_capabilities_color.htm
tech.root: stream
ms.date: 03/12/2021
keywords: ["LAMP_CAPABILITIES_COLOR structure"]
ms.keywords: LAMP_CAPABILITIES_COLOR, LAMP_CAPABILITIES_COLOR structure [Streaming Media Devices], lamp/LAMP_CAPABILITIES_COLOR, stream.lamp_capabilities_color
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
targetos: Windows
req.typenames: LAMP_CAPABILITIES_COLOR
f1_keywords:
 - LAMP_CAPABILITIES_COLOR
 - lamp/LAMP_CAPABILITIES_COLOR
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - lamp.h
api_name:
 - LAMP_CAPABILITIES_COLOR
---

# LAMP_CAPABILITIES_COLOR structure

## -description

This structure is the I/O parameter type of **IOCTL_LAMP_{GET|SET}_INTENSITY_COLOR**.

## -struct-fields

### -field IsSupported

**TRUE** if the device can emit color light; **FALSE** otherwise.

### -field IsLightIntensityAdjustable

If **IsSupported** evaluates to **TRUE** (the driver is capable of emitting color light) and this field evaluates to **TRUE**, a client can get/set light intensity of a color lamp by calling [IOCTL_LAMP_GET_INTENSITY_COLOR](/windows-hardware/drivers/ddi/lamp/ni-lamp-ioctl_lamp_get_intensity_color) and [IOCTL_LAMP_SET_INTENSITY_COLOR](/windows-hardware/drivers/ddi/lamp/ni-lamp-ioctl_lamp_set_intensity_color).
