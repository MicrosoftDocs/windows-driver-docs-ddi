---
UID: NE:usbsidebandaudio._SIDEBANDAUDIO_USB_CONTROLLER_CONFIG_INFO_TYPE
title: SIDEBANDAUDIO_USB_CONTROLLER_CONFIG_INFO_TYPE
description: Microsoft USB Audio Sideband USB controller Set of Parameters.
ms.date: 07/11/2023
prerelease: false
req.construct-type: enumeration
req.ddi-compliance: 
req.header: usbsidebandaudio.h
req.include-header: usbsidebandaudio.h
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.typenames: 
typedef_isUnnamed: false
req.umdf-ver: 
targetos: Windows
tech.root: audio
ms.custom: RS5
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - usbsidebandaudio.h
api_name:
 - _SIDEBANDAUDIO_USB_CONTROLLER_CONFIG_INFO_TYPE
 - SIDEBANDAUDIO_USB_CONTROLLER_CONFIG_INFO_TYPE
f1_keywords:
 - _SIDEBANDAUDIO_USB_CONTROLLER_CONFIG_INFO_TYPE
 - usbsidebandaudio/_SIDEBANDAUDIO_USB_CONTROLLER_CONFIG_INFO_TYPE
 - SIDEBANDAUDIO_USB_CONTROLLER_CONFIG_INFO_TYPE
 - usbsidebandaudio/SIDEBANDAUDIO_USB_CONTROLLER_CONFIG_INFO_TYPE
dev_langs:
 - c++
helpviewer_keywords:
 - _SIDEBANDAUDIO_USB_CONTROLLER_CONFIG_INFO_TYPE
---

## -description

Microsoft USB Audio Sideband USB controller Set of Parameters.

```cpp
// {7FE4A3DB-B637-4168-B853-4317079560D2}
DEFINE_GUID(SIDEBANDAUDIO_PARAMS_SET_USB_CONTROLLER,
    0x7fe4a3db, 0xb637, 0x4168, 0xb8, 0x53, 0x43, 0x17, 0x7, 0x95, 0x60, 0xd2);
```

## -enum-fields

### -field SIOP_TYPE_USBAUD_CONTROLLER_CONFIG_INFO_DEVICE_BEHIND_HUB

Provides USB sideband audio information, for example about a USB headset endpoint.

### -field SBUSBAUD_CONTROLLER_CONFIG_INFO_TYPE_INVALID

An invalid controller config type.

## -remarks

Some systems may not be able to support a USB Sideband device behind a hub.

## -see-also

[usbsidebandaudio.h](index.md)
