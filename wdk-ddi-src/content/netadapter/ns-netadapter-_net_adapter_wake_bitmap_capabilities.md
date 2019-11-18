---
UID: NS:netadapter._NET_ADAPTER_WAKE_BITMAP_CAPABILITIES
title: NET_ADAPTER_WAKE_BITMAP_CAPABILITIES (netadapter.h)
author: windows-driver-content
description: The NET_ADAPTER_WAKE_BITMAP_CAPABILITIES structure describes a net adapter's wake on LAN (WoL) capabilities for waking from a bitmap pattern.
tech.root: netvista
ms.assetid: 0d68d5a2-5d25-4f33-96b5-57774a6f441e
ms.author: windowsdriverdev
ms.date: 10/24/2019
ms.topic: struct
f1_keywords:
 - "netadapter/NET_ADAPTER_WAKE_BITMAP_CAPABILITIES"
ms.keywords: NET_ADAPTER_WAKE_BITMAP_CAPABILITIES, NET_ADAPTER_WAKE_BITMAP_CAPABILITIES, 
req.header: netadapter.h
req.include-header:
req.target-type:
req.target-min-winverclnt: The next version of Windows 10
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.typenames: NET_ADAPTER_WAKE_BITMAP_CAPABILITIES
topic_type: 
 - apiref
api_type: 
 - HeaderDef
api_location: 
 - netadapter.h
api_name: 
 - NET_ADAPTER_WAKE_BITMAP_CAPABILITIES
product: 
 - Windows
targetos: Windows
ms.custom: Vb
---

# NET_ADAPTER_WAKE_BITMAP_CAPABILITIES structure

## -description

The **NET_ADAPTER_WAKE_BITMAP_CAPABILITIES** structure describes a net adapter's wake on LAN (WoL) capabilities for waking from a bitmap pattern.

## -struct-fields

### -field Size

The size of this structure, in bytes.
 
### -field BitmapPattern

A boolean value that describes if the net adapter is capable of waking from a bitmap pattern.
 
### -field MaximumPatternCount

The maximum number of bitmap patterns that the hardware supports.
 
### -field MaximumPatternSize

The maximum size, in bytes, for the bitmap patterns that the hardware supports. 

## -remarks

Call [**NET_ADAPTER_WAKE_BITMAP_CAPABILITIES_INIT**](../netadapter/nf-netadapter-net_adapter_wake_bitmap_capabilities_init.md) to initialize this structure, then call [**NetAdapterWakeSetBitmapCapabilities**](../netadapter/nf-netadapter-netadapterwakesetbitmapcapabilities.md) to set the net adapter's bitmap pattern WoL capabilities. Client drivers typically call **NetAdapterWakeSetBitmapCapabilities** when starting a net adapter, but before calling [**NetAdapterStart**](../netadapter/nf-netadapter-netadapterstart.md).

## -see-also

[Configuring power management](https://docs.microsoft.com/windows-hardware/drivers/netcx/configuring-power-management)

[**NET_ADAPTER_WAKE_BITMAP_CAPABILITIES_INIT**](../netadapter/nf-netadapter-net_adapter_wake_bitmap_capabilities_init.md)

[**NetAdapterWakeSetBitmapCapabilities**](../netadapter/nf-netadapter-netadapterwakesetbitmapcapabilities.md)

[**NetAdapterStart**](../netadapter/nf-netadapter-netadapterstart.md)