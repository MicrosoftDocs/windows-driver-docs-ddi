---
UID: NE:lamp.LAMP_MODE
title: LAMP_MODE (lamp.h)
description: This enumeration contains the operating modes of a lamp device.
old-location: stream\lamp_mode.htm
tech.root: stream
ms.date: 04/23/2018
keywords: ["LAMP_MODE enumeration"]
ms.keywords: LAMP_MODE, LAMP_MODE enumeration [Streaming Media Devices], LAMP_MODE_COLOR, LAMP_MODE_WHITE, lamp/LAMP_MODE, lamp/LAMP_MODE_COLOR, lamp/LAMP_MODE_WHITE, stream.lamp_mode
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
req.typenames: LAMP_MODE
f1_keywords:
 - LAMP_MODE
 - lamp/LAMP_MODE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - lamp.h
api_name:
 - LAMP_MODE
---

# LAMP_MODE enumeration


## -description

This enumeration contains the operating modes of a lamp device.

## -enum-fields

### -field LAMP_MODE_WHITE

Required. White light only.

### -field LAMP_MODE_COLOR

Optional. Color light.

## -remarks

This is the I/O parameter type of <a href="/windows-hardware/drivers/ddi/lamp/ni-lamp-ioctl_lamp_get_mode">IOCTL_LAMP_GET_MODE</a> and <a href="/windows-hardware/drivers/ddi/lamp/ni-lamp-ioctl_lamp_set_mode">IOCTL_LAMP_SET_MODE</a>.
