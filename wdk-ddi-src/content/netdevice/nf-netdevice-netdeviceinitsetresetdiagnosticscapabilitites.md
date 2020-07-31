---
UID: NF:netdevice.NetDeviceInitSetResetDiagnosticsCapabilitites
title: NetDeviceInitSetResetDiagnosticsCapabilitites
author: windows-driver-content
ms.topic: language-reference
ms.author: windowsdriverdev
ms.date: 07/02/2020
ms.custom: Fe
targetos: Windows
keywords: ["NetDeviceInitSetResetDiagnosticsCapabilitites"]
description: The NetDeviceInitSetResetDiagnosticsCapabilitites method registers a client driver's NET_DEVICE_RESET_DIAGNOSTICS_CAPABILITIES to the framework.
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
 - NetDeviceInitSetResetDiagnosticsCapabilitites
f1_keywords:
 - netdevice/NetDeviceInitSetResetDiagnosticsCapabilitites
dev_langs:
 - c++
---

## -description

The **NetDeviceInitSetResetDiagnosticsCapabilitites** method registers a client driver's [**NET_DEVICE_RESET_DIAGNOSTICS_CAPABILITIES**](../netdevice/ns-netdevice-net_device_reset_diagnostics_capabilities.md) to the NetAdapterCx framework.

## -parameters

### -param DeviceInit

A pointer to a **WDFDEVICE_INIT** object that the client driver received in its [**EVT_WDF_DRIVER_DEVICE_ADD**](../wdfdriver/nc-wdfdriver-evt_wdf_driver_device_add.md) callback.

### -param ResetDiagnosticsCapabilities

A pointer to a client driver allocated and initialized [**NET_DEVICE_RESET_DIAGNOSTICS_CAPABILITIES**](../netdevice/ns-netdevice-net_device_reset_diagnostics_capabilities.md) structure.

## -remarks

A client driver typically calls the **NetDeviceInitSetResetDiagnosticsCapabilitites** method in its [**EVT_WDF_DRIVER_DEVICE_ADD**](../wdfdriver/nc-wdfdriver-evt_wdf_driver_device_add.md) callback.

Before calling this method, the client driver must initialize [**NET_DEVICE_RESET_DIAGNOSTICS_CAPABILITIES**](../netdevice/ns-netdevice-net_device_reset_diagnostics_capabilities.md) by calling the [**NET_DEVICE_RESET_DIAGNOSTICS_CAPABILITIES_INIT**](../netdevice/nf-netdevice-net_device_reset_diagnostics_capabilities_init.md) method.

## -see-also

[Recovering an unresponsive NIC with NetAdapterCx PLDR](/windows-hardware/drivers/netcx/platform-level-device-reset/)

[**EVT_WDF_DRIVER_DEVICE_ADD**](../wdfdriver/nc-wdfdriver-evt_wdf_driver_device_add.md)

[**NET_DEVICE_RESET_DIAGNOSTICS_CAPABILITIES**](../netdevice/ns-netdevice-net_device_reset_diagnostics_capabilities.md)

[**NET_DEVICE_RESET_DIAGNOSTICS_CAPABILITIES_INIT**](../netdevice/nf-netdevice-net_device_reset_diagnostics_capabilities_init.md)
