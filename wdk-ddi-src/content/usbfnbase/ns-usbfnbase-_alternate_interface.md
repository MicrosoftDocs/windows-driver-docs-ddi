---
UID: NS:usbfnbase._ALTERNATE_INTERFACE
title: _ALTERNATE_INTERFACE (usbfnbase.h)
description: The ALTERNATE_INTERFACE structure provides information about alternate settings for a Universal Serial Bus (USB) interface.
old-location: buses\alternate_interface.htm
tech.root: usbref
ms.date: 05/07/2018
keywords: ["ALTERNATE_INTERFACE structure"]
ms.keywords: "*PALTERNATE_INTERFACE, ALTERNATE_INTERFACE, ALTERNATE_INTERFACE structure [Buses], PALTERNATE_INTERFACE, PALTERNATE_INTERFACE structure pointer [Buses], _ALTERNATE_INTERFACE, buses.alternate_interface, usbfnbase/ALTERNATE_INTERFACE, usbfnbase/PALTERNATE_INTERFACE"
req.header: usbfnbase.h
req.include-header: Usbfnbase.h
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
req.typenames: ALTERNATE_INTERFACE, *PALTERNATE_INTERFACE
f1_keywords:
 - _ALTERNATE_INTERFACE
 - usbfnbase/_ALTERNATE_INTERFACE
 - PALTERNATE_INTERFACE
 - usbfnbase/PALTERNATE_INTERFACE
 - ALTERNATE_INTERFACE
 - usbfnbase/ALTERNATE_INTERFACE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - usbfnbase.h
api_name:
 - _ALTERNATE_INTERFACE
 - PALTERNATE_INTERFACE
 - ALTERNATE_INTERFACE
---

# _ALTERNATE_INTERFACE structure


## -description

The <b>ALTERNATE_INTERFACE</b> structure provides information about alternate settings for a Universal Serial Bus (USB) interface.

## -struct-fields

### -field InterfaceNumber

The index number for theUSB interface setting.

### -field AlternateInterfaceNumber

The index number for the alternate USB interface setting.

## -see-also

<a href="/windows-hardware/drivers/ddi/usbfnbase/ns-usbfnbase-_usbfn_notification">USBFN_NOTIFICATION</a>

