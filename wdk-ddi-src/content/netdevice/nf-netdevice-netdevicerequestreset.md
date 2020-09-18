---
UID: NF:netdevice.NetDeviceRequestReset
title: NetDeviceRequestReset
author: windows-driver-content
ms.topic: language-reference
ms.author: windowsdriverdev
ms.date: 07/02/2020
ms.custom: Fe
targetos: Windows
description: The NetDeviceRequestReset function triggers the NetAdapterCx framework to perform the platform-level device reset operation that recovers an unresponsive NIC device.
keywords: ["NetDeviceRequestReset function"]
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
 - NetDeviceRequestReset
f1_keywords:
 - netdevice/NetDeviceRequestReset
dev_langs:
 - c++
---

## -description

The **NetDeviceRequestReset** function triggers the NetAdapterCx framework to perform the platform-level device reset operation that recovers an unresponsive NIC device.

## -parameters

### -param Device

[in] The WDFDEVICE object the client driver previously created with a call to [**WdfDeviceCreate**](../wdfdevice/nf-wdfdevice-wdfdevicecreate.md).

## -remarks

A client driver calls **NetDeviceRequestReset** when it detects device failure. **NetDeviceRequestReset** returns immediately to the client driver. The driver can only call **NetDeviceRequestReset** at PASSIVE_LEVEL.

**NetDeviceRequestReset** is nonblocking and returns immediately to the client driver. The client driver should cancel any ongoing jobs that access the currently failed device.

We recommend that client drivers set up a [**NET_DEVICE_RESET_CAPABILITIES**](ns-netdevice-net_device_reset_capabilities.md) structure to collect meaningful reset diagnostics during the device reset and recovery process.
For more on how to collect reset diagnostics, see [Register the optional diagnostics collection callback](/windows-hardware/drivers/netcx/platform-level-device-reset/#register-the-optional-diagnostics-collection-callback).

## -see-also

[Recovering an unresponsive NIC with NetAdapterCx PLDR](/windows-hardware/drivers/netcx/platform-level-device-reset/)

[**WdfDeviceCreate**](../wdfdevice/nf-wdfdevice-wdfdevicecreate.md)

[**NET_DEVICE_RESET_CAPABILITIES**](ns-netdevice-net_device_reset_capabilities.md)
