---
UID: NF:wificx.WifiDeviceSetBandCapabilities
tech.root: netvista
title: WifiDeviceSetBandCapabilities (wificx.h)
ms.date: 03/06/2024
targetos: Windows
description: The WifiDeviceSetBandCapabilities function sets the band capabilities for a WiFiCx device.
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
 - WifiDeviceSetBandCapabilities
f1_keywords:
 - WifiDeviceSetBandCapabilities
 - wificx/WifiDeviceSetBandCapabilities
dev_langs:
 - c++
---

## -description

The **WifiDeviceSetBandCapabilities** function sets the band capabilities for a WiFiCx device.

## -parameters

### -param Device

A handle to a framework device object the client driver obtained from a previous call to [**WdfDeviceCreate**](../wdfdevice/nf-wdfdevice-wdfdevicecreate.md).

### -param BandCapabilities

A pointer to a client driver-allocated and initialized [**WIFI_BAND_CAPABILITIES**](ns-wificx-wifi_band_capabilities.md) structure.

## -returns

Returns STATUS_SUCCESS if the operation succeeds. Otherwise, this function may return an appropriate NTSTATUS error code.

## -remarks

Client drivers typically call **WifiDeviceSetBandCapabilities** within [*EvtDevicePrepareHardware*](../wdfdevice/nc-wdfdevice-evt_wdf_device_prepare_hardware.md).

Call [**WIFI_BAND_CAPABILITIES_INIT**](nf-wificx-wifi_band_capabilities_init.md) to initialize the **WIFI_BAND_CAPABILITIES** structure and fill in its **Size** field. Then call **WifiDeviceSetBandCapabilities** to report band capabilities to WiFiCx.

For more information see [Default (station) adapter creation flow](/windows-hardware/drivers/netcx/writing-a-wificx-client-driver#default-(station)-adapter-creation-flow).

## -see-also

[**WIFI_BAND_CAPABILITIES**](ns-wificx-wifi_band_capabilities.md)

[**WIFI_BAND_CAPABILITIES_INIT**](nf-wificx-wifi_band_capabilities_init.md)

[Default (station) adapter creation flow](/windows-hardware/drivers/netcx/writing-a-wificx-client-driver#default-(station)-adapter-creation-flow)