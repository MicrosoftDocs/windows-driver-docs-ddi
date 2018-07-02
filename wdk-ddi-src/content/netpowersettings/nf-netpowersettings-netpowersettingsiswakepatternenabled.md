---
UID: NF:netpowersettings.NetPowerSettingsIsWakePatternEnabled
title: NetPowerSettingsIsWakePatternEnabled function
author: windows-driver-content
description: Determines if a wake-on-LAN (WoL) pattern is enabled for a network adapter.
ms.assetid: 3ae9bce4-27db-404a-a9c7-6958004fcd0d
ms.author: windowsdriverdev
ms.date: 02/08/2018
ms.topic: function
ms.keywords: NetPowerSettingsIsWakePatternEnabled
req.header: netpowersettings.h
req.include-header: netadaptercx.h
req.target-type: Universal
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver: 1.23
req.umdf-ver:
req.lib: NetAdapterCxStub.lib
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
-	apiref
apitype: 
-	HeaderDef
apilocation: 
-	netpowersettings.h
apiname: 
-	NetPowerSettingsIsWakePatternEnabled
product: Windows
targetos: Windows
req.product: Windows 10 or later.
---

# NetPowerSettingsIsWakePatternEnabled function


## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1809.

Determines if a wake-on-LAN (WoL) pattern is enabled for a network adapter.

## -parameters

### -param NetPowerSettings
A handle to the NETPOWERSETTINGS object associated with the net adapter. To retrieve the handle, call [NetAdapterGetPowerSettings](../netadapter/nf-netadapter-netadaptergetpowersettings.md).

### -param NdisPmWolPattern
A pointer to an [NDIS_PM_WOL_PATTERN](../ntddndis/ns-ntddndis-_ndis_pm_wol_pattern.md) structure obtained by calling [NetPowerSettingsGetWakePattern](nf-netpowersettings-netpowersettingsgetwakepattern.md).

## -returns
Returns **TRUE** if the WoL pattern is enabled and the driver must enable it in its hardware, and **FALSE** otherwise.

## -remarks
The client driver must only call **NetPowerSettingsIsWakePatternEnabled** during a power transition, typically from its *[EVT_WDF_DEVICE_ARM_WAKE_FROM_SX](../wdfdevice/nc-wdfdevice-evt_wdf_device_arm_wake_from_sx.md)*, *[EVT_WDF_DEVICE_ARM_WAKE_FROM_S0](../wdfdevice/nc-wdfdevice-evt_wdf_device_arm_wake_from_s0.md)*, or *[EVT_NET_ADAPTER_PREVIEW_WAKE_PATTERN](../netadapter/nc-netadapter-evt_net_adapter_preview_wake_pattern.md)* callback function. Otherwise, the call results in a system bugcheck.

If the wake pattern is enabled, the driver programs its hardware to enable the pattern during a power down transition.



## -see-also

[NDIS_PM_WOL_PATTERN](../ntddndis/ns-ntddndis-_ndis_pm_wol_pattern.md)