---
UID: NF:wificx.WifiDeviceSetStationCapabilities
tech.root: netvista
<<<<<<< HEAD
title: WifiDeviceSetStationCapabilities (wificx.h)
ms.date: 08/26/2021
ms.topic: language-reference
targetos: Windows
description: The WifiDeviceSetStationCapabilities function sets the station capabilities for a WiFiCx device.
=======
title: WifiDeviceSetStationCapabilities
ms.date: 04/30/2021
targetos: Windows
description: "Microsoft reserves the WifiDeviceSetStationCapabilities function for internal use only. Don't use this function in your code."
>>>>>>> main
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
<<<<<<< HEAD
req.target-min-winverclnt: Windows 11 
=======
req.target-min-winverclnt: Windows 11
>>>>>>> main
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
 - WifiDeviceSetStationCapabilities
f1_keywords:
 - WifiDeviceSetStationCapabilities
 - wificx/WifiDeviceSetStationCapabilities
dev_langs:
 - c++
---

## -description

The **WifiDeviceSetStationCapabilities** function sets the station capabilities for a WiFiCx device.

## -parameters

### -param Device

A handle to a framework device object the client driver obtained from a previous call to [**WdfDeviceCreate**](../wdfdevice/nf-wdfdevice-wdfdevicecreate.md).

### -param StationCapabilities

A pointer to a client driver-allocated and initialized [**WIFI_STATION_CAPABILITIES**](ns-wificx-wifi_station_capabilities.md) structure.

## -returns

Returns STATUS_SUCCESS if the operation succeeds. Otherwise, this function may return an appropriate NTSTATUS error code.

## -remarks

Client drivers typically call **WifiDeviceSetStationCapabilities** within [*EvtDevicePrepareHardware*](../wdfdevice/nc-wdfdevice-evt_wdf_device_prepare_hardware.md). For more information see [Default (station) adapter creation flow](/windows-hardware/drivers/netcx/writing-a-wificx-client-driver#default-(station)-adapter-creation-flow).

To indicate the ability to maintain [Secondary Sta connectivity](/windows-hardware/drivers/netcx/dual-sta-connectivity), the driver must set the **NumSecondaryStaBandCombinations** and **SecondaryStaBandsCombinations** fields of the [**WIFI_STATION_CAPABILITIES**](ns-wificx-wifi_station_capabilities.md) structure to non-zero values. If either value is **0** or **NULL**, then the Secondary Sta capability will not be set.

## -see-also

[**WIFI_STATION_CAPABILITIES**](ns-wificx-wifi_station_capabilities.md)

[Default (station) adapter creation flow](/windows-hardware/drivers/netcx/writing-a-wificx-client-driver#default-(station)-adapter-creation-flow)

