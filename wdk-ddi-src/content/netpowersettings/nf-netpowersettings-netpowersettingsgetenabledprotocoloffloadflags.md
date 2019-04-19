---
UID: NF:netpowersettings.NetPowerSettingsGetEnabledProtocolOffloadFlags
title: NetPowerSettingsGetEnabledProtocolOffloadFlags function (netpowersettings.h)
description: Retrieves flags that specify currently enabled low power protocol offloads that a network adapter supports.
tech.root: netvista
ms.assetid: 80320d68-e1cd-49b1-b8e0-5709ab7a1817
ms.date: 02/08/2018
ms.topic: function
ms.keywords: NetPowerSettingsGetEnabledProtocolOffloadFlags
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
- NetPowerSettingsGetEnabledProtocolOffloadFlags
product:
- Windows
targetos: Windows
product:
- Windows
---

# NetPowerSettingsGetEnabledProtocolOffloadFlags function


## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1903.

Retrieves flags that specify currently enabled low power protocol offloads that a network adapter supports.

## -parameters

### -param NetPowerSettings
A handle to the NETPOWERSETTINGS object associated with the net adapter. To retrieve the handle, call [NetAdapterGetPowerSettings](../netadapter/nf-netadapter-netadaptergetpowersettings.md).

## -returns
A ULONG value that contains a bitwise OR of [NET_ADAPTER_PROTOCOL_OFFLOADS_FLAGS](../netadapter/ne-netadapter-_net_adapter_protocol_offloads_flags.md)-typed flags that correspond to events that the client driver reported in the **SupportedProtocolOffloads** member of the [NET_ADAPTER_POWER_CAPABILITIES](../netadapter/ns-netadapter-_net_adapter_power_capabilities.md) structure. NDIS uses these flags to enable the low power protocol offload capabilities on a network adapter.

For more information, see [NDIS_PM_PARAMETERS](../ntddndis/ns-ntddndis-_ndis_pm_parameters.md).

## -remarks
The client driver must only call **NetPowerSettingsGetEnabledProtocolOffloadFlags** during a power transition, typically from its *[EVT_WDF_DEVICE_ARM_WAKE_FROM_SX](../wdfdevice/nc-wdfdevice-evt_wdf_device_arm_wake_from_sx.md)* or *[EVT_WDF_DEVICE_ARM_WAKE_FROM_S0](../wdfdevice/nc-wdfdevice-evt_wdf_device_arm_wake_from_s0.md)* callback function. Otherwise, the call results in a system bugcheck.



## -see-also
