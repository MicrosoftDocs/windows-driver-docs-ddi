---
UID: NF:netdevice.NET_DEVICE_RESET_CAPABILITIES_INIT
title: NET_DEVICE_RESET_CAPABILITIES_INIT
author: windows-driver-content
ms.date: 07/02/2020
ms.topic: language-reference
ms.author: windowsdriverdev
ms.custom: Fe
keywords: ["NET_DEVICE_RESET_CAPABILITIES_INIT function"]
targetos: Windows
description: The NET_DEVICE_RESET_CAPABILITIES_INIT function initializes a NET_DEVICE_RESET_CAPABILITIES structure.
req.assembly:
req.construct-type: function
req.ddi-compliance:
req.dll:
req.header: netadaptercx.h
req.idl:
req.include-header: netadaptercx.h
req.irql: PASSIVE_LEVEL
req.kmdf-ver:
req.lib:
req.max-support:
req.namespace:
req.redist:
req.target-min-winverclnt:
req.target-min-winversvr:
req.target-type:
req.type-library:
req.umdf-ver:
req.unicode-ansi:
topic_type:
 - apiref
api_type:
 - LibDef
api_location:
 - netdevice.h
api_name:
 - NET_DEVICE_RESET_CAPABILITIES_INIT
f1_keywords:
 - netdevice/NET_DEVICE_RESET_CAPABILITIES_INIT
dev_langs:
 - c++
---

# NET_DEVICE_RESET_CAPABILITIES_INIT function

## -description

The **NET_DEVICE_RESET_CAPABILITIES_INIT** function initializes a [**NET_DEVICE_RESET_CAPABILITIES**](ns-netdevice-net_device_reset_capabilities.md) structure.

## -parameters

### -param ResetDiagnosticsCapabilities

[out] A pointer to a driver-allocated [**NET_DEVICE_RESET_CAPABILITIES**](ns-netdevice-net_device_reset_capabilities.md) structure.

### -param ResetDiagnosticsGuid

[in] A client driver specified global unique identifier (GUID). Developers can use this identifier to retrieve reset diagnostics. The client driver collects the reset diagnostics as secondary data in the full kernel dump captured in the process of device reset and recovery.

### -param EvtNetDeviceCollectResetDiagnostics

[in] A pointer to the client driver's implementation of the [**EVT_NET_DEVICE_COLLECT_RESET_DIAGNOSTICS**](nc-netdevice-evt_net_device_collect_reset_diagnostics.md) callback that collects device-specific reset diagnostics from a hardware device.

## -remarks

A client driver typically calls **NET_DEVICE_RESET_CAPABILITIES_INIT** in its [*EVT_WDF_DRIVER_DEVICE_ADD*](../wdfdriver/nc-wdfdriver-evt_wdf_driver_device_add.md) callback.

This function zeros out the [**NET_DEVICE_RESET_CAPABILITIES**](ns-netdevice-net_device_reset_capabilities.md) structure and fills in its **Size** member. Then it sets the **ResetDiagnosticsGuid** member and ***EvtNetDeviceCollectResetDiagnostics*** member with the corresponding input parameters.

## -see-also

[Recovering an unresponsive NIC with NetAdapterCx PLDR](/windows-hardware/drivers/netcx/platform-level-device-reset/)

[*EVT_WDF_DRIVER_DEVICE_ADD*](../wdfdriver/nc-wdfdriver-evt_wdf_driver_device_add.md)

[**NET_DEVICE_RESET_CAPABILITIES**](ns-netdevice-net_device_reset_capabilities.md)

[*EVT_NET_DEVICE_COLLECT_RESET_DIAGNOSTICS*](nc-netdevice-evt_net_device_collect_reset_diagnostics.md)
