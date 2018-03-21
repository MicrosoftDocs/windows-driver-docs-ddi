---
UID: NC:netadapter.EVT_NET_ADAPTER_PREVIEW_PROTOCOL_OFFLOAD
title: EVT_NET_ADAPTER_PREVIEW_PROTOCOL_OFFLOAD
author: windows-driver-content
description: Implement this optional callback to reject protocol offloads that are not compatible with your hardware.
ms.assetid: 0e0d97a7-16a7-4d5f-8f19-a4fc52608842
ms.author: windowsdriverdev
ms.date: 02/05/2018
ms.topic: callback
ms.prod: windows-hardware
ms.technology: windows-devices
req.header: netadapter.h
req.include-header:
req.target-type: Universal
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver: 1.21
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
topictype: 
-	apiref
apitype: 
-	UserDefined
apilocation: 
-	netadapter.h
apiname: 
-	EVT_NET_ADAPTER_PREVIEW_PROTOCOL_OFFLOAD
product: Windows
targetos: Windows
req.typenames: 
req.product: Windows 10 or later.
---

# EVT_NET_ADAPTER_PREVIEW_PROTOCOL_OFFLOAD callback function

## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1803.

Implement this optional callback to reject protocol offloads that are not compatible with your hardware.

## -prototype

```c++
//Declaration

EVT_NET_ADAPTER_PREVIEW_PROTOCOL_OFFLOAD EvtNetAdapterPreviewProtocolOffload; 

// Definition

NTSTATUS EvtNetAdapterPreviewProtocolOffload 
(
	_In_ 	NETADAPTER 						Adapter,
	_In_ 	NETPOWERSETTINGS				ExistingPowerSettings,
	_In_ 	NDIS_PM_PROTOCOL_OFFLOAD_TYPE	ProtocolOffloadType,
	_In_	PNDIS_PM_PROTOCOL_OFFLOAD		ProtocolOffloadToBeAdded
)
{...}

typedef EVT_NET_ADAPTER_PREVIEW_PROTOCOL_OFFLOAD *PFN_NET_ADAPTER_PREVIEW_PROTOCOL_OFFLOAD;

```

## -parameters

### -param Adapter 
The network adapter object that the client created in a prior call to [NetAdapterCreate](nf-netadapter-netadaptercreate.md).

### -param ExistingPowerSettings  
A handle to the net power settings object.

### -param ProtocolOffloadType: 
An [NDIS_PM_PROTOCOL_OFFLOAD_TYPE](../ntddndis/ne-ntddndis-_ndis_pm_protocol_offload_type.md) enumeration value that specifies the type of protocol offload.

### -param ProtocolOffloadToBeAdded   
A pointer to a structure of type [NDIS_PM_PROTOCOL_OFFLOAD](../ntddndis/ns-ntddndis-_ndis_pm_protocol_offload.md) that specifies the protocol offload to accept or reject.

## -returns

To accept the protocol offload, the callback function must return STATUS_SUCCESS.

To reject the protocol offload, return STATUS_NDIS_PM_PROTOCOL_OFFLOAD_LIST_FULL.

## -remarks

Drivers are not required to implement EvtNetAdapterPreviewProtocolOffload, as NetAdapter already blocks protocol offloads that are not compatible with the driver's [NET_ADAPTER_POWER_CAPABILITIES](ns-netadapter-_net_adapter_power_capabilities.md). However, if your hardware has additional limitations that cannot be expressed in the [NET_ADAPTER_POWER_CAPABILITIES](ns-netadapter-_net_adapter_power_capabilities.md) structure, you can provide *EvtNetAdapterPreviewProtocolOffload* to enforce those additional limitations.

Register your implementation of this callback function by setting the appropriate member of [NET_ADAPTER_POWER_CAPABILITIES](ns-netadapter-_net_adapter_power_capabilities.md), then calling [NetAdapterSetPowerCapabilities](nf-netadapter-netadaptersetpowercapabilities.md) during *[EVT_NET_ADAPTER_SET_CAPABILITIES](nc-netadapter-evt_net_adapter_set_capabilities.md)*.

In this callback, the driver typically iterates through the *ExistingPowerSettings* to determine whether to accept or reject *ProtocolOffloadToBeAdded*.

The client driver can use the pointer to examine the [NDIS_PM_PROTOCOL_OFFLOAD](../ntddndis/ns-ntddndis-_ndis_pm_protocol_offload.md) structure, but should not retain it. NetAdapterCx will destroy the protocol offload structure once the driver's *EvtNetAdapterPreviewProtocolOffload* returns.

For more info, see [Configuring Power Management](https://docs.microsoft.com/windows-hardware/drivers/netcx/configuring-power-management).

The minimum NetAdapterCx version for **EVT_NET_ADAPTER_PREVIEW_PROTOCOL_OFFLOAD** is 1.0.

## -see-also

[EVT_NET_ADAPTER_PREVIEW_WAKE_PATTERN](nc-netadapter-evt_net_adapter_preview_wake_pattern.md)

[NetAdapterSetPowerCapabilities](nf-netadapter-netadaptersetpowercapabilities.md)