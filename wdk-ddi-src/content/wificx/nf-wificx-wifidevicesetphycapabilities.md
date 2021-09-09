---
UID: NF:wificx.WifiDeviceSetPhyCapabilities
tech.root: netvista
<<<<<<< HEAD
title: WifiDeviceSetPhyCapabilities (wificx.h)
ms.date: 08/26/2021
ms.topic: language-reference
targetos: Windows
description: The WifiDeviceSetPhyCapabilities function sets the PHY capabilities for a WiFiCx device.
=======
title: WifiDeviceSetPhyCapabilities
ms.date: 04/30/2021
targetos: Windows
description: "Microsoft reserves the WifiDeviceSetPhyCapabilities function for internal use only. Don't use this function in your code."
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
 - WifiDeviceSetPhyCapabilities
f1_keywords:
 - WifiDeviceSetPhyCapabilities
 - wificx/WifiDeviceSetPhyCapabilities
dev_langs:
 - c++
---

## -description

The **WifiDeviceSetPhyCapabilities** function sets the PHY capabilities for a WiFiCx device.

## -parameters

### -param Device

A handle to a framework device object the client driver obtained from a previous call to [**WdfDeviceCreate**](../wdfdevice/nf-wdfdevice-wdfdevicecreate.md).

### -param PhyCapabilities

A pointer to a client driver-allocated and initialized [**WIFI_PHY_CAPABILITIES**](ns-wificx-wifi_wifidirect_capabilities.md) structure.

## -returns

Returns STATUS_SUCCESS if the operation succeeds. Otherwise, this function may return an appropriate NTSTATUS error code.

## -remarks

Client drivers typically call **WifiDeviceSetPhyCapabilities** within [*EvtDevicePrepareHardware*](../wdfdevice/nc-wdfdevice-evt_wdf_device_prepare_hardware.md).

For more information see [Default (station) adapter creation flow](/windows-hardware/drivers/netcx/writing-a-wificx-client-driver#default-(station)-adapter-creation-flow).

## -see-also

[**WIFI_PHY_CAPABILITIES**](ns-wificx-wifi_wifidirect_capabilities.md)

[Default (station) adapter creation flow](/windows-hardware/drivers/netcx/writing-a-wificx-client-driver#default-(station)-adapter-creation-flow)