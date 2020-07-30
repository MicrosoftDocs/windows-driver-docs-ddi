---
UID: NF:netdevice.NetDeviceStoreResetDiagnostics
title: NetDeviceStoreResetDiagnostics
author: windows-driver-content
ms.topic: language-reference
ms.author: windowsdriverdev
ms.date: 07/02/2020
ms.custom: Fe
targetos: Windows
description: The **NetDeviceStoreResetDiagnostics** method stores client driver collected reset diagnostics into the framework.
keywords: ["NetDeviceStoreResetDiagnostics function"]
req.assembly:
req.construct-type: function
req.ddi-compliance:
req.dll:
req.header: netdevice.h
req.idl:
req.include-header:
req.irql:
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
 - NetDeviceStoreResetDiagnostics
f1_keywords:
 - netdevice/NetDeviceStoreResetDiagnostics
dev_langs:
 - c++
---

## -description

The **NetDeviceStoreResetDiagnostics** method stores client driver collected reset diagnostics into the NetAdapterCx framework.

## -parameters

### -param Device

The WDFDEVICE object the client driver previously created with a call to [**WdfDeviceCreate**](../wdfdevice/nf-wdfdevice-wdfdevicecreate.md).

### -param ResetDiagnosticsSize

The size, in bytes, of the **ResetDiagnosticsBuffer**. The maximum size of reset diagnostics the framework accepts is 1 MBytes.

### -param ResetDiagnosticsBuffer

A pointer to the data buffer that holds the reset diagnostics data. The data buffer can come from either paged or non-paged pool.

## -remarks

The only valid scenario to invoke the **NetDeviceStoreResetDiagnostics** method is in a client driver's [**EVT_NET_DEVICE_COLLECT_RESET_DIAGNOSTICS**](../netdevice/nc-netdevice-evt_net_device_collect_reset_diagnostics.md) callback.
See [Implement EVT_NET_DEVICE_COLLECT_RESET_DIAGNOSTICS](/windows-hardware/drivers/netcx/platform-level-device-reset/#implement-EVT_NET_DEVICE_COLLECT_RESET_DIAGNOSTICS) for how to correctly use the **NetDeviceStoreResetDiagnostics** method.

## -see-also

[Recovering an unresponsive NIC with NetAdapterCx PLDR](/windows-hardware/drivers/netcx/platform-level-device-reset/)

[**WdfDeviceCreate**](../wdfdevice/nf-wdfdevice-wdfdevicecreate.md)

[**EVT_NET_DEVICE_COLLECT_RESET_DIAGNOSTICS**](../netdevice/nc-netdevice-evt_net_device_collect_reset_diagnostics.md)