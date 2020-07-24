---
UID: NF:netdevice.NetDeviceRequestReset
title: NetDeviceRequestReset
author: windows-driver-content
ms.topic: language-reference
ms.author: windowsdriverdev
ms.date: 07/02/2020
ms.custom: Fe
targetos: Windows
description: The NetDeviceRequestReset method requests the framework to reset and recover unresponsive NIC device.
keywords: ["NetDeviceRequestReset function"]
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

The **NetDeviceRequestReset** method can only be called at PASSIVE_LEVEL.
This method is nonblocking; it returns immediately to the client driver and the client driver should cancel any ongoing jobs that accesses the already failed device.

Client drivers are recommended to set up their [**NET_DEVICE_RESET_DIAGNOSTICS_CAPABILITIES**](../netdevice/ns-netdevice-net_device_reset_diagnostics_capabilities.md) in order to help the framework to collect meaningful reset diagnostics in the process of device reset and recovery.
For how to collect reset diagnostics, see [Register the optional diagnostics collection callback](/windows-hardware/drivers/netcx/platform-level-device-reset/#register-the-optional-diagnostics-collection-callback).


## -see-also

[Recovering unresponsive NIC with NetAdapterCx PLDR](/windows-hardware/drivers/netcx/platform-level-device-reset/).
