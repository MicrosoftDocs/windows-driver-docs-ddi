---
UID: NF:netdevice.NET_DEVICE_RESET_DIAGNOSTICS_CAPABILITIES_INIT
title: NET_DEVICE_RESET_DIAGNOSTICS_CAPABILITIES_INIT
author: windows-driver-content
ms.date: 07/02/2020
ms.topic: language-reference
ms.author: windowsdriverdev
ms.custom: Fe
keywords: ["NET_DEVICE_RESET_DIAGNOSTICS_CAPABILITIES_INIT function"]
targetos: Windows
description: The NET_DEVICE_RESET_DIAGNOSTICS_CAPABILITIES_INIT method initializes a NET_DEVICE_RESET_DIAGNOSTICS_CAPABILITIES structure.
req.assembly:
req.construct-type: function
req.ddi-compliance:
req.dll:
req.header: netdevice.h
req.idl:
req.include-header:
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
 -
api_location:
 - netdevice.h
api_name:
 - NET_DEVICE_RESET_DIAGNOSTICS_CAPABILITIES_INIT
f1_keywords:
 - netdevice/NET_DEVICE_RESET_DIAGNOSTICS_CAPABILITIES_INIT
dev_langs:
 - c++
---

# NET_DEVICE_RESET_DIAGNOSTICS_CAPABILITIES_INIT function

## -description

The **NET_DEVICE_RESET_DIAGNOSTICS_CAPABILITIES_INIT** method initializes a [**NET_DEVICE_RESET_DIAGNOSTICS_CAPABILITIES**](../netdevice/ns-netdevice-net_device_reset_diagnostics_capabilities.md) structure.

## -parameters

### -param ResetDiagnosticsCapabilities

A pointer to a driver-allocated **NET_DEVICE_RESET_DIAGNOSTICS_CAPABILITIES** structure.

### -param ResetDiagnosticsGuid

A client driver specified global unique identifier (GUID). Developers can retrieve client driver collected reset diagnostics with this identifier as secondary data in the full kernel dump captured in the process of device reset and recovery.

### -param EvtNetDeviceCollectResetDiagnostics

A pointer to the client driver's implementation of the [**EVT_NET_DEVICE_COLLECT_RESET_DIAGNOSTICS**](../netdevice/nc-netdevice-evt_net_device_collect_reset_diagnostics.md) callback, in which the client driver collects device-specific reset diagnostics from hardware device.

## -remarks

This method zeros out the **NET_DEVICE_RESET_DIAGNOSTICS_CAPABILITIES** structure, then fills in the **Size** member, and sets the **ResetDiagnosticsGuid** member and **EvtNetDeviceCollectResetDiagnostics** member with the corresponding input parameters.

## -see-also

[Recovering unresponsive NIC with NetAdapterCx PLDR](/windows-hardware/drivers/netcx/platform-level-device-reset/).
