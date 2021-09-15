---
UID: NC:wificx.EVT_WIFI_DEVICE_CREATE_WIFIDIRECTDEVICE
tech.root: netvista
title: EVT_WIFI_DEVICE_CREATE_WIFIDIRECTDEVICE (wificx.h)
ms.date: 08/30/2021
ms.topic: language-reference
targetos: Windows
description: WiFiCx client drivers implement EvtWifiDeviceCreateWifiDirectDevice to create a WIFIDIRECTDEVICE object.
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: wificx.h
req.idl: 
req.include-header: 
req.irql: PASSIVE_LEVEL
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
 - LibDef
api_location:
 - wificx.h
api_name:
 - EVT_WIFI_DEVICE_CREATE_WIFIDIRECTDEVICE
f1_keywords:
 - EVT_WIFI_DEVICE_CREATE_WIFIDIRECTDEVICE
 - wificx/EVT_WIFI_DEVICE_CREATE_WIFIDIRECTDEVICE
dev_langs:
 - c++
---

## -description

WiFiCx client drivers implement *EvtWifiDeviceCreateWifiDirectDevice* to create a WIFIDIRECTDEVICE object.

## -parameters

### -param Device

[_In_] A handle to a framework device object that the client driver obtained from a previous call to [**WdfDeviceCreate**](../wdfdevice/nf-wdfdevice-wdfdevicecreate.md).

### -param WifiDirectDeviceInit

[_Inout_] A pointer to a WIFIDIRECT_DEVICE_INIT object that describes the initialization information for the WIFIDIRECTDEVICE object.

## -returns

This callback function returns STATUS_SUCCESS if the operation was successful. Otherwise, it returns an appropriate NTSTATUS error code.

## -remarks

A WiFiCx client driver registers the *EvtWifiDeviceCreateWifiDirectDevice* callback function by calling [**WiFiDeviceInitialize**](nf-wificx-wifideviceinitialize.md).

In its *EvtWifiDeviceCreateWifiDirectDevice* callback, the client driver:

- Calls [**WifiDirectDeviceCreate**](nf-wificx-wifidirectdevicecreate.md) to create the WIFIDIRECTDEVICE object.
- Calls [**WifiDirectDeviceInitialize**](nf-wificx-wifidirectdeviceinitialize.md) to initialize the object. 
- Calls [**WifiDirectDeviceGetPortId**](nf-wificx-wifidirectdevicegetportid.md) to determine the port id (which is used in command messages).

For a code example of implementing *EvtWifiDeviceCreateWifiDirectDevice*, see [Wi-Fi Direct (P2P) Support](/windows-hardware/drivers/netcx/writing-a-wificx-client-driver#wi-fi-driect-device-capabilities).

## -see-also

[Wi-Fi Direct (P2P) Support](/windows-hardware/drivers/netcx/writing-a-wificx-client-driver#wi-fi-driect-device-capabilities)

[**WifiDirectDeviceCreate**](nf-wificx-wifidirectdevicecreate.md)

[**WifiDirectDeviceInitialize**](nf-wificx-wifidirectdeviceinitialize.md)

[**WifiDirectDeviceGetPortId**](nf-wificx-wifidirectdevicegetportid.md)

