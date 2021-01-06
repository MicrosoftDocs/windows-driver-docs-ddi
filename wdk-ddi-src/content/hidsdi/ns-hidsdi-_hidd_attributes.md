---
UID: NS:hidsdi._HIDD_ATTRIBUTES
title: _HIDD_ATTRIBUTES (hidsdi.h)
description: The HIDD_ATTRIBUTES structure contains vendor information about a HIDClass device.
old-location: hid\hidd_attributes.htm
tech.root: hid
ms.date: 04/30/2018
keywords: ["HIDD_ATTRIBUTES structure"]
ms.keywords: "*PHIDD_ATTRIBUTES, HIDD_ATTRIBUTES, HIDD_ATTRIBUTES structure [Human Input Devices], PHIDD_ATTRIBUTES, PHIDD_ATTRIBUTES structure pointer [Human Input Devices], _HIDD_ATTRIBUTES, hid.hidd_attributes, hidsdi/HIDD_ATTRIBUTES, hidsdi/PHIDD_ATTRIBUTES, hidstrct_450ed87e-655a-414d-b24a-8b1aec7564b8.xml"
req.header: hidsdi.h
req.include-header: Hidsdi.h
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
req.typenames: HIDD_ATTRIBUTES, *PHIDD_ATTRIBUTES
f1_keywords:
 - _HIDD_ATTRIBUTES
 - hidsdi/_HIDD_ATTRIBUTES
 - PHIDD_ATTRIBUTES
 - hidsdi/PHIDD_ATTRIBUTES
 - HIDD_ATTRIBUTES
 - hidsdi/HIDD_ATTRIBUTES
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - hidsdi.h
api_name:
 - HIDD_ATTRIBUTES
---

# _HIDD_ATTRIBUTES structure


## -description

The HIDD_ATTRIBUTES structure contains vendor information about a HIDClass device.

## -struct-fields

### -field Size

Specifies the size, in bytes, of a HIDD_ATTRIBUTES structure.

### -field VendorID

Specifies a HID device's vendor ID.

### -field ProductID

Specifies a HID device's product ID.

### -field VersionNumber

Specifies the manufacturer's revision number for a HIDClass device.

## -remarks

A caller of <a href="/windows-hardware/drivers/ddi/hidsdi/nf-hidsdi-hidd_getattributes">HidD_GetAttributes</a>, uses this structure to obtain a device's vendor information.

Before using a HIDD_ATTRIBUTES structure with <a href="/windows-hardware/drivers/ddi/index">HIDClass support routines</a>, the caller must set the <b>Size</b> member.

## -see-also

<a href="/windows-hardware/drivers/ddi/hidsdi/nf-hidsdi-hidd_getattributes">HidD_GetAttributes</a>
