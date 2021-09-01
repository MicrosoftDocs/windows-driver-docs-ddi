---
UID: NF:wificx.WifiDirectDeviceInitialize
tech.root: netvista
title: WifiDirectDeviceInitialize (wificx.h)
ms.date: 08/30/2021
ms.topic: language-reference
targetos: Windows
description: The WifiDirectDeviceInitialize function initializes a newly created WIFIDIRECTDEVICE object.
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
 - WifiDirectDeviceInitialize
f1_keywords:
 - WifiDirectDeviceInitialize
 - wificx/WifiDirectDeviceInitialize
dev_langs:
 - c++
---

## -description

The **WifiDirectDeviceInitialize** function initializes a newly created WIFIDIRECTDEVICE object.

## -parameters

### -param WifiDirectDevice

[_In_] A handle to a WIFIDIRECTDEVICE object obtained in a previous call to [**WifiDirectDeviceCreate**](nf-wificx-wifidirectdevicecreate.md).

## -returns

Returns STATUS_SUCCESS if the operation succeeds. Otherwise, this function may return an appropriate NTSTATUS error code.

## -remarks

The client calls **WifiDirectDeviceInitialize** from within its [*EvtWifiDeviceCreateWifiDirectDevice*](nc-wificx-evt_wifi_device_create_wifidirectdevice.md) routine.

For a code example of creating a WIFIDIRECTDEVICE object, see [Wi-Fi Direct (P2P) Support](/windows-hardware/drivers/netcx/writing-a-wificx-client-driver#wi-fi-driect-(p2p)-support).

## -see-also

[Wi-Fi Direct (P2P) Support](/windows-hardware/drivers/netcx/writing-a-wificx-client-driver#wi-fi-driect-(p2p)-support)

[*EvtWifiDeviceCreateWifiDirectDevice*](nc-wificx-evt_wifi_device_create_wifidirectdevice.md)

[**WifiDirectDeviceCreate**](nf-wificx-wifidirectdevicecreate.md)