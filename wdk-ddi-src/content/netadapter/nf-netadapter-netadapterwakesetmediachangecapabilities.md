---
UID: NF:netadapter.NetAdapterWakeSetMediaChangeCapabilities
title: NetAdapterWakeSetMediaChangeCapabilities function (netadapter.h)
author: windows-driver-content
description: The NetAdapterWakeSetMediaChangeCapabilities method sets a net adapter's media change wake on LAN (WoL) capabilities.
tech.root: netvista
ms.assetid: 1814a1fc-1e1e-4b73-8104-3e7991ffa64f
ms.author: windowsdriverdev
ms.date: 10/25/2019
keywords: ["NetAdapterWakeSetMediaChangeCapabilities function"]
f1_keywords:
 - "netadapter/NetAdapterWakeSetMediaChangeCapabilities"
 - "NetAdapterWakeSetMediaChangeCapabilities"
ms.keywords: NetAdapterWakeSetMediaChangeCapabilities
req.header: netadapter.h
req.include-header:
req.target-type: Universal
req.target-min-winverclnt: Windows 10, version 2004
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib: netadaptercxstub.lib
req.dll:
req.irql: PASSIVE_LEVEL
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
topic_type: 
- apiref
api_type: 
- LibDef
api_location: 
- netadaptercxstub.lib
api_name: 
- NetAdapterWakeSetMediaChangeCapabilities
product: 
- Windows
targetos: Windows
ms.custom: Vb
---

# NetAdapterWakeSetMediaChangeCapabilities function


## -description

The **NetAdapterWakeSetMediaChangeCapabilities** method sets a net adapter's media change wake on LAN (WoL) capabilities.

## -parameters

### -param Adapter

A handle to a NETADAPTER object that the client driver obtained from a previous call to [**NetAdapterCreate**](../netadapter/nf-netadapter-netadaptercreate.md).

### -param Capabilities

A pointer to a client driver-allocated and initialized [**NET_ADAPTER_WAKE_MEDIA_CHANGE_CAPABILITIES**](../netadapter/ns-netadapter-_net_adapter_wake_media_change_capabilities.md) structure.

## -returns

This method does not return a value.

## -remarks

Client drivers must call [**NET_ADAPTER_WAKE_MEDIA_CHANGE_CAPABILITIES_INIT**](../netadapter/nf-netadapter-net_adapter_wake_media_change_capabilities_init.md) to initialize the **NET_ADAPTER_WAKE_MEDIA_CHANGE_CAPABILITIES** structure, then set the structure's members appropriately before calling this method. Client drivers typically call this method from within their [*EvtDevicePrepareHardware*](../wdfdevice/nc-wdfdevice-evt_wdf_device_prepare_hardware.md) callback, but **must** call this method before calling [**NetAdapterStart**](nf-netadapter-netadapterstart.md).

## -see-also

[Configuring power management](https://docs.microsoft.com/windows-hardware/drivers/netcx/configuring-power-management)

[**NET_ADAPTER_WAKE_MEDIA_CHANGE_CAPABILITIES**](../netadapter/ns-netadapter-_net_adapter_wake_media_change_capabilities.md)

[**NET_ADAPTER_WAKE_MEDIA_CHANGE_CAPABILITIES_INIT**](../netadapter/nf-netadapter-net_adapter_wake_media_change_capabilities_init.md)

[**NetAdapterCreate**](../netadapter/nf-netadapter-netadaptercreate.md)

[*EvtDevicePrepareHardware*](../wdfdevice/nc-wdfdevice-evt_wdf_device_prepare_hardware.md)

[**NetAdapterStart**](nf-netadapter-netadapterstart.md)
