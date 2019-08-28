---
UID: NF:netpowersettings.NetPowerSettingsGetEnabledWakePatternFlags
title: NetPowerSettingsGetEnabledWakePatternFlags function (netpowersettings.h)
description: Retrieves flags representing currently enabled wake pattern types that a network adapter supports.
tech.root: netvista
ms.assetid: a82e0bdf-45a0-4f69-bd1d-0e863a49f080
ms.date: 02/08/2018
ms.topic: function
f1_keywords:
 - "netpowersettings/NetPowerSettingsGetEnabledWakePatternFlags"
ms.keywords: NetPowerSettingsGetEnabledWakePatternFlags
req.header: netpowersettings.h
req.include-header: netadaptercx.h
req.target-type: Universal
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver: 1.21
req.umdf-ver:
req.lib: NetAdapterCxStub.lib
req.dll:
req.irql: DISPATCH_LEVEL
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
req.alt-api:
req.alt-loc:
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location:
- netpowersettings.h
api_name: 
- NetPowerSettingsGetEnabledWakePatternFlags
targetos: Windows
product:
- Windows
---

# NetPowerSettingsGetEnabledWakePatternFlags function


## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1903.


Retrieves flags representing currently enabled wake pattern types that a network adapter supports.

## -parameters

### -param NetPowerSettings
A handle to the NETPOWERSETTINGS object associated with the net adapter. To retrieve the handle, call [NetAdapterGetPowerSettings](../netadapter/nf-netadapter-netadaptergetpowersettings.md).

## -returns
A ULONG value that contains a bitwise OR of [NET_ADAPTER_WAKE_PATTERN_FLAGS](../netadapter/ne-netadapter-_net_adapter_wake_pattern_flags.md)-typed flags that correspond to capabilities that the client driver reported in the **SupportedWakePacketPatterns** member of the [NET_ADAPTER_POWER_CAPABILITIES](../netadapter/ns-netadapter-_net_adapter_power_capabilities.md) structure. NDIS uses these flags to enable the wake-on-LAN (WOL) patterns that a network adapter uses to wake the local computer from a low power state. 

For more information about WOL patterns, see [NDIS_PM_WOL_PATTERN](../ntddndis/ns-ntddndis-_ndis_pm_wol_pattern.md).

## -remarks
The client driver must only call **NetPowerSettingsGetEnabledWakePatternFlags** during a power transition, typically from its *[EVT_WDF_DEVICE_ARM_WAKE_FROM_SX](../wdfdevice/nc-wdfdevice-evt_wdf_device_arm_wake_from_sx.md)* or *[EVT_WDF_DEVICE_ARM_WAKE_FROM_S0](../wdfdevice/nc-wdfdevice-evt_wdf_device_arm_wake_from_s0.md)* callback function. Otherwise, the call results in a system bugcheck.



## -see-also

- [NetPowerSettingsGetWakePatternCount](nf-netpowersettings-netpowersettingsgetwakepatterncount.md)
- [NDIS_PM_CAPABILITIES](../ntddndis/ns-ntddndis-_ndis_pm_capabilities.md)
- [NDIS_PM_PARAMETERS](../ntddndis/ns-ntddndis-_ndis_pm_parameters.md)
- [NDIS_PM_WOL_PATTERN](../ntddndis/ns-ntddndis-_ndis_pm_wol_pattern.md)
