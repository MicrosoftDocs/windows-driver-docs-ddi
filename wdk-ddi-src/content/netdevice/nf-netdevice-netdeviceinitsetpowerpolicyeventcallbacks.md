---
UID: NF:netdevice.NetDeviceInitSetPowerPolicyEventCallbacks
title: NetDeviceInitSetPowerPolicyEventCallbacks function (netdevice.h)
author: windows-driver-content
description: The NetDeviceInitSetPowerPolicyEventCallbacks method sets optional power policy event callbacks during device initialization for a client driver.
tech.root: netvista
ms.assetid: 417d0da7-26f1-4a81-a9ea-0413facffa1d
ms.author: windowsdriverdev
ms.date: 10/11/2019
keywords: ["NetDeviceInitSetPowerPolicyEventCallbacks function"]
f1_keywords:
 - "netdevice/NetDeviceInitSetPowerPolicyEventCallbacks"
ms.keywords: NetDeviceInitSetPowerPolicyEventCallbacks
req.header: netdevice.h
req.include-header:
req.target-type: Universal
req.target-min-winverclnt: Windows 10, version 2004
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib: netadaptercxstub.lib
req.dll:
req.irql: PASSIVE_LEVEL
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
- LibDef
api_location: 
- netadaptercxstub.lib
api_name: 
- NetDeviceInitSetPowerPolicyEventCallbacks
product: 
- Windows
targetos: Windows
ms.custom: Vb
---

# NetDeviceInitSetPowerPolicyEventCallbacks function


## -description

The **NetDeviceInitSetPowerPolicyEventCallbacks** method sets optional power policy event callbacks during device initialization for a client driver.

## -parameters

### -param DeviceInit

A pointer to a WDFDEVICE_INIT object that the client driver received in its [*EvtDriverDeviceAdd*](../wdfdriver/nc-wdfdriver-evt_wdf_driver_device_add.md) routine.

### -param Callbacks

A pointer to a client driver allocated and initialized [**NET_DEVICE_POWER_POLICY_EVENT_CALLBACKS**](../netdevice/ns-netdevice-_net_device_power_policy_event_callbacks.md) structure.

## -returns

This method does not return a value.

## -remarks

Initialize the WDFDEVICE_INIT object by calling [**NetDeviceInitConfig**](../netdevice/nf-netdevice-netdeviceinitconfig.md) before calling this method. Initialize the [**NET_DEVICE_POWER_POLICY_EVENT_CALLBACKS**](../netdevice/ns-netdevice-_net_device_power_policy_event_callbacks.md) structure by calling [**NET_DEVICE_POWER_POLICY_EVENT_CALLBACKS_INIT**](../netdevice/nf-netdevice-net_device_power_policy_event_callbacks_init.md), then fill in pointers to the callbacks that your client driver implements.

## -see-also

[Configuring Power Management](https://docs.microsoft.com/windows-hardware/drivers/netcx/configuring-power-management)

[**NET_DEVICE_POWER_POLICY_EVENT_CALLBACKS**](../netdevice/ns-netdevice-_net_device_power_policy_event_callbacks.md)
