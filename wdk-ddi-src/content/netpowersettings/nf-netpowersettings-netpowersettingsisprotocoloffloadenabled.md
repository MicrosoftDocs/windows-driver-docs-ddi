---
UID: NF:netpowersettings.NetPowerSettingsIsProtocolOffloadEnabled
title: NetPowerSettingsIsProtocolOffloadEnabled function (netpowersettings.h)
description: Determines if a protocol offload is enabled.
tech.root: netvista
ms.assetid: 94a24518-1a0e-40be-b270-8c3e68222ac4
ms.date: 02/08/2018
ms.topic: function
ms.keywords: NetPowerSettingsIsProtocolOffloadEnabled
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
- NetPowerSettingsIsProtocolOffloadEnabled
product:
- Windows
targetos: Windows
product:
- Windows
---

# NetPowerSettingsIsProtocolOffloadEnabled function


## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1809.

Determines if a protocol offload is enabled.

## -parameters

### -param NetPowerSettings
A handle to the NETPOWERSETTINGS object associated with the net adapter. To retrieve the handle, call [NetAdapterGetPowerSettings](../netadapter/nf-netadapter-netadaptergetpowersettings.md).

### -param NdisProtocolOffload
A pointer to a [NDIS_PM_PROTOCOL_OFFLOAD](../ntddndis/ns-ntddndis-_ndis_pm_protocol_offload.md) structure obtained by calling [NetPowerSettingsGetProtocolOffload](nf-netpowersettings-netpowersettingsgetprotocoloffload.md).

## -returns
Returns **TRUE** if the protocol offload is enabled, and **FALSE** otherwise.

## -remarks
The client driver must only call **NetPowerSettingsIsProtocolOffloadEnabled** during a power transition, typically from its *[EVT_WDF_DEVICE_ARM_WAKE_FROM_SX](../wdfdevice/nc-wdfdevice-evt_wdf_device_arm_wake_from_sx.md)*, *[EVT_WDF_DEVICE_ARM_WAKE_FROM_S0](../wdfdevice/nc-wdfdevice-evt_wdf_device_arm_wake_from_s0.md)*, or *[EVT_NET_ADAPTER_PREVIEW_PROTOCOL_OFFLOAD](../netadapter/nc-netadapter-evt_net_adapter_preview_protocol_offload.md)* callback function. Otherwise, the call results in a system bugcheck.



## -see-also

[NDIS_PM_PROTOCOL_OFFLOAD](../ntddndis/ns-ntddndis-_ndis_pm_protocol_offload.md)
