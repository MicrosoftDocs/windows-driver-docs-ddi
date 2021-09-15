---
UID: NF:wificx.WifiDirectDeviceCreate
tech.root: netvista
title: WifiDirectDeviceCreate (wificx.h)
ms.date: 08/30/2021
ms.topic: language-reference
targetos: Windows
description: The WifiDirectDeviceCreate function creates a WIFIDIRECTDEVICE object.
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
 - WifiDirectDeviceCreate
f1_keywords:
 - WifiDirectDeviceCreate
 - wificx/WifiDirectDeviceCreate
dev_langs:
 - c++
---

## -description

Creates a WIFIDIRECTDEVICE object.

## -parameters

### -param WifiDirectDeviceInit

[_In_] A pointer to a caller-allocated WIFIDIRECT_DEVICE_INIT object.

### -param WifiDirectDeviceAttributes

[_In__opt_] A pointer to a WDF_OBJECT_ATTRIBUTES object that contains driver-supplied attributes for the new WIFIDIRECTDEVICE object.

### -param WifiDirectDevice

[_Out_] A pointer to a location that receives a handle to the new WIFIDIRECTDEVICE object.

## -returns

Returns STATUS_SUCCESS if the operation succeeds. Otherwise, this function may return an appropriate NTSTATUS error code.

## -remarks

The client calls **WifiDirectDeviceCreate** from within its [*EvtWifiDeviceCreateWifiDirectDevice*](nc-wificx-evt_wifi_device_create_wifidirectdevice.md) routine. Call [**WifiDirectDeviceInitialize**](nf-wificx-wifidirectdeviceinitialize.md) to initialize this object. 

For a code example of creating a WIFIDIRECTDEVICE object, see [Wi-Fi Direct (P2P) Support](/windows-hardware/drivers/netcx/writing-a-wificx-client-driver#wi-fi-driect-device-capabilities).


## -see-also

[*EvtWifiDeviceCreateWifiDirectDevice*](nc-wificx-evt_wifi_device_create_wifidirectdevice.md)

[**WifiDirectDeviceInitialize**](nf-wificx-wifidirectdeviceinitialize.md)

[Wi-Fi Direct (P2P) Support](/windows-hardware/drivers/netcx/writing-a-wificx-client-driver#wi-fi-driect-device-capabilities)