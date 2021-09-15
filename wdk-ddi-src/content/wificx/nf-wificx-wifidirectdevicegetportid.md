---
UID: NF:wificx.WifiDirectDeviceGetPortId
tech.root: netvista
title: WifiDirectDeviceGetPortId (wificx.h)
ms.date: 08/30/2021
ms.topic: language-reference
targetos: Windows
description: The WifiDirectDeviceGetPortId function gets the Wi-Fi Direct port ID.
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
 - HeaderDef
api_location:
 - wificx.h
api_name:
 - WifiDirectDeviceGetPortId
f1_keywords:
 - WifiDirectDeviceGetPortId
 - wificx/WifiDirectDeviceGetPortId
dev_langs:
 - c++
---

## -description

Gets the Wi-Fi Direct port ID.

## -parameters

### -param WifiDirectDevice

[_In_] A handle to a WIFIDIRECTDEVICE object obtained in a previous call to [**WifiDirectDeviceCreate**](nf-wificx-wifidirectdevicecreate.md).

## -returns

Returns the Wi-Fi Direct port ID.

## -remarks

The client calls **WifiDirectDeviceGetPortId** from within its [*EvtWifiDeviceCreateWifiDirectDevice*](nc-wificx-evt_wifi_device_create_wifidirectdevice.md) routine.

For a code example of creating a WIFIDIRECTDEVICE object, see [Wi-Fi Direct (P2P) Support](/windows-hardware/drivers/netcx/writing-a-wificx-client-driver#wi-fi-driect-device-capabilities).

## -see-also

[**WifiDirectDeviceCreate**](nf-wificx-wifidirectdevicecreate.md)

[*EvtWifiDeviceCreateWifiDirectDevice*](nc-wificx-evt_wifi_device_create_wifidirectdevice.md) 

[Wi-Fi Direct (P2P) Support](/windows-hardware/drivers/netcx/writing-a-wificx-client-driver#wi-fi-driect-device-capabilities)