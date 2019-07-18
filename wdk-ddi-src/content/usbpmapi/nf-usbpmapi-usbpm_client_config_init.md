---
UID: NF:usbpmapi.USBPM_CLIENT_CONFIG_INIT
title: USBPM_CLIENT_CONFIG_INIT function (usbpmapi.h)
description: Initializes a **USBPM_CLIENT_CONFIG** structure.
ms.assetid: af50623f-d31a-47d9-b1dd-6472fd3bee04
ms.date: 09/30/2018
ms.topic: function
f1_keywords:
 - "usbpmapi/USBPM_CLIENT_CONFIG_INIT"
ms.keywords: USBPM_CLIENT_CONFIG_INIT
tech.root: usbref
req.header: usbpmapi.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 1809
req.target-min-winversvr:
req.kmdf-ver: 1.27
req.umdf-ver: 2.27
req.lib:
req.dll:
req.irql: 
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- usbpmapi.h
api_name: 
- USBPM_CLIENT_CONFIG_INIT
product:
- Windows
targetos: Windows


ms.custom: RS5
---

# USBPM_CLIENT_CONFIG_INIT function


## -description

Initializes a [**USBPM_CLIENT_CONFIG**](ns-usbpmapi-_usbpm_client_config.md) structure. The client driver must call this function before calling [**UsbPm_Register**](nf-usbpmapi-usbpm_register.md).

## -parameters

### -param ClientConfig
[Out] A pointer to a [**USBPM_CLIENT_CONFIG**](ns-usbpmapi-_usbpm_client_config.md) to initialize.
### -param AccessDesired
[In] A bitwise-OR of the flags defined by the [**USBPM_ACCESS_TYPE**](ne-usbpmapi-_usbpm_access_type.md) enumeration that indicates the type of access the client driver requires.
### -param EventCallback
[In] A pointer to the [**EVT_USBPM_EVENT_CALLBACK**](nc-usbpmapi-evt_usbpm_event_callback.md) callback function implemented by the client driver.
### -param ExtraInfo
[In] A pointer to a [**USBPM_CLIENT_CONFIG_EXTRA_INFO**](ns-usbpmapi-_usbpm_client_config_extra_info.md) structure that contains optional information such as the WDM device object.

## -returns

## -remarks

## -see-also
