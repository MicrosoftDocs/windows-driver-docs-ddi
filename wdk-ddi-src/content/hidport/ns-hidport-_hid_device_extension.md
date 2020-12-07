---
UID: NS:hidport._HID_DEVICE_EXTENSION
title: _HID_DEVICE_EXTENSION (hidport.h)
description: The HID_DEVICE_EXTENSION structure is used by a HID minidriver as its layout for the device extension of a HIDClass device's functional device object.
old-location: hid\hid_device_extension.htm
tech.root: hid
ms.date: 04/30/2018
keywords: ["HID_DEVICE_EXTENSION structure"]
ms.keywords: "*PHID_DEVICE_EXTENSION, HID_DEVICE_EXTENSION, HID_DEVICE_EXTENSION structure [Human Input Devices], PHID_DEVICE_EXTENSION, PHID_DEVICE_EXTENSION structure pointer [Human Input Devices], _HID_DEVICE_EXTENSION, hid.hid_device_extension, hidport/HID_DEVICE_EXTENSION, hidport/PHID_DEVICE_EXTENSION, hidstrct_faf2bb84-b1f7-4cfa-84b0-5328dfb521dc.xml"
req.header: hidport.h
req.include-header: Hidport.h
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
req.typenames: HID_DEVICE_EXTENSION, *PHID_DEVICE_EXTENSION
f1_keywords:
 - _HID_DEVICE_EXTENSION
 - hidport/_HID_DEVICE_EXTENSION
 - PHID_DEVICE_EXTENSION
 - hidport/PHID_DEVICE_EXTENSION
 - HID_DEVICE_EXTENSION
 - hidport/HID_DEVICE_EXTENSION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - hidport.h
api_name:
 - HID_DEVICE_EXTENSION
---

# _HID_DEVICE_EXTENSION structure


## -description

The HID_DEVICE_EXTENSION structure is used by a HID minidriver as its layout for the device extension of a HIDClass device's functional device object.

## -struct-fields

### -field PhysicalDeviceObject

Pointer to HID device's physical device object.

### -field NextDeviceObject

Pointer to the device object immediately below the functional device object in the HID device's device stack.

### -field MiniDeviceExtension

Pointer to the minidriver-specific portion of the device extension.

## -see-also

<a href="/windows-hardware/drivers/ddi/hidport/nf-hidport-hidregisterminidriver">HidRegisterMinidriver</a>
