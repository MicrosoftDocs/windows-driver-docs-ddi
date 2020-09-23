---
UID: NC:netdevice.EVT_NET_DEVICE_PREVIEW_WAKE_SOURCE
title: EVT_NET_DEVICE_PREVIEW_WAKE_SOURCE (netdevice.h)
description: Implement this optional callback to reject wake patterns that are not compatible with your hardware.
tech.root: netvista
ms.assetid: d227adc8-0a5f-4cc7-967f-555336f05ef2
ms.date: 10/11/2019
keywords: ["EVT_NET_DEVICE_PREVIEW_WAKE_SOURCE callback function"]
req.header: netdevice.h
req.include-header: netadaptercx.h 
req.target-type: Universal
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
targetos: Windows
ms.custom: Vb
f1_keywords:
 - EVT_NET_DEVICE_PREVIEW_WAKE_SOURCE
 - netdevice/EVT_NET_DEVICE_PREVIEW_WAKE_SOURCE
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - netdevice.h
api_name:
 - EVT_NET_DEVICE_PREVIEW_WAKE_SOURCE
product:
 - Windows
---

# EVT_NET_DEVICE_PREVIEW_WAKE_SOURCE callback function


## -description

Implement this optional callback to reject wake patterns that are not compatible with your hardware.

## -parameters

### -param Device: 

The WDFDEVICE object that the client driver previously obtained with a call to [**WdfDeviceCreate**](../wdfdevice/nf-wdfdevice-wdfdevicecreate.md).

### -param WakeSource: 

A NETWAKESOURCE object that represents the wake source to examine.

## -returns

To accept the pattern, the callback function must return STATUS_SUCCESS.

To reject the pattern, return STATUS_NDIS_PM_WOL_PATTERN_LIST_FULL.

## -prototype

```
//Declaration

EVT_NET_DEVICE_PREVIEW_WAKE_SOURCE EvtNetDevicePreviewWakeSource; 

// Definition

NTSTATUS EvtNetDevicePreviewWakeSource 
(
	WDFDEVICE Device
	NETWAKESOURCE WakeSource
)
{...}

```

## -remarks

Drivers are not required to implement *EvtNetDevicePreviewWakeSource*, as NetAdapterCx already blocks wake sources that are not compatible with the driver's [**NET_ADAPTER_WAKE_BITMAP_CAPABILITIES**](../netadapter/ns-netadapter-_net_adapter_wake_bitmap_capabilities.md). However, if your hardware has additional limitations that cannot be expressed in the bitmap capabilities structure, you can provide *EvtNetDevicePreviewWakeSource* to enforce those additional limitations.

Register your implementation of this callback function by setting the appropriate member of the [**NET_DEVICE_POWER_POLICY_EVENT_CALLBACKS**](../netdevice/ns-netdevice-_net_device_power_policy_event_callbacks.md), then calling [**NetDeviceInitSetPowerPolicyEventCallbacks**](../netdevice/nf-netdevice-netdeviceinitsetpowerpolicyeventcallbacks.md).

Client drivers typically call **NetDeviceInitSetPowerPolicyEventCallbacks** when creating the device object, before calling [**WdfDeviceCreate**](../wdfdevice/nf-wdfdevice-wdfdevicecreate.md).

In this callback, client drivers get the chance to reject the wake source. For example, if the number of power filters in the current wake source list for **Device** have already reached or exceeded the number of power filters that the hardware supports, the driver can reject this wake source.

For more info, see [Configuring Power Management](/windows-hardware/drivers/netcx/configuring-power-management).

## -see-also