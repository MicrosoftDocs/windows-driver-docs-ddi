---
UID: NF:netpowersettings.NetPowerSettingsGetEnabledWakeUpFlags
title: NetPowerSettingsGetEnabledWakeUpFlags function (netpowersettings.h)
description: Retrieves flags that specify currently enabled media-independent wake-up events that a network adapter supports.
tech.root: netvista
ms.assetid: 2b658690-0b0e-4b28-93c0-6540a2527c30
ms.date: 02/08/2018
ms.topic: function
ms.keywords: NetPowerSettingsGetEnabledWakeUpFlags
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
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location:
- netpowersettings.h
api_name: 
- NetPowerSettingsGetEnabledWakeUpFlags
product:
- Windows
targetos: Windows
product:
- Windows
---

# NetPowerSettingsGetEnabledWakeUpFlags function


## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1809.

Retrieves flags that specify currently enabled media-independent wake-up events that a network adapter supports.

## -parameters

### -param NetPowerSettings
A handle to the NETPOWERSETTINGS object associated with the net adapter. To retrieve the handle, call [NetAdapterGetPowerSettings](../netadapter/nf-netadapter-netadaptergetpowersettings.md).


## -returns
A ULONG value that contains a bitwise OR of [NET_ADAPTER_WAKEUP_EVENTS_FLAGS](../netadapter/ne-netadapter-_net_adapter_wakeup_events_flags.md)-typed flags that correspond to wake-up events that the client driver reported in the **SupportedWakeUpEvents** member of the [NET_ADAPTER_POWER_CAPABILITIES](../netadapter/ns-netadapter-_net_adapter_power_capabilities.md) structure. 

For more information, see the **WakeUpFlags** member of [NDIS_PM_PARAMETERS](../ntddndis/ns-ntddndis-_ndis_pm_parameters.md).

## -remarks
The client driver must only call **NetPowerSettingsGetEnabledWakeUpFlags** during a power transition, typically from its *[EVT_WDF_DEVICE_ARM_WAKE_FROM_SX](../wdfdevice/nc-wdfdevice-evt_wdf_device_arm_wake_from_sx.md)* or *[EVT_WDF_DEVICE_ARM_WAKE_FROM_S0](../wdfdevice/nc-wdfdevice-evt_wdf_device_arm_wake_from_s0.md)* callback function. Otherwise, the call results in a system bugcheck.



## -see-also

[NDIS_PM_PARAMETERS](../ntddndis/ns-ntddndis-_ndis_pm_parameters.md)
