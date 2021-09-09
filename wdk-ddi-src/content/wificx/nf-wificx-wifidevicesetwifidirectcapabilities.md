---
UID: NF:wificx.WifiDeviceSetWiFiDirectCapabilities
tech.root: netvista
title: WifiDeviceSetWiFiDirectCapabilities (wificx.h)
ms.date: 08/26/2021
ms.topic: language-reference
targetos: Windows
description: The WifiDeviceSetWiFiDirectCapabilities function sets the Wi-Fi Direct capabilities for a WiFiCx device.
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
 - WifiDeviceSetWiFiDirectCapabilities
f1_keywords:
 - WifiDeviceSetWiFiDirectCapabilities
 - wificx/WifiDeviceSetWiFiDirectCapabilities
dev_langs:
 - c++
---

## -description

The **WifiDeviceSetWiFiDirectCapabilities** function sets the Wi-Fi Direct capabilities for a WiFiCx device.

## -parameters

### -param Device

A handle to a framework device object the client driver obtained from a previous call to [**WdfDeviceCreate**](../wdfdevice/nf-wdfdevice-wdfdevicecreate.md).

### -param WiFiDirectCapabilities

A pointer to a client driver-allocated and initialized [**WIFI_WIFIDIRECT_CAPABILITIES**](ns-wificx-wifi_wifidirect_capabilities.md) structure.

## -returns

Returns STATUS_SUCCESS if the operation succeeds. Otherwise, this function may return an appropriate NTSTATUS error code.

## -remarks

Client drivers need to call **WifiDeviceSetWiFiDirectCapabilities** in the set device capabilities phase. Typically this is within [*EvtDevicePrepareHardware*](../wdfdevice/nc-wdfdevice-evt_wdf_device_prepare_hardware.md).

For an example showing how to set Wi-Fi Direct capabilities, see [Wi-Fi Direct (P2P) Support](/windows-hardware/drivers/netcx/writing-a-wificx-client-driver#wi-fi-direct-(p2p)-support)


## -see-also

[**WIFI_WIFIDIRECT_CAPABILITIES**](ns-wificx-wifi_wifidirect_capabilities.md)

[Wi-Fi Direct (P2P) Support](/windows-hardware/drivers/netcx/writing-a-wificx-client-driver#wi-fi-direct-(p2p)-support)