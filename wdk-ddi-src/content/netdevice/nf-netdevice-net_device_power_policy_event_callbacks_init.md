---
UID: NF:netdevice.NET_DEVICE_POWER_POLICY_EVENT_CALLBACKS_INIT
title: NET_DEVICE_POWER_POLICY_EVENT_CALLBACKS_INIT function (netdevice.h)
author: windows-driver-content
description: The NET_DEVICE_POWER_POLICY_EVENT_CALLBACKS_INIT method initializes a NET_DEVICE_POWER_POLICY_EVENT_CALLBACKS structure.
tech.root: netvista
ms.assetid: adf5b2fc-1b9a-4dad-97ad-e23f382acb8c
ms.author: windowsdriverdev
ms.date: 10/11/2019
keywords: ["NET_DEVICE_POWER_POLICY_EVENT_CALLBACKS_INIT function"]
f1_keywords:
 - "netdevice/NET_DEVICE_POWER_POLICY_EVENT_CALLBACKS_INIT"
ms.keywords: NET_DEVICE_POWER_POLICY_EVENT_CALLBACKS_INIT
req.header: netdevice.h
req.include-header:
req.target-type: Universal
req.target-min-winverclnt: Windows 10, version 2004
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.irql: Any level as long as target memory is resident
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- netdevice.h
api_name: 
- NET_DEVICE_POWER_POLICY_EVENT_CALLBACKS_INIT
product: 
- Windows
targetos: Windows
ms.custom: Vb
---

# NET_DEVICE_POWER_POLICY_EVENT_CALLBACKS_INIT function


## -description

The **NET_DEVICE_POWER_POLICY_EVENT_CALLBACKS_INIT** method initializes a [**NET_DEVICE_POWER_POLICY_EVENT_CALLBACKS**](../netdevice/ns-netdevice-_net_device_power_policy_event_callbacks.md) structure.

## -parameters

### -param Callbacks

A pointer to a driver-allocated [**NET_DEVICE_POWER_POLICY_EVENT_CALLBACKS**](../netdevice/ns-netdevice-_net_device_power_policy_event_callbacks.md) structure.

## -returns

This method does not return a value.

## -remarks

This method zeroes out the **NET_DEVICE_POWER_POLICY_EVENT_CALLBACKS** structure, then fills in the **Size** member. After calling this method, call [**NetDeviceInitSetPowerPolicyEventCallbacks**](../netdevice/nf-netdevice-netdeviceinitsetpowerpolicyeventcallbacks.md) during device initialization before you call [**WdfDeviceCreate**](../wdfdevice/nf-wdfdevice-wdfdevicecreate.md).

## -see-also

[Configuring Power Management](https://docs.microsoft.com/windows-hardware/drivers/netcx/configuring-power-management)

[**NET_DEVICE_POWER_POLICY_EVENT_CALLBACKS**](../netdevice/ns-netdevice-_net_device_power_policy_event_callbacks.md)

[**NetDeviceInitSetPowerPolicyEventCallbacks**](../netdevice/nf-netdevice-netdeviceinitsetpowerpolicyeventcallbacks.md)

[**WdfDeviceCreate**](../wdfdevice/nf-wdfdevice-wdfdevicecreate.md)
