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
description: Advertises client driver's NET_DEVICE_RESET_DIAGNOSTICS_CAPABILITIES to framework.
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

The **NetDeviceInitSetResetDiagnosticsCapabilitites** method registers a client driver's NET_DEVICE_RESET_DIAGNOSTICS_CAPABILITIES to the framework.

## -parameters

### -param DeviceInit

A pointer to a WDFDEVICE_INIT object that the client driver received in its [**EvtDriverDeviceAdd**](../wdfdriver/nc-wdfdriver-evt_wdf_driver_device_add.md) routine.

### -param ResetDiagnosticsCapabilities

A pointer to a client driver allocated and initialized [**NET_DEVICE_RESET_DIAGNOSTICS_CAPABILITIES**](../netdevice/E:\WdkDdi\wdk-ddi-src\content\netdevice\ns-netdevice-net_device_reset_diagnostics_capabilities.md) structure.

## -remarks

A client driver typically calls **NetDeviceInitSetResetDiagnosticsCapabilitites** method from within its [**EvtDriverDeviceAdd**](../wdfdriver/nc-wdfdriver-evt_wdf_driver_device_add.md) callback.
Initialize [**NET_DEVICE_RESET_DIAGNOSTICS_CAPABILITIES**](../netdevice/E:\WdkDdi\wdk-ddi-src\content\netdevice\ns-netdevice-net_device_reset_diagnostics_capabilities.md) by calling [**NET_DEVICE_RESET_DIAGNOSTICS_CAPABILITIES_INIT**](../netdevice/nf-netdevice-net_device_reset_diagnostics_capabilities_init.md) method before calling this method.


## -see-also

[Recovering unresponsive NIC with platform-level device reset](/windows-hardware/drivers/netcx/platform-level-device-reset)
