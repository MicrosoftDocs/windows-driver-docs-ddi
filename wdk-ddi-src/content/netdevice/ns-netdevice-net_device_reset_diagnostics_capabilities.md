---
UID: NS:netdevice._NET_DEVICE_RESET_DIAGNOSTICS_CAPABILITIES
title: NET_DEVICE_RESET_DIAGNOSTICS_CAPABILITIES
author: windows-driver-content
ms.topic: language-reference
ms.author: windowsdriverdev
ms.date: 07/02/2020
ms.custom: Fe
targetos: Windows
description: The NET_DEVICE_RESET_DIAGNOSTICS_CAPABILITIES structure describes the client driver's capabilities to collect diagnostics in the process of device reset and recovery.
keywords: ["EVT_NET_DEVICE_COLLECT_RESET_DIAGNOSTICS callback function"]
req.construct-type: structure
req.ddi-compliance:
req.dll:
req.header: netdevice.h
req.include-header:
req.kmdf-ver:
req.lib:
req.max-support:
req.redist:
req.target-min-winverclnt:
req.target-min-winversvr:
req.target-type:
req.typenames: NET_DEVICE_RESET_DIAGNOSTICS_CAPABILITIES
req.umdf-ver:
req.unicode-ansi:
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - netdevice.h
api_name:
 - _NET_DEVICE_RESET_DIAGNOSTICS_CAPABILITIES
 - NET_DEVICE_RESET_DIAGNOSTICS_CAPABILITIES
f1_keywords:
 - netdevice/_NET_DEVICE_RESET_DIAGNOSTICS_CAPABILITIES
 - netdevice/NET_DEVICE_RESET_DIAGNOSTICS_CAPABILITIES
dev_langs:
 - c++
---

## -description

The NET_DEVICE_RESET_DIAGNOSTICS_CAPABILITIES structure describes the client driver's capabilities to collect diagnostics in the process of device reset and recovery.

## -struct-fields

### -field Size

The size of this structure, in bytes.

### -field ResetDiagnosticsGuid

A client driver specified global unique identifier (GUID). Developers can retrieve client driver collected reset diagnostics with this identifier as secondary data in the full kernel dump captured in the process of device reset and recovery.

### -field EvtNetDeviceCollectResetDiagnostics

A pointer to the client driver's implementation of the [**EVT_NET_DEVICE_COLLECT_RESET_DIAGNOSTICS**](../netdevice/nc-netdevice-evt_net_device_collect_reset_diagnostics.md) callback, in which the client driver collects device-specific reset diagnostics from hardware device.

## -remarks

Call [**NET_DEVICE_RESET_DIAGNOSTICS_CAPABILITIES_INIT**](../netdevice/nf-netdevice-net_device_reset_diagnostics_capabilities_init.md) method to initialize this structure.
Call [**NetDeviceInitSetResetDiagnosticsCapabilitites**](../netdeivce/nf-netdevice-netdeviceinitsetresetdiagnosticscapabilitites.md) method to register this structure to the framework.
See [Register NET_DEVICE_RESET_DIAGNOSTICS_CAPABILITIES](/windows-hardware/drivers/netcx/platform-level-device-reset/#register-NET_DEVICE_RESET_DIAGNOSTICS_CAPABILITIES) for details.

## -see-also

[Recovering unresponsive NIC with NetAdapterCx PLDR](/windows-hardware/drivers/netcx/platform-level-device-reset/).
