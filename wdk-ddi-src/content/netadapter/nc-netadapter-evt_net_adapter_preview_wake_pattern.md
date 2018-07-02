---
UID: NC:netadapter.EVT_NET_ADAPTER_PREVIEW_WAKE_PATTERN
title: EVT_NET_ADAPTER_PREVIEW_WAKE_PATTERN
author: windows-driver-content
description: Implement this optional callback to reject wake patterns that are not compatible with your hardware.
ms.assetid: 2ce5d3bd-0719-4b5b-a416-370d743dce56
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
req.irql: 
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
-	EvtNetAdapterPreviewWakePattern
product: Windows
targetos: Windows
req.typenames: 
req.product: Windows 10 or later.
---

# EVT_NET_ADAPTER_PREVIEW_WAKE_PATTERN callback function

## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1809.

Implement this optional callback to reject wake patterns that are not compatible with your hardware.

## -prototype

```c++
//Declaration

EVT_NET_ADAPTER_PREVIEW_WAKE_PATTERN EvtNetAdapterPreviewWakePattern; 

// Definition

NTSTATUS EvtNetAdapterPreviewWakePattern 
(
	_In_	NETADAPTER				Adapter,
	_In_	NETPOWERSETTINGS		ExistingPowerSettings,
	_In_	NDIS_PM_WOL_PACKET 		WakePatternType,
	_In_	PNDIS_PM_WOL_PATTERN	PatternToBeAdded
)
{...}

typedef EVT_NET_ADAPTER_PREVIEW_WAKE_PATTERN *PFN_NET_ADAPTER_PREVIEW_WAKE_PATTERN;
```

## -parameters

### -param Adapter

The network adapter object that the client created in a prior call to [NetAdapterCreate](nf-netadapter-netadaptercreate.md).

### -param ExistingPowerSettings 

A handle to the net power settings object.

### -param WakePatternType 

An [NDIS_PM_WOL_PACKET](../ntddndis/ne-ntddndis-_ndis_pm_wol_packet.md) enumeration value that specifies the type of the WOL packet.

### -param PatternToBeAdded 

A pointer to an [NDIS_PM_WOL_PATTERN](../ntddndis/ns-ntddndis-_ndis_pm_wol_pattern.md) structure that specifies the wake-on-LAN (WOL) pattern to accept or reject. The client driver can use this pointer to examine the **NDIS_PM_WOL_PATTERN** structure but should not retain it. NetAdapterCx will destroy the wake pattern structure once the driver's *EvtNetAdapterPreviewWakePattern* returns.

## -returns

To accept the pattern, the callback function must return STATUS_SUCCESS.

To reject the pattern, return STATUS_NDIS_PM_WOL_PATTERN_LIST_FULL.

## -remarks

Drivers are not required to implement EvtNetAdapterPreviewWakePattern, as NetAdapter already blocks wake patterns that are not compatible with the driver's [NET_ADAPTER_POWER_CAPABILITIES](ns-netadapter-_net_adapter_power_capabilities.md). However, if your hardware has additional limitations that cannot be expressed in the [NET_ADAPTER_POWER_CAPABILITIES](ns-netadapter-_net_adapter_power_capabilities.md) structure, you can provide *EvtNetAdapterPreviewWakePattern* to enforce those additional limitations.

Register your implementation of this callback function by setting the appropriate member of [NET_ADAPTER_POWER_CAPABILITIES](ns-netadapter-_net_adapter_power_capabilities.md) and then calling [NetAdapterSetPowerCapabilities](nf-netadapter-netadaptersetpowercapabilities.md) during *EVT_NET_ADAPTER_SET_CAPABILITIES*.

The client driver can use the pointer to examine the **NDIS_PM_WOL_PATTERN** structure but should not retain it. NetAdapterCx will destroy the wake pattern structure once the driver's *EvtNetAdapterPreviewWakePattern* returns.

In this callback, the driver typically uses the NETPOWERSETTINGS handle it receives in the *ExistingPowerSettings* parameter to iterate through the enabled wake patterns to determine whether to accept or reject *PatternToBeAdded*. For an example, see [Configuring Power Management](https://docs.microsoft.com/windows-hardware/drivers/netcx/configuring-power-management).

In its [EvtDeviceArmWakeFromS0](../wdfdevice/nc-wdfdevice-evt_wdf_device_arm_wake_from_s0.md) and [EvtDeviceArmWakeFromSx](../wdfdevice/nc-wdfdevice-evt_wdf_device_arm_wake_from_sx.md) callback functions, the driver can iterate through the enabled wake patterns and protocol offloads to program them into the hardware.

## -see-also

[EVT_NET_ADAPTER_PREVIEW_PROTOCOL_OFFLOAD](nc-netadapter-evt_net_adapter_preview_protocol_offload.md)

[NetAdapterSetPowerCapabilities](nf-netadapter-netadaptersetpowercapabilities.md)