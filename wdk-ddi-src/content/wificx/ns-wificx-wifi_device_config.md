---
UID: NS:wificx._WIFI_DEVICE_CONFIG
tech.root: netvista
title: WIFI_DEVICE_CONFIG (wificx.h)
ms.date: 08/18/2021
ms.topic: language-reference
targetos: Windows
description: The WIFI_DEVICE_CONFIG structure contains pointers to a client driver's WiFiCx-specific callback functions.
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: wificx.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 11 
req.target-min-winversvr: Windows Server 2022
req.target-type: 
req.typenames: WIFI_DEVICE_CONFIG
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wificx.h
api_name:
 - _WIFI_DEVICE_CONFIG
 - WIFI_DEVICE_CONFIG
f1_keywords:
 - _WIFI_DEVICE_CONFIG
 - wificx/_WIFI_DEVICE_CONFIG
 - WIFI_DEVICE_CONFIG
 - wificx/WIFI_DEVICE_CONFIG
dev_langs:
 - c++
---

## -description

The **WIFI_DEVICE_CONFIG** structure contains pointers to a client driver's WiFiCx-specific callback functions. The client driver must supply an initialized **WIFI_DEVICE_CONFIG** structure as an input parameter to [**WiFiDeviceInitialize**](nf-wificx-wifideviceinitialize.md).


## -struct-fields

### -field Size

The size of this **WIFI_DEVICE_CONFIG** structure, in bytes.

### -field WdiVersion

The WDI version.

### -field SendCommand

A pointer to the client driver's implementation of the [*EVT_WIFI_DEVICE_SEND_COMMAND*](nc-wificx-evt_wifi_device_send_command.md) callback function.

### -field CreateAdapter

A pointer to the client driver's implementation of the [*EVT_WIFI_DEVICE_CREATE_ADAPTER*](nc-wificx-evt_wifi_device_create_adapter.md) callback function.

### -field CreateWifiDirectDevice

A pointer to the client driver's implementation of the [*EVT_WIFI_DEVICE_CREATE_WIFIDIRECTDEVICE*](nc-wificx-evt_wifi_device_create_wifidirectdevice.md) callback function.

## -remarks

Call [**WIFI_DEVICE_CONFIG_INIT**](nf-wificx-wifi_device_config_init.md) to initialize this structure.

## -see-also

[**WiFiDeviceInitialize**](nf-wificx-wifideviceinitialize.md)

[*EVT_MBB_DEVICE_CREATE_ADAPTER*](nc-wificx-evt_wifi_device_create_adapter.md)

[*EVT_WIFI_DEVICE_SEND_COMMAND*](nc-wificx-evt_wifi_device_send_command.md)

[*EVT_WIFI_DEVICE_CREATE_WIFIDIRECTDEVICE*](nc-wificx-evt_wifi_device_create_wifidirectdevice.md)

[**WIFI_DEVICE_CONFIG_INIT**](nf-wificx-wifi_device_config_init.md)