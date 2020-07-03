---
UID: NF:netdevice.NetDeviceRequestReset
title: NetDeviceRequestReset
author: windows-driver-content
ms.topic: language-reference
ms.author: windowsdriverdev
ms.date: 07/02/2020
ms.custom: Fe
targetos: Windows
description: Request platform-level device reset to recover unresponsive device.
keywords: ["NetDeviceRequestReset function"]
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
 - NetDeviceRequestReset
f1_keywords:
 - netdevice/NetDeviceRequestReset
dev_langs:
 - c++
---

## -description

The **NetDeviceRequestReset** method requests the framework to perform platform-level device reset in order to recover unresponsive NIC device.

## -parameters

### -param Device

The WDFDEVICE object the client driver previously created with a call to [**WdfDeviceCreate**](../wdfdevice/nf-wdfdevice-wdfdevicecreate.md).

## -remarks

Client drivers are recommended to set up their [**NET_DEVICE_RESET_DIAGNOSTICS_CAPABILITIES**](../netdevice/ns-netdevice-net_device_reset_diagnostics_capabilities.md) before calling the **NetDeviceRequestReset** method, in order to help the framework to collect meaningful reset diagnostics upon device reset.
The **NET_DEVICE_RESET_DIAGNOSTICS_CAPABILITIES** method is nonblocking; it returns immediately to the client driver such that client driver can cancel any ongoing jobs that accesses the already failed device. If a client driver implements [**EVT_NET_DEVICE_COLLECT_RESET_DIAGNOSTICS**](../netdevice/nc-netdevice-evt_net_device_collect_reset_diagnostics.md) callback, it should synchronize the accesses to device hardware from both their **EVT_NET_DEVICE_COLLECT_RESET_DIAGNOSTICS** and the ongoing jobs.
For more info, see [Recovering unresponsive NIC with platform-level device reset](/windows-hardware/drivers/netcx/platform-level-device-reset).

## -see-also

