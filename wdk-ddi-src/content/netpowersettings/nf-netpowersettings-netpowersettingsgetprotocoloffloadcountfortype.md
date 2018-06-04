---
UID: NF:netpowersettings.NetPowerSettingsGetProtocolOffloadCountForType
title: NetPowerSettingsGetProtocolOffloadCountForType function
author: windows-driver-content
description: Retrieves the number of protocol offload structures in the NETPOWERSETTINGS object for the particular offload type.
ms.assetid: 9d7db442-522c-4079-97b2-24619a845da6
ms.author: windowsdriverdev
ms.date: 02/08/2018
ms.topic: function
ms.keywords: NetPowerSettingsGetProtocolOffloadCountForType
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
-	NetPowerSettingsGetProtocolOffloadCountForType
product: Windows
targetos: Windows
req.product: Windows 10 or later.
---

# NetPowerSettingsGetProtocolOffloadCountForType function


## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1803.

Retrieves the number of protocol offload structures in the NETPOWERSETTINGS object for the particular offload type.

## -parameters

### -param NetPowerSettings
A handle to the NETPOWERSETTINGS object associated with the net adapter. To retrieve the handle, call [NetAdapterGetPowerSettings](../netadapter/nf-netadapter-netadaptergetpowersettings.md).

### -param ProtocolOffloadType
An [NDIS_PM_PROTOCOL_OFFLOAD_TYPE](../ntddndis/ne-ntddndis-_ndis_pm_protocol_offload_type.md) value that contains the type of protocol offload to count.

## -returns
Returns the total number of enabled and disabled protocol offloads in the NETPOWERSETTINGS object for the specified protocol offload type.

## -remarks
The client driver must only call **NetPowerSettingsGetProtocolOffloadCountForType** during a power transition, typically from its *[EVT_WDF_DEVICE_ARM_WAKE_FROM_SX](../wdfdevice/nc-wdfdevice-evt_wdf_device_arm_wake_from_sx.md)*, *[EVT_WDF_DEVICE_ARM_WAKE_FROM_S0](../wdfdevice/nc-wdfdevice-evt_wdf_device_arm_wake_from_s0.md)*, or *[EVT_NET_ADAPTER_PREVIEW_PROTOCOL_OFFLOAD](../netadapter/nc-netadapter-evt_net_adapter_preview_protocol_offload.md)* callback function. Otherwise, the call results in a system bugcheck.

To determine if a specific protocol offload is enabled, call [NetPowerSettingsIsProtocolOffloadEnabled](nf-netpowersettings-netpowersettingsisprotocoloffloadenabled.md).



## -see-also

[NDIS_PM_PROTOCOL_OFFLOAD_TYPE](../ntddndis/ne-ntddndis-_ndis_pm_protocol_offload_type.md)