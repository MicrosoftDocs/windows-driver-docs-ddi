---
UID: NF:netpowersettings.NetPowerSettingsGetProtocolOffload
title: NetPowerSettingsGetProtocolOffload function
author: windows-driver-content
description: Retrieves a structure that specifies parameters for a low power protocol offload to a network adapter.
ms.assetid: 32c8e98b-8192-442a-8dca-fe97ea5a11bd
ms.author: windowsdriverdev
ms.date: 02/08/2018
ms.topic: function
ms.keywords: NetPowerSettingsGetProtocolOffload
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
-	NetPowerSettingsGetProtocolOffload
product:
-	Windows
targetos: Windows
product:
- Windows
---

# NetPowerSettingsGetProtocolOffload function


## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1809.

Retrieves a structure that specifies parameters for a low power protocol offload to a network adapter.

## -parameters

### -param NetPowerSettings
A handle to the NETPOWERSETTINGS object associated with the net adapter. To retrieve the handle, call [NetAdapterGetPowerSettings](../netadapter/nf-netadapter-netadaptergetpowersettings.md).

### -param Index
A zero-based value that is used as an index into the protocol offload structures associated with the NETPOWERSETTINGS object. This value must be less than the value returned by [NetPowerSettingsGetProtocolOffloadCount](nf-netpowersettings-netpowersettingsgetprotocoloffloadcount.md).

## -returns
Returns a pointer to the [NDIS_PM_PROTOCOL_OFFLOAD](../ntddndis/ns-ntddndis-_ndis_pm_protocol_offload.md) structure at the specified index, or **NULL** if the index value is invalid.

## -remarks
The client driver must only call **NetPowerSettingsGetProtocolOffload** during a power transition, typically from its *[EVT_WDF_DEVICE_ARM_WAKE_FROM_SX](../wdfdevice/nc-wdfdevice-evt_wdf_device_arm_wake_from_sx.md)*, *[EVT_WDF_DEVICE_ARM_WAKE_FROM_S0](../wdfdevice/nc-wdfdevice-evt_wdf_device_arm_wake_from_s0.md)*, or *[EVT_NET_ADAPTER_PREVIEW_PROTOCOL_OFFLOAD](../netadapter/nc-netadapter-evt_net_adapter_preview_protocol_offload.md)* callback function. Otherwise, the call results in a system bugcheck.

The client driver can use the pointer to examine the [NDIS_PM_PROTOCOL_OFFLOAD](../ntddndis/ns-ntddndis-_ndis_pm_protocol_offload.md) structure, but should not retain it. NetAdapterCx automatically releases the protocol offload structure during offload removal.



## -see-also

[NDIS_PM_PROTOCOL_OFFLOAD](../ntddndis/ns-ntddndis-_ndis_pm_protocol_offload.md)