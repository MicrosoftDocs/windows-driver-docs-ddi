---
UID: NF:wificx.WIFI_DEVICE_CONFIG_INIT
tech.root: netvista
title: WIFI_DEVICE_CONFIG_INIT (wificx.h)
ms.date: 12/28/2021
ms.topic: language-reference
targetos: Windows
description: The WIFI_DEVICE_CONFIG_INIT function initializes the WIFI_DEVICE_CONFIG structure.
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: wificx.h
req.idl: 
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Windows 11 
req.target-min-winversvr: Windows Server 2022
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wificx.h
api_name:
 - WIFI_DEVICE_CONFIG_INIT
f1_keywords:
 - WIFI_DEVICE_CONFIG_INIT
 - wificx/WIFI_DEVICE_CONFIG_INIT
dev_langs:
 - c++
---

## -description

The **WIFI_DEVICE_CONFIG_INIT** function initializes the [**WIFI_DEVICE_CONFIG**](ns-wificx-wifi_device_config.md) structure.

## -parameters

### -param Config

[_Out_] A pointer to the client driver-allocated [**WIFI_DEVICE_CONFIG**](ns-wificx-wifi_device_config.md) structure.

### -param WdiVersion

[_In_] The WDI version.

### -param SendCommand

[_In_] A pointer to the client driver's implementation of the [*EVT_WIFI_DEVICE_SEND_COMMAND*](nc-wificx-evt_wifi_device_send_command.md) callback function.

### -param CreateAdapter

[_In_] A pointer to the client driver's implementation of the [*EVT_WIFI_DEVICE_CREATE_ADAPTER*](nc-wificx-evt_wifi_device_create_adapter.md) callback function.

### -param CreateWifiDirectDevice

[_In_] A pointer to the client driver's implementation of the [*EVT_WIFI_DEVICE_CREATE_WIFIDIRECTDEVICE*](nc-wificx-evt_wifi_device_create_wifidirectdevice.md) callback function.

## -remarks

The client driver calls this function from its [*EVT_WDF_DRIVER_DEVICE_ADD*](../wdfdriver/nc-wdfdriver-evt_wdf_driver_device_add.md) event callback function in preparation for calling [**WiFiDeviceInitialize**](nf-wificx-wifideviceinitialize.md).

## -see-also

[Writing a WiFiCx client driver](/windows-hardware/drivers/netcx/writing-a-wificx-client-driver)

[**WIFI_DEVICE_CONFIG**](ns-wificx-wifi_device_config.md)

[*EVT_WIFI_DEVICE_SEND_COMMAND*](nc-wificx-evt_wifi_device_send_command.md)

[*EVT_WIFI_DEVICE_CREATE_ADAPTER*](nc-wificx-evt_wifi_device_create_adapter.md)

[*EVT_WIFI_DEVICE_CREATE_WIFIDIRECTDEVICE*](nc-wificx-evt_wifi_device_create_wifidirectdevice.md)

[**WiFiDeviceInitialize**](nf-wificx-wifideviceinitialize.md)

