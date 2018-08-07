---
UID: NS:netadapter._NET_ADAPTER_POWER_CAPABILITIES
title: _NET_ADAPTER_POWER_CAPABILITIES
author: windows-driver-content
description: Describes the power capabilities of the adapter.
ms.assetid: ffd56d81-ed07-4c28-bbb3-dd872f935da3
ms.author: windowsdriverdev
ms.date: 02/06/2018
ms.topic: struct
ms.prod: windows-hardware
ms.technology: windows-devices
ms.keywords: _NET_ADAPTER_POWER_CAPABILITIES, *PNET_ADAPTER_POWER_CAPABILITIES, NET_ADAPTER_POWER_CAPABILITIES, 
req.header: netadapter.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver: 1.21
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.alt-api:
req.alt-loc:
req.typenames: NET_ADAPTER_POWER_CAPABILITIES, *PNET_ADAPTER_POWER_CAPABILITIES
topictype: 
-	apiref
apitype: 
-	HeaderDef
apilocation: 
-	netadapter.h
apiname: 
-	NET_ADAPTER_POWER_CAPABILITIES
product:
-	Windows
targetos: Windows
req.product: Windows 10 or later.
---

# _NET_ADAPTER_POWER_CAPABILITIES structure

## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1809.

Describes the power capabilities of the adapter.

## -struct-fields

### -field Size
The size of this structure, in bytes.
 
### -field Flags
A bitwise OR of [NET_ADAPTER_POWER_FLAGS](ne-netadapter-_net_adapter_power_flags.md)-typed flags.
 
### -field SupportedWakePatterns
A bitwise OR of [NET_ADAPTER_WAKE_PATTERN_FLAGS](ne-netadapter-_net_adapter_wake_pattern_flags.md)-typed flags that specify the wake-on-LAN (WOL) patterns that a network adapter supports.
 
### -field NumTotalWakePatterns
The total number of wake patterns that a network adapter supports. This is the sum of the number of supported wake protocol patterns and the number of supported wake bitmap patterns.
 
### -field MaxWakePatternSize
The maximum number of bytes that can be compared with a pattern.
 
### -field MaxWakePatternOffset
The number of bytes in a packet that can be examined, starting at the beginning of the MAC header.
 
### -field MaxWakePacketSaveBuffer
The number of bytes of a wake packet that the client can save to a buffer and indicate up the driver stack. This value must be less than or equal to the size, in bytes, of the maximum transmission unit (MTU) for the network media.
 
### -field SupportedProtocolOffloads
A bitwise OR of [NET_ADAPTER_PROTOCOL_OFFLOADS_FLAGS](ne-netadapter-_net_adapter_protocol_offloads_flags.md)-typed flags that specify the protocol offload features that a network adapter supports.
 
### -field NumArpOffloadIPv4Addresses
The number of IPv4 addresses that the adapter supports for ARP offload.
 
### -field NumNSOffloadIPv6Addresses
The number of IPv6 NS offload requests that the adapter supports. This should be at least 2.
 
### -field SupportedWakeUpEvents
A bitwise OR of [NET_ADAPTER_WAKEUP_EVENTS_FLAGS](ne-netadapter-_net_adapter_wakeup_events_flags.md)-typed flags that specify the media-independent wake-up events that a network adapter supports.
 
### -field SupportedMediaSpecificWakeUpEvents
A bitwise OR of [NET_ADAPTER_MEDIA_SPECIFIC_WAKEUP_EVENTS_FLAGS](ne-netadapter-_net_adapter_media_specific_wakeup_events_flags.md)-typed flags that specify the media-specific wake-up events that a network adapter supports.
 
### -field EvtAdapterPreviewWakePattern
A pointer to the client's implementation of the *[EVT_NET_ADAPTER_PREVIEW_WAKE_PATTERN](nc-netadapter-evt_net_adapter_preview_wake_pattern.md)* event callback.
 
### -field EvtAdapterPreviewProtocolOffload
A pointer to the client's implementation of the *[EVT_NET_ADAPTER_PREVIEW_PROTOCOL_OFFLOAD](nc-netadapter-evt_net_adapter_preview_protocol_offload.md)* event callback.
 
### -field ManageS0IdlePowerReferences
A [WDF_TRI_STATE](../wdftypes/ne-wdftypes-_wdf_tri_state.md)-typed enumerator that indicates whether NetAdapterCx should manage power references for scenarios such as modern standby (AoAC). See more info in the **Remarks** section. This member can have one of the following values:

**WdfTrue** - NetAdapterCx manages power references. The client driver must be the power policy owner to specify **WdfTrue**.
**WdfFalse** - NetAdapterCx does not manage power references.
**WdfUseDefault** : if driver is the power policy owner, then use **WdfTrue**; otherwise, use **WdfFalse**.

## -remarks
The client driver passes an initialized **NET_ADAPTER_POWER_CAPABILITIES** structure as an input parameter value to [NetAdapterSetPowerCapabilities](nf-netadapter-netadaptersetpowercapabilities.md).

Call [NET_ADAPTER_POWER_CAPABILITIES_INIT](nf-netadapter-net_adapter_power_capabilities_init.md) to initialize this structure.

The client driver configures its S0-Idle policy like any other WDF driver, by calling [WdfDeviceAssignS0IdleSettings](../wdfdevice/nf-wdfdevice-wdfdeviceassigns0idlesettings.md).

When power reference management is enabled via **ManageS0IdlePowerReferences**, NetAdapterCx manages power references that result in the WDFDEVICE being powered up/down as necessary. For example, the class extension acquires and releases power references so the device maintains power state as necessary to support modern standby (AoAC). Additionally, the client driver can set the **NET_ADAPTER_POWER_SELECTIVE_SUSPEND** flag in the [NET_ADAPTER_POWER_FLAGS](ne-netadapter-_net_adapter_power_flags.md) enumeration to cause NetAdapterCx to manage power references for the data and control path. This will result in the device being powered down when it is idle. Note that the **NET_ADAPTER_POWER_SELECTIVE_SUSPEND** option results in improved power efficiency at the cost of some performance.



## -see-also

[Power Policy Ownership](https://docs.microsoft.com/windows-hardware/drivers/wdf/power-policy-ownership)