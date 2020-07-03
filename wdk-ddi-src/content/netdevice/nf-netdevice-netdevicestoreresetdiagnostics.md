---
UID: NF:netdevice.NetDeviceStoreResetDiagnostics
title: NetDeviceStoreResetDiagnostics
author: windows-driver-content
ms.topic: language-reference
ms.author: windowsdriverdev
ms.date: 07/02/2020
ms.custom: Fe
targetos: Windows
description: Submit collected reset diagnostics to the framework.
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

The **NetDeviceStoreResetDiagnostics** method stores client driver collected reset diagnostics into the framework.

## -parameters

### -param Device

The WDFDEVICE object the client driver previously created with a call to [**WdfDeviceCreate**](../wdfdevice/nf-wdfdevice-wdfdevicecreate.md).

### -param ResetDiagnosticsSize

The size, in bytes, of the **ResetDiagnosticsBuffer**. The maximum amount of reset diagnostics accepted by the framework is 1 MBytes.

### -param ResetDiagnosticsBuffer

A pointer to the data buffer that holds the reset diagnostics data. The data buffer can come from either paged or non-paged pool.

## -remarks

After client driver collects reset diagnostics in its implementation of [**EVT_NET_DEVICE_COLLECT_RESET_DIAGNOSTICS**](../netdevice/nc-netdevice-evt_net_device_collect_reset_diagnostics.md) callback, it should submit diagnostics as a flat data buffer to the framework by calling the **NetDeviceStoreResetDiagnostics** method.
This is the only valid scenarios to call the **NetDeviceStoreResetDiagnostics** method.
The framework will bugcheck the client driver if it calls **NetDeviceStoreResetDiagnostics** outside of **EVT_NET_DEVICE_COLLECT_RESET_DIAGNOSTICS** callback, or calls **NetDeviceStoreResetDiagnostics** multiple times.
The client driver must calls **NetDeviceStoreResetDiagnostics** API at PASSIVE_LEVEL.
Once The **NetDeviceStoreResetDiagnostics** method returns, it is fine for client drivers to free the collected diagnostics data, that is, the data buffer pointed by **ResetDiagnosticsBuffer**.
For more info, see [Recovering unresponsive NIC with platform-level device reset](/windows-hardware/drivers/netcx/platform-level-device-reset).

## -see-also

