---
UID: NC:netdevice.EVT_NET_DEVICE_PREVIEW_POWER_OFFLOAD
title: EVT_NET_DEVICE_PREVIEW_POWER_OFFLOAD (netdevice.h)
author: windows-driver-content
description: Implement this optional callback to reject protocol offloads that are not compatible with your hardware.
tech.root: netvista
ms.assetid: 7429f331-19e5-4a1c-8153-b814c57871d6
ms.author: windowsdriverdev
ms.date: 10/10/2019
ms.topic: callback
f1_keywords:
 - "netdevice/EVT_NET_DEVICE_PREVIEW_POWER_OFFLOAD"
req.header: netdevice.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 2004
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
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
 - UserDefined
api_location: 
 - netdevice.h
api_name: 
 - EVT_NET_DEVICE_PREVIEW_POWER_OFFLOAD
product: 
 - Windows
targetos: Windows
ms.custom: Vb
---

# EVT_NET_DEVICE_PREVIEW_POWER_OFFLOAD callback function

## -description

Implement this optional callback to reject protocol offloads that are not compatible with your hardware.

## -prototype

```
//Declaration

EVT_NET_DEVICE_PREVIEW_POWER_OFFLOAD EvtNetDevicePreviewPowerOffload; 

// Definition

NTSTATUS EvtNetDevicePreviewPowerOffload 
(
	WDFDEVICE Device
	NETPOWEROFFLOAD PowerOffload
)
{...}

```

## -parameters

### -param Device: 

The WDFDEVICE object that the client driver previously obtained with a call to [**WdfDeviceCreate**](../wdfdevice/nf-wdfdevice-wdfdevicecreate.md).

### -param PowerOffload: 

A NETPOWEROFFLOAD object that represents the low power protocol offload to examine.

## -returns

To accept the protocol offload, the callback function must return STATUS_SUCCESS.

To reject the protocol offload, return STATUS_NDIS_PM_PROTOCOL_OFFLOAD_LIST_FULL.

## -remarks

Drivers are not required to implement *EvtNetDevicePreviewPowerOffload*, as NetAdapterCx already blocks protocol offloads that are not compatible with the driver's power offload capabilities: [**NET_ADAPTER_POWER_OFFLOAD_ARP_CAPABILITIES**](../netadapter/ns-netadapter-_net_adapter_power_offload_arp_capabilities.md) and [**NET_ADAPTER_POWER_OFFLOAD_NS_CAPABILITIES**](../netadapter/ns-netadapter-_net_adapter_power_offload_ns_capabilities.md). However, if your hardware has additional limitations that cannot be expressed in these capabilities structures, you can provide *EvtNetDevicePreviewPowerOffload* to enforce those additional limitations.

Register your implementation of this callback function by setting the appropriate member of the [**NET_DEVICE_POWER_POLICY_EVENT_CALLBACKS**](../netdevice/ns-netdevice-_net_device_power_policy_event_callbacks.md), then calling [**NetDeviceInitSetPowerPolicyEventCallbacks**](../netdevice/nf-netdevice-netdeviceinitsetpowerpolicyeventcallbacks.md).

Client drivers typically call **NetDeviceInitSetPowerPolicyEventCallbacks** when creating the device object, before calling [**WdfDeviceCreate**](../wdfdevice/nf-wdfdevice-wdfdevicecreate.md).

In this callback, client drivers get the chance to reject the protocol offload. For example, if the number of protocol offloads in the current protocol offload list for **Device** have already reached or exceeded the number of protocol offloads that the hardware supports, the driver can reject this protocol offload.

For more info, see [Configuring Power Management](https://docs.microsoft.com/windows-hardware/drivers/netcx/configuring-power-management).

## -see-also