---
UID: NF:netpowersettings.NetPowerSettingsGetEnabledMediaSpecificWakeUpEvents
title: NetPowerSettingsGetEnabledMediaSpecificWakeUpEvents function (netpowersettings.h)
description: Retrieves flags that specify currently enabled media-specific wake-up events that a network adapter supports.
tech.root: netvista
ms.assetid: a46c5a52-6393-421c-8495-8e8b20b60fba
ms.date: 02/08/2018
ms.topic: function
ms.keywords: NetPowerSettingsGetEnabledMediaSpecificWakeUpEvents
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
-	NetPowerSettingsGetEnabledMediaSpecificWakeUpEvents
product:
-	Windows
targetos: Windows
product:
- Windows
---

# NetPowerSettingsGetEnabledMediaSpecificWakeUpEvents function


## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1809.

Retrieves flags that specify currently enabled media-specific wake-up events that a network adapter supports.

## -parameters

### -param NetPowerSettings
A handle to the NETPOWERSETTINGS object associated with the net adapter. To retrieve the handle, call [NetAdapterGetPowerSettings](../netadapter/nf-netadapter-netadaptergetpowersettings.md).

## -returns
A ULONG value that contains a bitwise OR of [NET_ADAPTER_MEDIA_SPECIFIC_WAKEUP_EVENTS_FLAGS](../netadapter/ne-netadapter-_net_adapter_media_specific_wakeup_events_flags.md)-typed flags that correspond to events that the client driver reported in the **SupportedMediaSpecificWakeUpEvents** member of the [NET_ADAPTER_POWER_CAPABILITIES](../netadapter/ns-netadapter-_net_adapter_power_capabilities.md) structure. The flags represent the media-specific wake-up events that the driver must enable in the hardware to arm the device for wake.

For more information, see the **MediaSpecificWakeUpEvents** member of [NDIS_PM_PARAMETERS](../ntddndis/ns-ntddndis-_ndis_pm_parameters.md).

## -remarks
The client driver must only call **NetPowerSettingsGetEnabledMediaSpecificWakeUpEvents** during a power transition, typically from its *[EVT_WDF_DEVICE_ARM_WAKE_FROM_SX](../wdfdevice/nc-wdfdevice-evt_wdf_device_arm_wake_from_sx.md)* or *[EVT_WDF_DEVICE_ARM_WAKE_FROM_S0](../wdfdevice/nc-wdfdevice-evt_wdf_device_arm_wake_from_s0.md)* callback function. Otherwise, the call results in a system bugcheck.



## -see-also

[NDIS_PM_PARAMETERS](../ntddndis/ns-ntddndis-_ndis_pm_parameters.md)
