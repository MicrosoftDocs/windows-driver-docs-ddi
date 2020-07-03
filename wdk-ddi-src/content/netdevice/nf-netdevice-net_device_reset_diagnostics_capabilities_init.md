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

A pointer to a driver-allocated [**NET_DEVICE_RESET_DIAGNOSTICS_CAPABILITIES**](../netdevice/ns-netdevice-net_device_reset_diagnostics_capabilities.md) structure.

### -param ResetDiagnosticsGuid

A client driver specified global unique identifier (GUID). The developer of the client driver can retrieve the reset diagnostics with this identifier as secondary data in the full kernel dump captured during device reset.

### -param EvtNetDeviceCollectResetDiagnostics

A pointer to the client driver's implementation of the [**EvtNetDeviceCollectResetDiagnostics**](../netdevice/nc-netdevice-evt_net_device_collect_reset_diagnostics.md) callback function for collecting reset diagnostics from hardware device.

## -remarks

This method zero out the [**NET_DEVICE_RESET_DIAGNOSTICS_CAPABILITIES**](../netdevice/ns-netdevice-net_device_reset_diagnostics_capabilities.md) structure, then fills in the [**Size**] member, and set the [**ResetDiagnosticsGuid**] and [**EvtNetDeviceCollectResetDiagnostics**] member with the corresponding input parameters.

After calling this method to initialize the **NET_DEVICE_RESET_DIAGNOSTICS_CAPABILITIES** structure, client driver should call [**NetDeviceInitSetResetDiagnosticsCapabilitites**](../netdevice/nf-netdevice-netdeviceinitsetresetdiagnosticscapabilitites.md) method to register this structure to the framework.

The framework utilizes the [**NET_DEVICE_RESET_DIAGNOSTICS_CAPABILITIES**](../netdevice/ns-netdevice-net_device_reset_diagnostics_capabilities.md) structure to collect reset diagnostics upon device reset and recovering.
For more info, see [Recovering unresponsive NIC with platform-level device reset](/windows-hardware/drivers/netcx/platform-level-device-reset).

## -see-also

