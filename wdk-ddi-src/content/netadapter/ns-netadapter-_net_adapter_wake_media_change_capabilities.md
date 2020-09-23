---
UID: NS:netadapter._NET_ADAPTER_WAKE_MEDIA_CHANGE_CAPABILITIES
title: NET_ADAPTER_WAKE_MEDIA_CHANGE_CAPABILITIES (netadapter.h)
description: The NET_ADAPTER_WAKE_MEDIA_CHANGE_CAPABILITIES structure describes a net adapter's wake on LAN (WoL) capabilities for waking from a media change event.
tech.root: netvista
ms.assetid: 0f6ef6ae-6ba0-4ce1-a780-b18825fb5998
ms.date: 10/25/2019
keywords: ["NET_ADAPTER_WAKE_MEDIA_CHANGE_CAPABILITIES structure"]
ms.keywords: NET_ADAPTER_WAKE_MEDIA_CHANGE_CAPABILITIES, NET_ADAPTER_WAKE_MEDIA_CHANGE_CAPABILITIES,
req.header: netadapter.h
req.include-header: netadaptercx.h 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 2004
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.ddi-compliance: 
req.unicode-ansi: 
req.max-support: 
req.typenames: NET_ADAPTER_WAKE_MEDIA_CHANGE_CAPABILITIES
targetos: Windows
ms.custom: Vb
f1_keywords:
 - _NET_ADAPTER_WAKE_MEDIA_CHANGE_CAPABILITIES
 - netadapter/_NET_ADAPTER_WAKE_MEDIA_CHANGE_CAPABILITIES
 - NET_ADAPTER_WAKE_MEDIA_CHANGE_CAPABILITIES
 - netadapter/NET_ADAPTER_WAKE_MEDIA_CHANGE_CAPABILITIES
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - netadapter.h
api_name:
 - NET_ADAPTER_WAKE_MEDIA_CHANGE_CAPABILITIES
product:
 - Windows
---

# NET_ADAPTER_WAKE_MEDIA_CHANGE_CAPABILITIES structure


## -description

The **NET_ADAPTER_WAKE_MEDIA_CHANGE_CAPABILITIES** structure describes a net adapter's wake on LAN (WoL) capabilities for waking from a media change event.

## -struct-fields

### -field Size

The size of this structure, in bytes.

### -field MediaConnect

A boolean value that describes if the net adapter is capable of waking from a media connect event.

### -field MediaDisconnect

A boolean value that describes if the net adapter is capable of waking from a media disconnect event.

## -remarks

Call [**NET_ADAPTER_WAKE_MEDIA_CHANGE_CAPABILITIES_INIT**](../netadapter/nf-netadapter-net_adapter_wake_media_change_capabilities_init.md) to initialize this structure, then call [**NetAdapterWakeSetMediaChangeCapabilities**](../netadapter/nf-netadapter-netadapterwakesetmediachangecapabilities.md) to set the net adapter's media change WoL capabilities. Client drivers typically call **NetAdapterWakeSetMediaChangeCapabilities** when starting a net adapter, but before calling [**NetAdapterStart**](../netadapter/nf-netadapter-netadapterstart.md).

## -see-also

[Configuring power management](https://docs.microsoft.com/windows-hardware/drivers/netcx/configuring-power-management)

[**NET_ADAPTER_WAKE_MEDIA_CHANGE_CAPABILITIES_INIT**](../netadapter/nf-netadapter-net_adapter_wake_media_change_capabilities_init.md)

[**NetAdapterWakeSetMediaChangeCapabilities**](../netadapter/nf-netadapter-netadapterwakesetmediachangecapabilities.md)

[**NetAdapterStart**](../netadapter/nf-netadapter-netadapterstart.md)

