---
UID: NF:netpowersettings.NetPowerSettingsGetWakePatternCountForType
title: NetPowerSettingsGetWakePatternCountForType function (netpowersettings.h)
description: Retrieves the number of wake-on-LAN (WoL) patterns stored in the NETPOWERSETTINGS object for the specified wake pattern type.
tech.root: netvista
ms.assetid: 87e1c05c-ca73-40b0-add8-ec3c56697557
ms.date: 02/08/2018
ms.topic: function
ms.keywords: NetPowerSettingsGetWakePatternCountForType
req.header: netpowersettings.h
req.include-header: netadaptercx.h
req.target-type: Universal
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver: 1.23
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
req.alt-api:
req.alt-loc:
topictype: 
- apiref
apitype: 
- HeaderDef
apilocation: 
- netpowersettings.h
apiname: 
- NetPowerSettingsGetWakePatternCountForType
product:
- Windows
targetos: Windows
product:
- Windows
---

# NetPowerSettingsGetWakePatternCountForType function


## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1809.

Retrieves the number of wake-on-LAN (WoL) patterns stored in the NETPOWERSETTINGS object for the specified wake pattern type.

## -parameters

### -param NetPowerSettings
A handle to the NETPOWERSETTINGS object associated with the net adapter. To retrieve the handle, call [NetAdapterGetPowerSettings](../netadapter/nf-netadapter-netadaptergetpowersettings.md).

### -param WakePatternType
An [NDIS_PM_WOL_PACKET](../ntddndis/ne-ntddndis-_ndis_pm_wol_packet.md) value that contains the type of wake pattern to count.

## -returns
Returns the total number of enabled and disabled wake patterns stored in the NETPOWERSETTINGS object for the specified pattern type.

## -remarks
The client driver must only call **NetPowerSettingsGetWakePatternCountForType** during a power transition, typically from its *[EVT_WDF_DEVICE_ARM_WAKE_FROM_SX](../wdfdevice/nc-wdfdevice-evt_wdf_device_arm_wake_from_sx.md)*, *[EVT_WDF_DEVICE_ARM_WAKE_FROM_S0](../wdfdevice/nc-wdfdevice-evt_wdf_device_arm_wake_from_s0.md)*, or *[EVT_NET_ADAPTER_PREVIEW_WAKE_PATTERN](../netadapter/nc-netadapter-evt_net_adapter_preview_wake_pattern.md)* callback function. Otherwise, the call results in a system bugcheck.

To determine if a specific wake pattern is enabled, call [NetPowerSettingsIsWakePatternEnabled](nf-netpowersettings-netpowersettingsiswakepatternenabled.md).



## -see-also

[NDIS_PM_WOL_PACKET](../ntddndis/ne-ntddndis-_ndis_pm_wol_packet.md)

[NDIS_PM_WOL_PATTERN](../ntddndis/ns-ntddndis-_ndis_pm_wol_pattern.md)
