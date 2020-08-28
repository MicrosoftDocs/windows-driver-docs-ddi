---
UID: NS:netdevice._NET_DEVICE_RESET_DIAGNOSTICS_CAPABILITIES
title: NET_DEVICE_RESET_DIAGNOSTICS_CAPABILITIES
author: windows-driver-content
ms.topic: language-reference
ms.author: windowsdriverdev
ms.date: 07/02/2020
ms.custom: Fe
targetos: Windows
description: The NET_DEVICE_RESET_DIAGNOSTICS_CAPABILITIES structure describes a client driver's capabilities for collecting diagnostics during the device reset and recovery process.
keywords: ["EVT_NET_DEVICE_COLLECT_RESET_DIAGNOSTICS callback function"]
req.construct-type: structure
req.ddi-compliance:
req.dll:
req.header: netadaptercx.h
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

The **NET_DEVICE_RESET_DIAGNOSTICS_CAPABILITIES** structure describes a client driver's capabilities for collecting diagnostics during the device reset and recovery process.

## -struct-fields

### -field Size

The size of this structure, in bytes.

### -field ResetDiagnosticsGuid

A client driver specified global unique identifier (GUID). Developers can use this identifier to retrieve reset diagnostics. The client driver collects the diagnostics as secondary data in the full kernel dump captured in the device reset and recovery process.

### -field EvtNetDeviceCollectResetDiagnostics

A pointer to the client driver's implementation of the [*EVT_NET_DEVICE_COLLECT_RESET_DIAGNOSTICS*](nc-netdevice-evt_net_device_collect_reset_diagnostics.md) callback that collects device-specific reset diagnostics from a hardware device.

## -remarks

Client drivers initialize and register this structure in their [*EVT_WDF_DRIVER_DEVICE_ADD*](../wdfdriver/nc-wdfdriver-evt_wdf_driver_device_add.md) callback function.

Call [**NET_DEVICE_RESET_DIAGNOSTICS_CAPABILITIES_INIT**](nf-netdevice-net_device_reset_diagnostics_capabilities_init.md) to initialize this structure.

Call [**NetDeviceInitSetResetDiagnosticsCapabilities**](nf-netdevice-netdeviceinitsetresetdiagnosticscapabilities.md) to register this structure to the NetAdapterCx framework.

For more information, see [Register NET_DEVICE_RESET_DIAGNOSTICS_CAPABILITIES](/windows-hardware/drivers/netcx/platform-level-device-reset/#register-NET_DEVICE_RESET_DIAGNOSTICS_CAPABILITIES).

## -see-also

[Recovering an unresponsive NIC with NetAdapterCx PLDR](/windows-hardware/drivers/netcx/platform-level-device-reset/)

[*EVT_WDF_DRIVER_DEVICE_ADD*](../wdfdriver/nc-wdfdriver-evt_wdf_driver_device_add.md)

[*EVT_NET_DEVICE_COLLECT_RESET_DIAGNOSTICS*](nc-netdevice-evt_net_device_collect_reset_diagnostics.md)

[**NET_DEVICE_RESET_DIAGNOSTICS_CAPABILITIES_INIT**](nf-netdevice-net_device_reset_diagnostics_capabilities_init.md)

[**NetDeviceInitSetResetDiagnosticsCapabilities**](nf-netdevice-netdeviceinitsetresetdiagnosticscapabilities.md)
