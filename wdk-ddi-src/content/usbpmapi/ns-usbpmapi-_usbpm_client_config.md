---
UID: NS:usbpmapi._USBPM_CLIENT_CONFIG
title: _USBPM_CLIENT_CONFIG (usbpmapi.h)
description: The configuration structure used in the registering the client driver with the Policy Manager
ms.assetid: 744fbd96-7286-4f48-9c00-6a3206f0ee37
ms.date: 09/30/2018
f1_keywords:
 - "usbpmapi/_USBPM_CLIENT_CONFIG"
tech.root: usbref
ms.keywords: _USBPM_CLIENT_CONFIG, USBPM_CLIENT_CONFIG, *PUSBPM_CLIENT_CONFIG, 
req.header: usbpmapi.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 1809
req.target-min-winversvr:
req.kmdf-ver: 1.27
req.umdf-ver: 2.27
req.lib: 
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.typenames: USBPM_CLIENT_CONFIG, *PUSBPM_CLIENT_CONFIG
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- usbpmapi.h
api_name: 
- _USBPM_CLIENT_CONFIG
product:
- Windows
targetos: Windows
ms.custom: RS5
---

# _USBPM_CLIENT_CONFIG structure

## -description
The configuration structure used in the registering the client driver with the Policy Manager. This structure is used in the [**UsbPm_Register**](nf-usbpmapi-usbpm_register.md) call.

## -struct-fields

### -field Version
Version of this structure. 

### -field AccessDesired
A bitwise-OR of the [**USBPM_ACCESS_TYPE**](ne-usbpmapi-_usbpm_access_type.md) values.
 
### -field EventCallback
A pointer to the client driver's implementation of the [**USBPM_EVENT_CALLBACK**](nc-usbpmapi-evt_usbpm_event_callback.md) callback function. 
 
### -field Context
A driver-defined context structure.
 
### -field ExtraInfo
A pointer to a USBPM_CLIENT_CONFIG_EXTRA_INFO structure that contains additional information, such as the WDM device object associated with the client driver. 

## -remarks

## -see-also
[**UsbPm_Register**](nf-usbpmapi-usbpm_register.md) 
